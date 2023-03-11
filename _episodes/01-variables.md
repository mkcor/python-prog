---
title: Assigning Values to Variables
teaching: 10
exercises: 10
questions:
- "What basic data types can I work with in Python?"
- "How can I create a new variable in Python?"
- "How do I use a function?"
- "How can I change the value of a variable?"
objectives:
- "Assign values to variables."
keypoints:
- "Basic data types in Python include strings, integers, and floating-point numbers."
- "Use `variable = value` to assign a value to a variable in order to record it in memory."
- "Variables are created on demand whenever a value is assigned to them."
- "Use `print(something)` to display the value of `something`."
- "Built-in functions are always available to use."
---

## Types of data

Python knows various types of data. Three common ones are:

* integer numbers,
* floating-point numbers, and
* character strings.

We can use Python as a calculator:

~~~
3 + 5 * 4
~~~
{: .language-python}
~~~
23
~~~
{: .output}

~~~
4.5 / 1.5
~~~
{: .language-python}
~~~
3.0
~~~
{: .output}

To create a string, we add single or double quotes around some text:

~~~
"hello"
~~~
{: .language-python}
~~~
'hello'
~~~
{: .output}

## Creating Variables

This is great but not very interesting.
To do anything useful with data, we need to assign its value to a _variable_.
In Python, we use the equals sign `=` to assign a value (on the right) to a
variable (on the left). The variable is created when a value is assigned to
it.
For example, we can track the weight of a patient who weighs 60.3 kilograms by
assigning the value `60.3` to a variable `weight_kg`:

~~~
weight_kg = 60.3
~~~
{: .language-python}

From now on, whenever we use `weight_kg`, Python will substitute the value we
assigned to it. In layperson's terms, **a variable is a name for a value**.

To identify and track a patient, we can assign them a unique identifier by
storing it in a string:

~~~
patient_id = '001'
~~~
{: .language-python}

In Python, variable names:

 - can include letters, digits, and underscores;
 - cannot start with a digit;
 - are case-sensitive.

This means that, for example:
 - `weight0` is a valid variable name, whereas `0weight` is not;
 - `weight` and `Weight` are different variables.

## Using Variables in Python

Once we have data stored in variables, we can make use of it in calculations.
We may be interested in our patient's weight in pounds:

~~~
# There are 2.2 pounds per kilogram
2.2 * weight_kg
~~~
{: .language-python}
~~~
132.66
~~~
{: .output}

We might decide to add a prefix to our patient identifier:

~~~
patient_id = 'inflam_' + patient_id
~~~
{: .language-python}

Variables must be created before they are used.

## Using Built-in Functions

To carry out common tasks with data and variables in Python,
the language provides us with several built-in functions.
To display information to the screen, we use the `print` function:

~~~
print(weight_lb)
print(patient_id)
~~~
{: .language-python}
~~~
132.66
inflam_001
~~~
{: .output}

When we want to make use of a function, which is referred to as _calling_ a
function, we follow its name by parentheses. The parentheses are important:
If you leave them off, the function doesn't actually run:

~~~
print
~~~
{: .language-python}
~~~
<built-in function print>
~~~
{: .output}

Note that this doesn't cause an error; it just prints out a description of the
`print` object in Python.

Sometimes we will include values or variables inside the parentheses.
In the case of `print`, we include what we want to display.

~~~
print("hello")
print("3")
print(3)
~~~
{: .language-python}
~~~
hello
3
3
~~~
{: .output}

We will learn more about how functions work and how to create our own in a
later episode.

We can display multiple things at once using only one `print` call:

~~~
print(patient_id, 'weight in kilograms:', weight_kg)
~~~
{: .language-python}
~~~
inflam_001 weight in kilograms: 60.3
~~~
{: .output}

> ## Using Formatted String Literals
>
> An alternative way of printing the above is to use formatted string
> literals, which make formatting easier. Also known as "f-strings," they
> start with an `f` and they contain variables inside of curly braces:
>
> ~~~
> print(f"{patient_id} weight in kilograms: {weight_kg}")
> ~~~
> {: .language-python}
> ~~~
> inflam_001 weight in kilograms: 60.3
> ~~~
> {: .output}
{: .callout}

We can also call a function inside of another function call.
For example, Python has a built-in function called `type` that tells us a
value's data type:

~~~
print(type(60.3))
print(type(patient_id))
~~~
{: .language-python}

~~~
<class 'float'>
<class 'str'>
~~~
{: .output}

Another common built-in function is `len`: It is used to find the length of a
character string:

~~~
print(len("hello"))
print(len('weight in pounds:'))
~~~
{: .language-python}
~~~
5
17
~~~
{: .output}

Moreover, we can do arithmetic with variables right inside the `print` call:

~~~
print('weight in pounds:', 2.2 * weight_kg)
~~~
{: .language-python}
~~~
weight in pounds: 132.66
~~~
{: .output}

## Changing the Value of Variables

The above command did not change the value of `weight_kg`:

~~~
print(weight_kg)
~~~
{: .language-python}
~~~
60.3
~~~
{: .output}

To change the value of the `weight_kg` variable, we have to _assign_
`weight_kg` a new value using the equals `=` sign:

~~~
weight_kg = 65.0
print('weight in kilograms is now:', weight_kg)
~~~
{: .language-python}
~~~
weight in kilograms is now: 65.0
~~~
{: .output}

> ## Variables as Sticky Notes
>
> A variable in Python is analogous to a sticky note with a name written on
> it: Assigning a value to a variable is like putting that sticky note on a
> particular value.
>
> ![Value of 65.0 with weight_kg label stuck on it](../fig/python-sticky-note-variables-01.svg)
>
> Using this analogy, we can investigate how assigning a value to one variable
> does **not** change values of other, seemingly related, variables. For
> example, let us store the patient's weight in pounds in its own variable:
>
> ~~~
> weight_lb = 2.2 * weight_kg
> print('weight in kilograms:', weight_kg, 'and in pounds:', weight_lb)
> ~~~
> {: .language-python}
> ~~~
> weight in kilograms: 65.0 and in pounds: 143.0
> ~~~
> {: .output}
>
> ![Value of 65.0 with weight_kg label stuck on it, and value of 143.0 with weight_lb label
stuck on it](../fig/python-sticky-note-variables-02.svg)
>
> The expression `2.2 * weight_kg` is evaluated to `143.0`, and
> then this value is assigned to the variable `weight_lb` (i.e., the sticky
> note `weight_lb` is placed on `143.0`). At this point, each variable is
> "stuck" to completely distinct and unrelated values.
>
> Let us now change `weight_kg`:
>
> ~~~
> weight_kg = 100.0
> print('weight in kilograms is now:', weight_kg, 'and weight in pounds is still:', weight_lb)
> ~~~
> {: .language-python}
> ~~~
> weight in kilograms is now: 100.0 and weight in pounds is still: 143.0
> ~~~
> {: .output}
>
> ![Value of 100.0 with label weight_kg stuck on it, and value of 143.0 with label weight_lb
stuck on it](../fig/python-sticky-note-variables-03.svg)
>
> Since `weight_lb` doesn't "remember" where its value comes from,
> it is not updated when we change `weight_kg`.
{: .callout}


> ## Check Your Understanding
>
> What values do the variables `mass` and `age` have after each of the following statements?
> Test your answer by executing the lines.
>
> ~~~
> mass = 47.5
> age = 122
> mass = mass * 2.0
> age = age - 20
> ~~~
> {: .language-python}
>
> > ## Solution
> > ~~~
> > `mass` holds a value of 47.5, `age` does not exist
> > `mass` still holds a value of 47.5, `age` holds a value of 122
> > `mass` now has a value of 95.0, `age`'s value is still 122
> > `mass` still has a value of 95.0, `age` now holds 102
> > ~~~
> > {: .output}
> {: .solution}
{: .challenge}

> ## Sorting Out References
>
> Python allows you to assign multiple values to multiple variables in one line by separating
> the variables and values with commas. What does the following program print out?
>
> ~~~
> first, second = 'Grace', 'Hopper'
> third, fourth = second, first
> print(third, fourth)
> ~~~
> {: .language-python}
>
> > ## Solution
> > ~~~
> > Hopper Grace
> > ~~~
> > {: .output}
> {: .solution}
{: .challenge}

> ## Seeing Data Types
>
> What are the data types of the following variables?
>
> ~~~
> planet = 'Earth'
> apples = 5
> distance = 10.5
> ~~~
> {: .language-python}
>
> > ## Solution
> > ~~~
> > print(type(planet))
> > print(type(apples))
> > print(type(distance))
> > ~~~
> > {: .language-python}
> >
> > ~~~
> > <class 'str'>
> > <class 'int'>
> > <class 'float'>
> > ~~~
> > {: .output}
> {: .solution}
{: .challenge}
