---
layout: page
title: Setup
permalink: /setup/
---

## Setup

1. Open [https://docs.conda.io/en/latest/miniconda.html](https://docs.conda.io/en/latest/miniconda.html) with your web browser.
2. Click on the latest Installer link depending on your OS: **Miniconda3 Windows 64-bit** for Windows, **Miniconda3 macOS Intel x86 64-bit pkg** for MacOS, **Miniconda3 Linux 64-bit** for Linux.
3. Install Python 3 by running the Miniconda Installer (double click on the downloaded file) using all of the defaults for installation. On MacOS and Linux, make sure to check **Add Miniconda to my PATH environment variable**.
4. On Windows: open the **Anaconda Prompt** from the **Start** menu. On MacOs and Linux: open the **Terminal** app. Install the required packages by running the following lines (copy-paste them in the window that just opened up and press Enter):
```
conda config --add channels conda-forge
conda install ipywidgets=7.6.5 jupyterlab=3.5.3 matplotlib=3.7.0 pandas=1.5.3 voila=0.3.6
```
5. Type `jupyter lab` in the Anaconda Prompt / Terminal. After JupyterLab has launched, click the “Python 3” button under “Notebook” in the launcher window, or use the “File” menu, to open a new Python 3 notebook.
6. To test your setup, run the following lines in a cell of the notebook:

```py
import pandas as pd                                                            
                                                                               
table = pd.DataFrame(
    {'Time': [0, 1, 2, 3],
     'Emma': [0, 10, 20, 30]}
)  
table.plot();
```
