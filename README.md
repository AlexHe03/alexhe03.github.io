# Qibing He's Quarto Website

This repository contains my personal Quarto website for DSCI 521. The website includes an introduction, an about page, and computational blog posts written in Python and R.

Live website: <https://alexhe03.github.io>

## Software requirements

The site was built using:

- Quarto 1.10.18
- uv 0.12.7
- Python 3.14.7
- R 4.6.1

Git and the software listed above must be installed before building the site. The R package `renv` will bootstrap itself when R is started from the repository.

## Build instructions

Clone the repository and enter its top-level directory:

```bash
git clone git@github.com:AlexHe03/alexhe03.github.io.git
cd alexhe03.github.io
```

Create the Python environment and install the packages recorded in `uv.lock`:

```bash
uv sync
```

Start R from the top level of the repository:

```bash
R
```

Inside the R session, restore the packages recorded in `renv.lock`, and then exit R:

```r
renv::restore()
q(save = "no")
```

From the top level of the repository, render the complete website:

```bash
uv run quarto render
```

The rendered website is written to the `docs/` directory. On macOS, open the local site with:

```bash
open docs/index.html
```

Alternatively, open `docs/index.html` in a web browser.

## Data

The computational posts use the [Parks dataset](https://opendata.vancouver.ca/explore/dataset/parks/) from the City of Vancouver Open Data Portal. The dataset is provided under the Open Government Licence – Vancouver.

A copy of the dataset is committed at `data/parks.csv`, so the build does not require a network connection to download the data. A network connection is required the first time `uv sync` and `renv::restore()` download the locked software packages.

## Generative AI acknowledgement

OpenAI ChatGPT was used for guidance on the Quarto, `uv`, and `renv` workflow and for assistance drafting and reviewing code and prose. All commands, code, results, and final content were reviewed and verified by myself.