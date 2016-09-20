> IP address: 130.238.10.31


## User accounts for instructors


```
sudo adduser taha
# fill in password and details
sudo adduser taha sudo
```

```
sudo adduser matt
sudo adduser matt sudo
```




## Setting up SSH access for instructors

For easier setup, we will **allow password login**. To make it slightly more secure, we'll limit allowed users to the instructors accounts:

```
# in sshd_config
PasswordAuthentication yes
AllowUsers ubuntu taha matt
```


### Generate SSH keypair

On the user's computer, generate a new keypair:

```
ssh-keygen -t rsa -b 4096
# /home/taha/.ssh/uu-rstudio
ssh-copy-id -i uu-rstudio.pub taha@130.238.10.31
ssh-add uu-rstudio
```

For even more ease, add something along the following lines to your `~/.ssh/config`:

```
Host uu-rstudio
Hostname 130.238.10.31
PreferredAuthentications publickey
IdentityFile /home/taha/.ssh/uu-rstudio
User taha
```

## Changed the hostname (FQDN)

In `/etc/hosts`, added the line

```
130.238.10.31 rfps.chepec.se rfps
```

And changed the contents of `/etc/hostname` to

```
rfps
```

Rebooted the machine for the changes to take effect (reboot not strictly necessary).



## Installing Apache

```
$ sudo apt-get install apache2
Reading package lists... Done
Building dependency tree       
Reading state information... Done
The following extra packages will be installed:
  apache2-bin apache2-data libapr1 libaprutil1 libaprutil1-dbd-sqlite3
  libaprutil1-ldap ssl-cert
Suggested packages:
  apache2-doc apache2-suexec-pristine apache2-suexec-custom apache2-utils
  openssl-blacklist
The following NEW packages will be installed:
  apache2 apache2-bin apache2-data libapr1 libaprutil1 libaprutil1-dbd-sqlite3
  libaprutil1-ldap ssl-cert
0 upgraded, 8 newly installed, 0 to remove and 4 not upgraded.
Need to get 1284 kB of archives.
After this operation, 5348 kB of additional disk space will be used.
```

Message during apache install about lack of FQDN:

```
AH00558: apache2: Could not reliably determine the server's fully qualified domain name, using 130.238.10.31. Set the 'ServerName' directive globally to suppress this message
```

(The above error because I installed Apache before setting the FQDN).


To be able to use reverse proxy with Apache, we need some more modules.

```
sudo apt-get install libapache2-mod-proxy-html
sudo apt-get install libxml2-dev
```

Then, to update the Apache configuration files to activate `mod_proxy` you execute the following commands:

```
sudo a2enmod proxy
sudo a2enmod proxy_http
sudo a2enmod proxy_wstunnel
sudo a2enmod rewrite
```

Added the following line to `/etc/rstudio/rserver.conf`:

```
www-address=127.0.0.1
```

There was something amiss, appears related to system locale:

> `$ sudo rstudio-server verify-installation`
`[rserver] ERROR Unexpected exception: locale::facet::_S_create_c_locale name not valid; LOGGED FROM: int main(int, char* const*) /home/ubuntu/rstudio/src/cpp/server/ServerMain.cpp:547`

```
$ sudo dpkg-reconfigure locales
perl: warning: Setting locale failed.
perl: warning: Please check that your locale settings:
	LANGUAGE = (unset),
	LC_ALL = (unset),
	LC_PAPER = "sv_SE.UTF-8",
	LC_ADDRESS = "sv_SE.UTF-8",
	LC_MONETARY = "sv_SE.UTF-8",
	LC_NUMERIC = "sv_SE.UTF-8",
	LC_TELEPHONE = "sv_SE.UTF-8",
	LC_IDENTIFICATION = "sv_SE.UTF-8",
	LC_MEASUREMENT = "sv_SE.UTF-8",
	LC_TIME = "sv_SE.UTF-8",
	LC_NAME = "sv_SE.UTF-8",
	LANG = "en_US.UTF-8"
    are supported and installed on your system.
perl: warning: Falling back to the standard locale ("C").
locale: Cannot set LC_ALL to default locale: No such file or directory
Generating locales...
  en_US.UTF-8... up-to-date
Generation complete.
```

So, it seems a couple locale params are unset. To make the fix stick, I added the following lines to `/etc/environment`:

```
LC_ALL=en_US.UTF-8
LANGUAGE=en_US.UTF-8
```

Now the Rstudio server process verify command gives no errors. Great!


- https://support.rstudio.com/hc/en-us/articles/200552326-Running-RStudio-Server-with-a-Proxy



### TLS certificate

```
# in the home directory of taha
wget https://dl.eff.org/certbot-auto
chmod a+x certbot-auto
./certbot-auto
```


> Failed authorization procedure. rfps.chepec.se (tls-sni-01): urn:acme:error:connection :: The server could not connect to the client to verify the domain :: Failed to connect to 130.238.10.31:443 for TLS-SNI-01 challenge

> Domain: rfps.chepec.se
> Type:   connection
> Detail: Failed to connect to 130.238.10.31:443 for TLS-SNI-01 challenge


**MAJOR ISSUE**: the VM has no publicly routable IP address (only from within UU network).
So no way to get Let's Encrypt TLS certs directly...

That means we will have to run RStudio over HTTP. Or does it?

> Alternatively, you can use the dns-01 challenge (which is not supported yet by the official client software, but is supported by several third-party clients). Since this challenge works by provisioning DNS TXT records, you don't ever need to point an A record at a public IP address.
> So your intranet does not need to be reachable from the Internet, but your domain name does need to exist in the public DNS under your control.



- https://certbot.eff.org/#ubuntutrusty-apache
- [StackExchange: Let's Encrypt for intranet websites?](http://security.stackexchange.com/a/121187)
- [Certificates for domains behind firewall / intermediate CA](https://community.letsencrypt.org/t/certificates-for-domains-behind-firewall-intermediate-ca/18621)
- [How to use Let's Encrypt DNS challenge validation?](http://serverfault.com/questions/750902/how-to-use-lets-encrypt-dns-challenge-validation)
- https://github.com/lukas2511/dehydrated




## Installing R

Added the following line to `/etc/apt/sources.list`:

```
deb https://www.stats.bris.ac.uk/R/bin/linux/ubuntu trusty/
```

Also, added the key for the CRAN repo to our system:

```
sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys E084DAB9
```

Now run `sudo apt-get update`.


```
sudo apt-get install r-base r-base-dev
```

Added default CRAN repo: added the following lines to `/etc/R/Rprofile.site`:

```
local({
   # Set CRAN mirror
   r <- getOption("repos")
   r["CRAN"] <- "https://www.stats.bris.ac.uk/R/"
   options(repos = r,
          # set path to LaTeX compiler
          tikzLatex = "/usr/local/texlive/2016/bin/x86_64-linux/")
})
```

Added PATH to LateX (for TikZ in particular) to `/etc/R/Renviron.site`:

```
PATH=/usr/local/texlive/2016/bin/x86_64-linux:${PATH}
```


### R packages

```
$ sudo R
```

R library paths:

```
> .libPaths()
[1] "/home/taha/R/x86_64-pc-linux-gnu-library/3.3"
[2] "/usr/local/lib/R/site-library"               
[3] "/usr/lib/R/site-library"                     
[4] "/usr/lib/R/library"
```

All packages below should be installed to `.libPaths()[4]`.


Installed `devtools`:

```
install.packages("devtools", lib = .libPaths()[4])
devtools::install_github("hadley/devtools")
```

Installed `tidyverse`.


Installed Linux packages required by some of the above packages:

```
sudo apt-get install libssh2-1-dev libcurl4-openssl-dev
```





## Installing LaTeX

```
wget http://mirror.ctan.org/systems/texlive/tlnet/install-tl-unx.tar.gz
tar xvf install-tl-unx.tar.gz
cd install-tl-20160915/
```

Make sure `/usr/local/texlive` is writable:

```
sudo mkdir /usr/local/texlive
sudo chmod go+w /usr/local/texlive
```

Run the Perl installation script:

```
./install-tl
```

>  Most importantly, add `/usr/local/texlive/2016/bin/x86_64-linux` to your `PATH` for current and future sessions.

Added the following line to `/etc/profile`:

```
PATH=$PATH:/usr/local/texlive/2016/bin/x86_64-linux
```



## Installing Rstudio server

```
sudo apt-get install gdebi-core
wget https://download2.rstudio.org/rstudio-server-0.99.903-amd64.deb
sudo gdebi rstudio-server-0.99.903-amd64.deb
```



- https://www.rstudio.com/products/rstudio/download-server/



## User accounts for participants

```
sudo su
cd
# we are now in /root
nano user-acccounts-participants.txt
```

User names will be the the participant's firts name (no capital lettters, no dots).
Password will be the last part of their user name in their UU email address (no capital letters, no dots).

We'll leave the UID field left empty, GID field left empty, in GECOS we'll fill the Other field, and shell will be bash.

> Well, `newusers` does not work. Apparently it has a [known bug in Ubuntu](https://bugs.launchpad.net/ubuntu/+source/shadow/+bug/1266675).

We'll use this script (by Pavlin Mitev) instead.

```
#!/bin/sh

setpass ()
{
  useradd -m $user ;
  echo "$user:$PASS"| chpasswd ;
}

user="adriane"; PASS="guillaumin"; setpass;
user="andrea"; PASS="pavlou"; setpass;
user="angeliki"; PASS="adamaki"; setpass;
user="anna"; PASS="munke"; setpass;
user="apurve"; PASS="saini"; setpass;
user="arvid"; PASS="gynna"; setpass;
user="burak"; PASS="aktekin"; setpass;
user="delphine"; PASS="lebrun"; setpass;
user="dennis"; PASS="vandermeer"; setpass;
user="emilia"; PASS="lundberg"; setpass;
user="fabian"; PASS="jeschull"; setpass;
user="feres"; PASS="dehchar"; setpass;
user="hasan"; PASS="ali"; setpass;
user="hongji"; PASS="yan"; setpass;
user="jose"; PASS="silva"; setpass;
user="juan"; PASS="jaramillo"; setpass;
user="mia"; PASS="sterby"; setpass;
user="oleksandr"; PASS="bilousov"; setpass;
user="rasmus"; PASS="luthander"; setpass;
user="reza"; PASS="younesi"; setpass;
user="ronnie"; PASS="mogensen"; setpass;
user="sanea"; PASS="sheikh"; setpass;
user="sankara"; PASS="pilla"; setpass;
user="serkan"; PASS="akansel"; setpass;
user="shuyi"; PASS="li"; setpass;
user="suvendu"; PASS="giri"; setpass;
```

```
sudo nano participant_accounts.sh
chmod +x participant_accounts.sh
./participant_accounts.sh
```

Worked like a charm!
