---
title: "Running Python"
teaching: 5
exercises: 5
questions:
- "How can I run Python programs?"
objectives:
- "Launch the JupyterLab server." 
- "Create a Python script." 
- "Create a Jupyter notebook."
- "Shutdown the JupyterLab server."
- "Understand the difference between a Python script and a Jupyter notebook."
- "Create Markdown cells in a notebook."
- "Create and run Python cells in a notebook."
keypoints:
- "Python scripts are plain text files."
- "Use Jupyter notebooks for editing and running Python."
- "The notebook has Command and Edit modes."
- "Use the mouse and keyboard to select and edit cells."
- "The notebook turns Markdown into pretty-printed documentation."
- "Markdown does most of what HTML does."
---

Python is a general-purpose programming language, i.e., it is used for
building software in many different application domains.
Software developers use either a text editor or an integrated development
environment (IDE) to create and edit their Python programs. These Python
programs can be run (executed) from the command line or through the IDE.
In this tutorial, we are going to use notebooks through JupyterLab, which is a
web-based IDE from Project Jupyter. This has several advantages:

*   You can easily type, edit, and copy-paste blocks of code.
*   With tab completion, you can easily access the names of things you are
    using and learn more about them.
*   You can annotate your code with formatted text (headings, links, bullet
    points, etc.) to make it more accessible to you and your collaborators.
*   You can display figures next to the code that produces them
    to tell a complete story of the analysis.

Because of these advantages, JupyterLab is very popular in data science, data
journalism, scientific computing, and machine learning.

Each notebook contains one or more cells, which themselves contain code, text,
(static) images, or interactive visualizations.
JupyterLab lets you work with notebooks, text files, terminals, and even
custom components in a flexible, integrated, and extensible manner.

You need a reasonably up-to-date web browser (ideally, a current version of
Chrome, Safari, or Firefox) to run JupyterLab. Note that even though
JupyterLab has a web-based interface, it can run locally on your machine,
without any internet connection:

*   The JupyterLab server sends messages to your web browser.
*   The JupyterLab server does the work and the web browser renders the result.
*   You will type code into the web interface and see the result when the web
    page talks to the JupyterLab server.

## Launching JupyterLab

You can start the JupyterLab server through the command line.
After you have opened a terminal, type the command:

~~~
$ jupyter lab
~~~
{: .bash}

And here is a screenshot of a JupyterLab landing page that should be similar
to the one that opens in your default web browser:

<p align='center'>
  <img alt="JupyterLab landing page" src="../fig/0_jupyterlab_landing_page.png" width="750"/>
</p>

## Navigating the JupyterLab Interface

JupyterLab has many features found in traditional IDEs but is focused on
providing flexible building blocks for interactive, exploratory computing.
Its [user interface](https://jupyterlab.readthedocs.io/en/stable/user/interface.html) 
consists of a menu bar, a collapsible left sidebar, and a main work area
which contains tabs of documents and activities.

### Menu Bar

Here is a screenshot of the default menu bar:

<p align='center'>
    <img alt="JupyterLab Menu Bar" src="../fig/0_jupyterlab_menu_bar.png" width="750"/>
</p>

The menu bar at the top of JupyterLab has the top-level menus that expose
various actions available in JupyterLab, along with their keyboard shortcuts
(where applicable). The following menus are included by default:

*   **File**: Actions related to files and directories such as *New*, *Open*,
    *Close*, *Save*, etc. The **File** menu also includes the *Shut Down*
    action used to shut down the JupyterLab server.
*   **Edit**: Actions related to editing documents and other activities such
    as *Undo*, *Cut*, *Copy*, *Paste*, etc.
*   **View**: Actions that alter the appearance of JupyterLab.
*   **Run**: Actions for running code in different activities such as
    notebooks and code consoles (discussed below).
*   **Kernel**: Actions for managing kernels. Kernels in Jupyter are explained
    in more detail below.
*   **Tabs**: List of the open documents and activities in the main work area.
*   **Settings**: Common JupyterLab settings can be configured using this
    menu. There is also an *Advanced Settings Editor* option in the dropdown
    menu that provides more fine-grained control of JupyterLab settings and
    configuration options.
*   **Help**: List of JupyterLab and kernel help links.

> ## Kernels
> The JupyterLab [docs](https://jupyterlab.readthedocs.io/en/stable/user/documents_kernels.html) 
> define kernels as "separate processes started by the server that run your
> code in different programming languages and environments."
> When we open a Jupyter notebook, that starts a kernel -- a process -- that
> can execute (run) the code blocks found in the notebook. 
> In this tutorial, we will be using the IPython kernel, which lets us run
> Python code interactively.
> 
> Using other Jupyter
> [kernels for other programming languages](https://github.com/jupyter/jupyter/wiki/Jupyter-kernels)
> would let us write and execute code in other programming languages (such as
> R, Java, Julia, Ruby, JavaScript, Fortran, etc.) in the same JupyterLab
> interface.
> 
{: .callout}

### Left Sidebar

Here is a screenshot of the default left sidebar:

<p align='center'>
    <img alt="JupyterLab Left Side Bar" src="../fig/0_jupyterlab_left_side_bar.png" width="250"/>
</p>

It contains a number of commonly used tabs, such as a file browser (showing
the contents of the working directory, i.e., where the JupyterLab server was
launched), a list of running kernels and terminals, the command palette, and
a list of open tabs in the main work area.
The left sidebar can be collapsed or expanded by selecting “Show Left Sidebar”
in the View menu or by clicking on the active sidebar tab.

### Main Work Area

Here is a screenshot of the default main work area:

<p align='center'>
    <img alt="JupyterLab Main Work Area" src="../fig/0_jupyterlab_main_work_area.png" width="750"/>
</p>

The main work area in JupyterLab lets you organize documents (notebooks,text
files, etc.) and other activities (terminals, code consoles, etc.) into panels
of tabs that can be resized or subdivided.
Drag a tab to the center of a tab panel to move the tab to this panel.
Subdivide a tab panel by dragging a tab to the left, right, top, or bottom of
that panel. The work area has a single current activity. The tab for the
current activity is marked with a coloured top border (blue, by default).

## Creating a Python Script

*   To start writing a new Python script, click the Text File icon under the
    *Other* header in the Launcher tab of the main work area.
    *   A Python script is a Python file that is intended to be run directly.
    *   You can also create a new plain text file by selecting
        *New > Text File* from the *File* menu in the menu bar.
*   To convert this plain text file into a Python file, select the
    *Save File As* action from the *File* menu and give your new text file a
    name ending with the `.py` extension.
    *   The `.py` file extension lets everyone (including the operating
        system) know that this text file is a Python file. This is convention,
        not a requirement.

## Creating a Jupyter Notebook

*   To open a new notebook, click the Python 3 icon under the *Notebook* header
    in the Launcher tab in the main work area.
    *   You can also create a new notebook by selecting *New > Notebook* from
        the *File* menu.
*   Notebook files have the extension `.ipynb` to distinguish them from plain
    Python files.
*   Notebooks can be exported as Python scripts that can be run from the
    command line.

Below is a screenshot of a Jupyter notebook running inside JupyterLab. If you
are interested in more details, please see the
[official documentation][jupyterlab-notebook-docs].

<p align='center'>
    <img alt="Example Jupyter Notebook" src="../fig/0_jupyterlab_notebook_screenshot.png" width="750"/>
</p>

> ## How It's Stored
>
> *   The notebook is stored in a format called JSON.
> *   This format allows Jupyter to mix source code, text, and images, all in
>     one file.
> *   Just like a web page, what's saved looks different from what you see in
>     your browser.
{: .callout}

> ## Code vs. Text
>
> Jupyter supports code and text in different types of blocks, called cells.
> By "code" we mean "the source code of software written in a programming
> language such as Python."
> A "code cell" in a notebook is a cell that contains software;
> a "text cell" is one that contains ordinary prose written for human beings.
{: .callout}

## Switching between Command and Edit Modes

*   If you press <kbd>Esc</kbd> and <kbd>Return</kbd> alternately, the outer
    border of your code cell will change from gray to blue.
*   These are the **Command** (gray) and **Edit** (blue) modes of your notebook.
*   Command mode allows you to edit notebook-level features, while Edit mode
    allows you to change the content of cells.
*   When in Command mode (<kbd>Esc</kbd>/gray):
    *   The <kbd>b</kbd> key will create a new cell below the current cell.
    *   The <kbd>a</kbd> key will create one above.
    *   The <kbd>x</kbd> key will delete the current cell.
    *   The <kbd>z</kbd> key will undo your last cell operation (which could
        be a deletion, creation, etc).
*   All actions can be done using the menus, but these keyboard shortcuts may
    help you work faster.

> ## Command vs. Edit
>
> In the Jupyter notebook, are you currently in Command or Edit mode?  
> Switch between the modes. 
> Use the shortcuts to generate a new cell. 
> Use the shortcuts to delete a cell.
> Use the shortcuts to undo the last cell operation you performed.
>
> > ## Solution
> >
> > Command mode has a grey border and Edit mode has a blue border. 
> > Use <kbd>Esc</kbd> and <kbd>Return</kbd> to switch between modes. 
> > You need to be in Command mode (Press <kbd>Esc</kbd> if your cell is blue).  Type <kbd>b</kbd> or <kbd>a</kbd>.
> > You need to be in Command mode (Press <kbd>Esc</kbd> if your cell is blue).  Type <kbd>x</kbd>.
> > You need to be in Command mode (Press <kbd>Esc</kbd> if your cell is blue).  Type <kbd>z</kbd>.
> {: .solution}
{: .challenge}

### Using the keyboard to edit and run cells

*   Pressing the <kbd>Return</kbd> key turns the border blue and engages Edit
    mode, which allows you to type within the cell.
*   Because we want to be able to write many lines of code in a single cell,
    pressing the <kbd>Return</kbd> key when in Edit mode (blue) moves the
    cursor to the next line in the cell just like in a text editor.
*   We need some other way to tell the Notebook we want to run what's in the
    cell.
*   Pressing <kbd>Shift</kbd>+<kbd>Return</kbd> together will execute the
    contents of the cell.
*   Notice that the <kbd>Return</kbd> and <kbd>Shift</kbd> keys on the right
    of the keyboard are right next to each other.

### Turning Markdown into pretty-printed documentation

*   Jupyter notebooks can also render [Markdown][markdown].
    Markdown is a simple, plain text format for writing lists, links, and
    other things that might go into a web page. Markdown does most of what
    HTML does.
*   Turn the current cell into a Markdown cell by entering the Command mode
    (<kbd>Esc</kbd>/gray) and pressing the <kbd>M</kbd> key.
*   `In [ ]:` will disappear to show it is no longer a code cell and you are
    able to write in Markdown.
*   Turn the current cell into a code cell by entering the Command mode
    (<kbd>Esc</kbd>/gray) and pressing the <kbd>y</kbd> key.

<div class="row">
  <div class="col-md-6" markdown="1">
    
~~~
*   Use asterisks
*   to create
*   bullet lists.
~~~

  </div>
  <div class="col-md-6" markdown="1">
  
*   Use asterisks
*   to create
*   bullet lists.

  </div>
</div>

<div class="row">
  <div class="col-md-6" markdown="1">
    
~~~
1.  Use numbers
1.  to create
1.  numbered lists.
~~~

  </div>
  <div class="col-md-6" markdown="1">

1.  Use numbers
1.  to create
1.  numbered lists.

  </div>
</div>

<div class="row">
  <div class="col-md-6" markdown="1">
    
~~~
*  You can use indents
	*  To create sublists 
	*  of the same type
*  Or sublists
	1. Of different
	1. types
~~~

  </div>
  <div class="col-md-6" markdown="1">
  
*  You can use indents
	*  To create sublists
	*  of the same type
*  Or sublists
	1. Of different
	1. types
  
  </div>
</div>

<div class="row">
  <div class="col-md-6" markdown="1">
    
~~~
# A Level-1 Heading
~~~

  </div>
  <div class="col-md-6" markdown="1">
  
# A Level-1 Heading

  </div>
</div>

<div class="row">
  <div class="col-md-6" markdown="1">
    
~~~
## A Level-2 Heading (etc.)
~~~

  </div>
  <div class="col-md-6" markdown="1">
  
## A Level-2 Heading (etc.)

  </div>
</div>

<div class="row">
  <div class="col-md-6" markdown="1">
    
~~~
Line breaks
don't matter.

But blank lines
create new paragraphs.
~~~

  </div>
  <div class="col-md-6" markdown="1">
  
Line breaks
don't matter.

But blank lines
create new paragraphs.

  </div>
</div>

<div class="row">
  <div class="col-md-6" markdown="1">
    
~~~
[Create links](https://software-carpentry.org) with `[...](...)`.
Or use [named links][data_carpentry].

[data_carpentry]: https://datacarpentry.org
~~~

  </div>
  <div class="col-md-6" markdown="1">
  
[Create links](https://software-carpentry.org) with `[...](...)`.
Or use [named links][data_carpentry].

[data_carpentry]: https://datacarpentry.org

  </div>
</div>

> ## Creating Lists in Markdown
>
> Create a nested list in a Markdown cell in a notebook that looks like this:
>
> 1.  Get funding.
> 2.  Do work.
>     *   Design experiment.
>     *   Collect data.
>     *   Analyze.
> 3.  Write up.
> 4.  Publish.
> 
> > ## Solution
> >
> > This challenge integrates both the numbered list and bullet list. 
> > Note that the bullet list is indented so that it is aligned with the items
> > of the numbered list.
> > ~~~
> > 1.  Get funding.
> > 2.  Do work.
> >     *   Design experiment.
> >     *   Collect data.
> >     *   Analyze.
> > 3.  Write up.
> > 4.  Publish.
> > ~~~
> {: .solution}
{: .challenge}

> ## Math
>
> What is displayed when a code cell in a notebook
> that contains several calculations is executed?
> For example, what happens when this cell is executed?
>
> ~~~
> 7 * 3
> 2 + 1
> ~~~
> {: .language-python}
> 
> > ## Solution
> >
> > Python returns the output of the last calculation.
> > ~~~
> > 3
> > ~~~
> > {: .language-python}
> {: .solution}
{: .challenge}

> ## Changing an Existing Cell from Code to Markdown
>
> What happens if you write some Python in a code cell
> and then you switch it to a Markdown cell?
> For example, put the following in a code cell:
>
> ~~~
> x = 6 * 7 + 12
> print(x)
> ~~~
> {: .language-python}
>
> And then run it with <kbd>Shift</kbd>+<kbd>Return</kbd> to be sure that it
> works as a code cell.
> Now go back to the cell and use <kbd>Esc</kbd> then <kbd>m</kbd> to switch
> the cell to Markdown; "run" it with <kbd>Shift</kbd>+<kbd>Return</kbd>.
> What happens and how might this be useful?
> 
> > ## Solution
> >
> > The Python code gets treated like Markdown text.
> > The lines appear as if they were part of one contiguous paragraph.
> > This could be useful to temporarily turn on and off cells in notebooks
> > that get used for multiple purposes. 
> > ~~~
> > x = 6 * 7 + 12 print(x)
> > ~~~
> > {: .language-python}
> {: .solution}
{: .challenge}

> ## Equations
>
> Standard Markdown (such as we're using for these notes) does not render
> equations, but the Jupyter notebook does.
> Create a new Markdown cell and enter the following:
>
> ~~~
> $\sum_{i=1}^{N} 2^{-i} \approx 1$
> ~~~
>
> (It's probably easier to copy and paste.)
> What does it display?
> What do you think the underscore, `_`, circumflex, `^`, and dollar sign, `$`, do?
> 
> > ## Solution
> >
> > The notebook shows the equation as it would be rendered from LaTeX syntax.
> > The dollar sign, `$`, is used to tell Markdown that the text in between is
> > a LaTeX equation.
> > If you're not familiar with LaTeX,  underscore, `_`, is used for
> > subscripts and circumflex, `^`, is used for superscripts.
> > A pair of curly braces, `{` and `}`, is used to group text together so
> > that the statement `i=1` becomes the subscript and `N` becomes the
> > superscript. Similarly, `-i` is in curly braces to make the whole
> > statement the superscript for `2`.
> > `\sum` and `\approx` are LaTeX commands for "sum over" and "approximate" symbols. 
> {: .solution}
{: .challenge}

## Closing JupyterLab

From the menu bar, select the *File* menu and then choose "Shut Down".
You will be prompted to confirm that you wish to shut down the JupyterLab
server (don't forget to save your work!).

To restart the JupyterLab server, you will need to run

~~~
$ jupyter lab
~~~

again from the command line.

> ## Closing JupyterLab
>
> Practice closing and restarting the JupyterLab server.
{: .challenge}
