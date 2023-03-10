---
title: "Repeating Actions with Loops"
teaching: 5
exercises: 5
questions:
- "How can I make a program do many things?"
objectives:
- "Explain what a `for` loop does."
- "Correctly write `for` loops to repeat simple calculations."
- "Trace changes to every variable as the loop runs."
keypoints:
- "Use `for variable in sequence:` to process the elements of a sequence one at a time."
- "The loop variable can be called anything, but it is strongly advised to use a meaningful name."
- "The body of a `for` loop must be indented."
- "Use `range` to iterate over a sequence of numbers."
---

## Executing Commands once for each Value in a Sequence

A `for` loop tells Python to execute some instructions once for each value in
a list, a character string, or some other sequence:

~~~
for number in [1, 3, 5, 7]:
    print(number)
~~~
{: .language-python}
~~~
1
3
5
7
~~~
{: .output}

This `for` loop is equivalent to:

~~~
print(1)
print(3)
print(5)
print(7)
~~~
{: .language-python}

Likewise, we can run:

~~~
for letter in 'hon':
    print(letter)
~~~
{: .language-python}
~~~
h
o
n
~~~
{: .output}

* The sequence (above, `'hon'`) is what the loop is being run on.
* The body (above, `print(letter)`) specifies what to do for each value in the
  sequence.
* The loop variable (above, `letter`) is what changes for each *iteration* of
  the loop.

> ## What's in a Name?
>
> In the examples above, the loop variable was given the names `number` and
> `letter`, respectively, as a mnemonic.
> We can choose any name we want for variables. We might just as easily have
> chosen the name `banana` for the loop variable, as long as we use the same
> name when we invoke the variable inside the loop:
>
> ~~~
> odds = [1, 3, 5, 7]
> for banana in odds:
>     print(banana)
> ~~~
> {: .language-python}
> ~~~
> 1
> 3
> 5
> 7
> ~~~
> {: .output}
>
> It is a good idea to choose variable names that are meaningful, otherwise it
> would be more difficult to understand what the loop is doing.
{: .callout}

## Using the Right Syntax

* The colon at the end of the first line signals the start of a *block* of
  (many) instructions.
* Python uses indentation (rather than `{}` or `begin`/`end`) to mean
  _nesting_.
* Any consistent indentation is legal, but almost everyone uses four spaces.

> ## Tracing Execution
>
> Create a table showing the numbers of the lines that are executed when this
> program runs, and the values of the variables after each line is executed.
>
> ~~~
> total = 0
> for char in "tin":
>     total = total + 1
> ~~~
> {: .language-python}
> > ## Solution
> >
> > | Line no | Variables             |
> > |---------|-----------------------|
> > | 1       | total = 0             |
> > | 2       | total = 0, char = 't' |
> > | 3       | total = 1, char = 't' |
> > | 2       | total = 1, char = 'i' |
> > | 3       | total = 2, char = 'i' |
> > | 2       | total = 2, char = 'n' |
> > | 3       | total = 3, char = 'n' |
> {: .solution}
{: .challenge}

> ## From 1 to N
>
> Python has a built-in function called `range` that generates a sequence of
> numbers. `range` accepts 1, 2, or 3 parameters.
>
> * If one parameter is given, `range` generates a sequence of that length,
>   starting at zero and incrementing by 1.
>   For example, `range(3)` produces the numbers `0, 1, 2`.
> * If two parameters are given, `range` starts at the first and ends just
>   before the second, incrementing by one.
>   For example, `range(2, 5)` produces `2, 3, 4`.
> * If three parameters are given, `range` starts at the first one, ends just
>   before the second one, and increments by the third one.
>   For example, `range(3, 10, 2)` produces `3, 5, 7, 9`.
>
> Note that `range(N)` is not a list: The numbers are produced on demand to
> make looping over large ranges more efficient.
>
> How does `range(len(odds))` relate with the indices of `odds`?
>
> > ## Solution
> > `range(len(odds))` gives exactly the indices of `odds` (if `odds` is a
> > list or a string).
> {: .solution}
{: .challenge}

## Using the Accumulator Pattern

A common pattern in programs is to:
    1.  Initialize an *accumulator* variable to zero, the empty string, or the
    empty list.
    2.  Update the variable with values from a sequence.

~~~
# Sum the first 4 integers.
total = 0

for number in range(1, 5):
   total = total + number

print(total)
~~~
{: .language-python}
~~~
10
~~~
{: .output}

> ## Reversing a String
>
> Fill in the blanks in the program below so that it prints "nit"
> (the reverse of the original character string "tin").
>
> ~~~
> original = "tin"
> result = ...
> for char in original:
>     result = ...
> print(result)
> ~~~
> {: .language-python}
> > ## Solution
> > ~~~
> > original = "tin"
> > result = ""
> > for char in original:
> >     result = char + result
> > print(result)
> > ~~~
> > {: .language-python}
> {: .solution}
{: .challenge}

> ## Doing Calculations for many Patients
>
> Given this nested list where the first position contains patient identifiers
> and the second position, their respective weights:
>
> ~~~
> weights_kg = [['inflam_001', 'inflam_002', 'inflam_003'],
>               [60.3, 65.2, 55.5]]
> ~~~
> {: .language-python}
>
> For each patient, print their identifier followed by their weight in pounds.
>
> > ## Solution
> > ~~~
> > for i in range(len(weights_kg[0])):
> >     weight_lb = 2.2 * weights_kg[1][i]
> >     print(f"Patient {weights_kg[0][i]} weighs {weight_lb:.2f} pounds.")
> > ~~~
> > {: .language-python}
> > ~~~
> > Patient inflam_001 weighs 132.66 pounds.
> > Patient inflam_002 weighs 143.44 pounds.
> > Patient inflam_003 weighs 122.10 pounds.
> > ~~~
> > {: .output}
> {: .solution}
{: .challenge}
