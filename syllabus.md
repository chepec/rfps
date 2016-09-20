# Course syllabus (preliminary)

This is up for discussion but I would suggest this basic structure.

## Day 1 - Complete beginner's introduction

Important packages: `readxl`

### Real basics

- Getting started
    - Install R, RStudio
    - Interpreter
    - Objects, `<-`, `str`, `class`, `data.frame`, `[]`, `$` etc
    - `install.packages`
    - basic functions - arithmetic, `summary`, `mean` etc

### Handling data

- Importing data
    - `read.table`, `read.delim`, `read.csv`
    - `readxl`


- Viewing data
    - `head`, `tail`
    - `View` in RStudio
    - `summary`


- Plotting
    - some basic `ggplot` with built-in dataset, `mtcars` etc


---

## Day 2 - Data manipulation, plotting

Important packages: `dplyr`, `ggplot2`, `reshape2`, `tidyr`




---

## Day 3 - "Programming"

Important packages: `magrittr`, `parallel`

- Write your own functions
- loops
    - `for`, `while`, but emphasise `*apply`, esp. `lapply`, `sapply`
    - `mclapply`?
- readable code

---

## Day 4 - Reporting, community etc.

Important packages: `knitr`

### Reporting

- R Markdown, `knitr` (via RStudio)
- R Notebooks
- LaTeX support

### Community

- StackOverflow
