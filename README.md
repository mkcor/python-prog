# Introduction to Python Programming

This tutorial is aimed at students with little or no programming experience.
It draws inspiration from the late
[Boston Python Workshop](https://wiki.openhatch.org/wiki/Boston_Python_Workshop/1/)
and uses materials from [Software Carpentry](https://software-carpentry.org)
lessons, which are available under the
[CC-BY license](https://creativecommons.org/licenses/by/4.0/).

Please refer to the [Setup](#setup) section to install the required software before the start of the tutorial.

## Schedule

* Morning
  - [JupyterLab](./_episodes/00-run-quit.md)
  - [Variables](./_episodes/01-variables.md)
  - [Lists](./_episodes/02-lists.md)
  - [Loops](./_episodes/03-loops.md)
  - *Coffee break*
  - [Conditionals](./_episodes/04-conditionals.md)
  - Writing Functions
* Afternoon
  - Plotting
  - A web app for free!
  - *Coffee break*
  - Errors and Exceptions
  - Defensive Programming

## Setup

### Installing Python Using Anaconda
1. Open https://www.anaconda.com/products/distribution with your web browser.
2. Click on **Download** to download the Anaconda Installer. If you do not have enough space left on your computer, please refer to the section below: [Installing Python Using Miniconda](#installing-python-using-miniconda).
3. Install Python 3 by running the Anaconda Installer using all of the defaults for installation. Make sure to check **Add Anaconda to my PATH environment variable**.
4. You can check that Python is installed by opening a terminal and typing `python --version`. The response should be `Python 3.10.x`.
5. Install the required packages by running the following lines in your terminal:
```
conda config --add channels conda-forge
conda install voila=0.3.6
```

### Installing Python Using Miniconda
1. Open https://docs.conda.io/en/latest/miniconda.html with your web browser.
2. Click on the latest Installer link depending on your OS: **Miniconda3 Windows 64-bit** for Windows, **Miniconda3 macOS Intel x86 64-bit pkg** for MacOS, **Miniconda3 Linux 64-bit** for Linux.
3. Install Python 3 by running the Anaconda Installer (double click on the downloaded file) using all of the defaults for installation. Make sure to check **Add Miniconda to my PATH environment variable**.
4. You can check that Python is installed by opening a terminal and typing `python --version`. The response should be `Python 3.10.x`.
5. Install the required packages by running the following lines in your terminal:
```
conda config --add channels conda-forge
conda install jupyterlab=3.5.3 matplotlib=3.7.0 ipywidgets=7.6.5 voila=0.3.6
```

## References
