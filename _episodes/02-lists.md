---
title: Storing Multiple Values in Lists
teaching: 15
exercises: 5
questions:
- "How can I store many values together?"
objectives:
- "Explain what a list is."
- "Create lists."
- "Index and slice lists."
- "Change the value of individual elements."
- "Append new elements to an existing list."
- "Create and manipulate nested lists."
keypoints:
- "`[value1, value2, value3, ...]` creates a list."
- "Lists can contain any Python object, including lists (i.e., nested lists)."
- "Lists are indexed and sliced with square brackets (e.g., `list[0]` and
`list[2:9]`, respectively), in the same way as strings and arrays."
- "Lists are mutable (i.e., their values can be changed in-place)."
- "Strings are immutable (i.e., the characters in them cannot be changed)."
---

Doing calculations for a hundred patients (e.g., converting their weight from
kilograms to pounds) would be as slow as doing them by hand. To store many
values together, we use a _list_.

## Creating Lists

We create a list by putting values inside square brackets and separating the
values with commas:

~~~
odds = [1, 3, 5, 7]
print('odds are:', odds)
~~~
{: .language-python}
~~~
odds are: [1, 3, 5, 7]
~~~
{: .output}

Just like for character strings, we use `len` to find out how many _elements_
are in a list:

~~~
print('length:', len(odds))
~~~
{: .language-python}
~~~
length: 4
~~~
{: .output}

## Accessing Elements

In the above list, the first element has a value of `1` and the last element,
a value of `7`. To access an element, we use its index, i.e., its numbered
position in the list. Indices are numbered starting at 0, so the first element
has an index of 0.

~~~
print('first element:', odds[0])
print('last element:', odds[3])
print('"-1" element:', odds[-1])
~~~
{: .language-python}
~~~
first element: 1
last element: 7
"-1" element: 7
~~~
{: .output}

Yes, we can use negative numbers as indices in Python. When we do so, index
`-1` gives us the last element, `-2` the second to last, and so on.
Because of this, `odds[3]` and `odds[-1]` point to the same element here.

Likewise, we can access elements of a character string by indexing:

~~~
print('hello'[0])
print('hello'[4])
patient_id = 'inflam_001'
print(patient_id[1])
~~~
{: .language-python}
~~~
h
o
n
~~~
{: .output}

## Changing the Value of Elements in a List

We can change the value of an element by assigning it a new value:

~~~
odds[3] = 9
print('odds are now:', odds)
~~~
{: .language-python}
~~~
odds are now: [1, 3, 5, 9]
~~~
{: .output}

There is one important difference between lists and strings:
We can change the values in a list,
but we cannot change individual characters in a string.

~~~
name = 'Darwin'
name[0] = 'd'
~~~
{: .language-python}
~~~
---------------------------------------------------------------------------
TypeError                                 Traceback (most recent call last)
<ipython-input-8-220df48aeb2e> in <module>()
      1 name = 'Darwin'
----> 2 name[0] = 'd'

TypeError: 'str' object does not support item assignment
~~~
{: .error}

> ## Ch-Ch-Changes
>
> Data which can be modified in-place is called _mutable_,
> while data which cannot be modified is called _immutable_.
> Strings and numbers are immutable. This does not mean that variables with
> string or number values are constants, but when we want to change the value
> of a variable with type string or number, we can only
> replace the old value with a completely new value.
>
> Lists and arrays, on the other hand, are mutable: We can modify them after
> they have been created. We can change individual elements, append new
> elements, or reorder the whole list. For some operations, like sorting, we
> can choose whether to use a function that modifies the data in-place or a
> function that returns a modified copy and leaves the original unchanged.
>
> Be careful when modifying data in-place. If two variables refer to the same
> list, and you modify the list value, it will change for both variables!
>
> ~~~
> other_odds = odds  # other_odds and odds point to the same data in memory 
> odds[0] = 2
> print('other_odds are:', other_odds)
> ~~~
> {: .language-python}
> ~~~
> other_odds are: [2, 3, 5, 9]
> ~~~
> {: .output}
>
> If you want variables with mutable data to be independent, you
> must make a copy of the data when you assign it:
>
> ~~~
> odds = [1, 3, 5, 7]
> odds_copy = list(odds)  # makes a copy of the list
> odds[0] = 2
> print('odds_copy are still:', odds_copy)
> ~~~
> {: .language-python}
> ~~~
> odds_copy are still: [1, 3, 5, 7]
> ~~~
> {: .output}
>
> Because of pitfalls like this, code which modifies data in-place can be more
> difficult to understand. However, it is often far more efficient to modify a
> large data structure in-place than to create a modified copy for every small
> change. You should consider both of these aspects when writing your code.
{: .callout}

Lists in Python can contain elements of different types.
~~~
odds[0] = 'Unknown'
print('odds is now a heterogeneous list:', odds)
~~~
{: .language-python}
~~~
odds is now a heterogeneous list: ['Unknown', 3, 5, 7]
~~~
{: .output}

Therefore, they can even contain other lists: These are _nested lists_.
For example, we could represent the products on the shelves of a small grocery
shop as follows:

~~~
foods = [['pepper', 'salt'],
         ['cabbage', 'lettuce', 'leek'],
         ['apple', 'pear', 'banana']]
print('There are', len(foods), 'shelves.')
print('There are', len(foods[1]), 'kinds of vegetables.')
print('seasoning:', foods[0])
print('"first" seasoning:', foods[0][0])
~~~
{: .language-python}
~~~
There are 3 shelves.
There are 3 kinds of vegetables.
seasoning: ['pepper', 'salt']
"first" seasoning: pepper
~~~
{: .output}

Here is a visual example of how indexing a list of lists `x` works:

![`x` is represented as a pepper shaker containing several packets of pepper.
`x[0]` is represented as a single packet of pepper.
`[x[0]]` would then be represented as a pepper shaker containing a single packet
of pepper. `x[0][0]` is represented as single grain of pepper.
Adapted from Hadley Wickham.](../fig/indexing_lists_python.png)

## Working with Lists

There are many ways to change the contents of lists besides assigning new
values to individual elements. We may add an element to the end of a list:

~~~
odds = [1, 3, 5, 7]
odds.append(9)
print('odds after appending a value:', odds)
~~~
{: .language-python}
~~~
odds after appending a value: [1, 3, 5, 7, 9]
~~~
{: .output}

We may remove it:
~~~
odds.pop()
~~~
{: .language-python}
~~~
9
~~~
{: .output}

We may reverse the order of the list:
~~~
odds.reverse()
print('odds after reversing:', odds)
~~~
{: .language-python}
~~~
odds after reversing: [7, 5, 3, 1]
~~~
{: .output}

And sort it again:
~~~
odds.sort()
print('odds after sorting:', odds)
~~~
{: .language-python}
~~~
odds after sorting: [1, 3, 5, 7]
~~~
{: .output}

While modifying in-place, it is useful to remember that Python treats lists in
a slightly counter-intuitive way.

~~~
odds.pop(0)
primes = odds
primes.append(2)
print('primes:', primes)
print('odds:', odds)
~~~
{: .language-python}
~~~
primes: [3, 5, 7, 2]
odds: [3, 5, 7, 2]
~~~
{: .output}

This is because Python stores a list in memory, and then can use multiple
names to refer to the same list. If all we want to do is copy a (simple) list,
we can again use the `list` function, so we do not modify a list we did not
mean to:

~~~
odds = [3, 5, 7]
primes = list(odds)
primes.append(2)
print('primes:', primes)
print('odds:', odds)
~~~
{: .language-python}
~~~
primes: [3, 5, 7, 2]
odds: [3, 5, 7]
~~~
{: .output}

Subsets of lists and strings can be accessed by specifying ranges of values in
square brackets. This is commonly referred to as _slicing_.

~~~
binomial_name = 'Drosophila melanogaster'
group = binomial_name[0:10]
print('group:', group)

species = binomial_name[11:23]
print('species:', species)

chromosomes = ['X', 'Y', '2', '3', '4']
autosomes = chromosomes[2:5]
print('autosomes:', autosomes)

last = chromosomes[-1]
print('last:', last)
~~~
{: .language-python}
~~~
group: Drosophila
species: melanogaster
autosomes: ['2', '3', '4']
last: 4
~~~
{: .output}

> ## Slicing From the End
>
> Use slicing to access only the last four characters of a string and the last
> four entries of a list.
>
> ~~~
> string_for_slicing = 'Observation date: 02-Feb-2013'
> list_for_slicing = [['fluorine', 'F'],
>                     ['chlorine', 'Cl'],
>                     ['bromine', 'Br'],
>                     ['iodine', 'I'],
>                     ['astatine', 'At']]
> ~~~
> {: .language-python}
> ~~~
> '2013'
> [['chlorine', 'Cl'], ['bromine', 'Br'], ['iodine', 'I'], ['astatine', 'At']]
> ~~~
> {: .output}
>
> Would your solution work regardless of whether you knew beforehand the
> length of the string or list (e.g., if you wanted to apply the solution to a
> set of lists of different lengths)?
> If not, try to change your approach to make it more robust.
>
> Hint: Remember that indices can be negative as well as positive.
>
> > ## Solution
> > Use negative indices to count elements from the end of a container (such as list or string):
> >
> > ~~~
> > string_for_slicing[-4:]
> > list_for_slicing[-4:]
> > ~~~
> > {: .language-python}
> {: .solution}
{: .challenge}

> ## Overloading
>
> `+` usually means addition, but when used on strings or lists, it means
> "concatenate". Try it out!
> Given that, what do you think the multiplication operator `*` does on lists?
> In particular, what will be the output of the following code?
>
> ~~~
> counts = [2, 4, 6, 8, 10]
> repeats = counts * 2
> print(repeats)
> ~~~
> {: .language-python}
>
> 1.  `[[2, 4, 6, 8, 10],[2, 4, 6, 8, 10]]`
> 2.  `[4, 8, 12, 16, 20]`
> 3.  `[2, 4, 6, 8, 10, 2, 4, 6, 8, 10]`
> 4.  `[2, 4, 6, 8, 10, 4, 8, 12, 16, 20]`
>
> The technical term for this is *operator overloading*:
> a single operator, like `+` or `*`,
> can do different things depending on what it's applied to.
>
> > ## Solution
> >
> > The multiplication operator `*` used on a list replicates elements of the
> > list and concatenates them together:
> >
> > ~~~
> > [2, 4, 6, 8, 10, 2, 4, 6, 8, 10]
> > ~~~
> > {: .output}
> >
> > It's equivalent to:
> >
> > ~~~
> > counts + counts
> > ~~~
> > {: .language-python}
> {: .solution}
{: .challenge}
