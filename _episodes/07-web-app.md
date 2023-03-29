---
title: "Creating Interactive Data Visualizations"
teaching: 15
exercises: 15
questions:
- "How can I make my data visualizations interactive?"
- "How can I turn my notebook into a web app?"
objectives:
- "Select a subset of columns and/or rows in a dataframe."
- "Create interactive plots with basic controls (sliders, dropdowns)."
- "Run a Jupyter notebook as a web app."
keypoints:
- "Jupyter widgets let us explore code and data interactively."
- "We can create basic user interface controls using the `interact` function."
- "Voilà allows us to convert Jupyter notebooks into interactive dashboards."
---

## Selecting and Plotting Subsets of (Tabular) Data

For the purpose of this simple demo, let us consider again a toy dataset
consisting of two tiny timeseries. Let us assume that we are tracking the
position of two runners, Emma and Jane.

~~~
import pandas as pd

time = [0, 1, 2, 3]
position = [0, 100, 200, 300]

table = pd.DataFrame({'Time': time, 'Emma': position})
table.set_index('Time', inplace=True)

# Create column for Jane's position
table['Jane'] = [0, 150, 200, 250]

print(table)
~~~
{: .language-python}
~~~
      Emma  Jane
Time
0        0     0
1      100   150
2      200   200
3      300   250
~~~
{: .output}

If we call the `plot` function (method) directly on the `pandas` dataframe, we
get a nice default style:

~~~
table.plot();
~~~
{: .language-python}

![Plot of dataframe with two timeseries](../fig/07_....png)

Indeed, we get a legend and an `xlabel`... for free! Here, we can see the
value of working with *labelled* data.

If we wanted to plot the position of a single runner, say, Jane, we would do
(see previous episode):

~~~
table['Jane'].plot();
~~~
{: .language-python}

![Plot of one timeseries](../fig/07_....png)

If we wanted to plot the positions only up to a certain time point, say, up to
the third time point, we would do:

~~~
table[:3].plot();
~~~
{: .language-python}

![Plot of first three positions](../fig/07_....png)

## Selecting them Interactively

[`ipywidgets`](https://ipywidgets.readthedocs.io/) is a library for exploring
code and data interactively. We import it as follows:

~~~
import ipywidgets as widgets
~~~
{: .language-python}

It provides a function, named `interact`, which allows us to create basic user
interface (UI) controls. For example, we may use a dropdown menu for
selecting the runner (Emma or Jane) whose position we want to visualize.
Likewise, we may use a slider for selecting the end value of the time points.

To begin with, we need to write a function where the parameter is the variable
we want to control (interact with). In the first case,

~~~
def f(x):
    table[x].plot();
~~~
{: .language-python}

and, in the second case,

~~~
def ff(xx):
    table[:xx].plot();
~~~
{: .language-python}

will do. Then, we need to call `interact` with this function as the first
argument and the variable to control as the second argument:

~~~
widgets.interact(f, x={'Emma', 'Jane'});
~~~
{: .language-python}
