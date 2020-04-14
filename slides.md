---
title: 'Class 4: Chapter 10: Lists'
separator: '\-\-\-\-\-'
verticalSeparator: '\+\+\+\+\+'
theme: 'moon'
revealOptions:
    transition: 'fade'
---

### ITSE-1402 Intermediate Python
<span style="font-family:Helvetica Neue; font-weight:bold; color:#e49436">Class 4: Chapter 10: Lists</span>
<br /><br />
##### [https://bit.ly/1402-class4](https://bit.ly/1402-class4)

-----

##### Chapter 10: Lists

+++++

A list in python is similar to a string. It's a sequence of values. 

+++++

The difference between strings and lists is that the string requires them to be characters:

```python
a = "this is a string of characters"
```
+++++

Whereas a list can be anything and starts with a '[' and ends with a '[]':

```python
a = ['a', list, 0, ['any','little','thing'], you[0], can["think"], "of", True]
```
Note:
Values are separated by commas. 
As you can see, you can have a list inside a list. This is called a nested list.

+++++

You also may find that you need to create a new list that is empty:

```python
a = []
```

+++++

You then can add items to it.

```python
a = []
a.append("item")
# a = ["item"]
```

Note:
We'll talk about methods more in a bit

+++++

Lists in python are mutable and you can do all kinds of odd things with them because of it (as well as some expected things).

```python
numbers = [1,2,3]
secondNum = number[1]
numbers = [numbers[0],numbers[2]]
otherSecondNum = numbers.pop(1)
# numbers = [1]
```

Note:
Meaning muttable objects can be changed in place after assignment or initialization, while an immutable object cannot.
Examples of immutable data types or objects or variables in Python are numbers (integers, floats), strings and tuples.
We can start with a pretty normal list of numbers. Lets say we only wanted the second one.
We then can remove the number by redefining the list, but there is a better way to do this. 
Pop is the method to do this. It removes it from the list and assigns it to what you choose.

+++++

We saw this last chapter, but you can also traverse lists.

```python
cheeses = ["havarti", "cheddar", "american", "gouda"]
for cheese in cheeses:
    print(cheese)
# havarti
# ...
# gouda
```

+++++

There are other ways to do this as well.

```python
cheeses = ["havarti", "cheddar", "american", "gouda"]
for i in range(len(cheeses)):
    print(cheeses[i])
# havarti
# ...
# gouda
```

Note: Range creates a new interable with numbers from zero up to the number you specify.

+++++

If you traverse and empty list, nothing will happen.

```python
for x in []:
    print("This will never happen.")
```

+++++

Although you can have nested lists, if you pull the list out of the list, it's still a list. 

```python
a = ['a', list, 0, ['any','little','thing'], you[0], can["think"], "of", True]
print(a[3])
# ['any','little','thing']
print(a[3][1])
# 'little'
```

+++++

There are also two operations you can do to lists. Add and multiply.

```python
a = [1,2,3]
b = [4,5,6]
c = a + b
# c = [1,2,3,4,5,6]
d = a * 4
# d = [1,2,3,1,2,3,1,2,3,1,2,3]
```

+++++

Just like strings, you can also slice lists.

```python
c = [1,2,3,4,5,6]
a = c[:2]
# a = [1,2,3]
b = c[3:]
# b = [4,5,6]
e = c[:]
# e = [1,2,3,4,5,6]
```

+++++

What about list methods. We know about pop... what else is there?

```python
t = ['a','b','c']
t.append('d')
# t = ['a','b','c','d']
u = ['f','e']
t.extend[u]
# t = ['a','b','c','d','f','e']
t.sort()
# # t = ['a','b','c','d','e','f']
```

+++++

Something to keep in mind: most methods modify the referenced list and return None.

```python
y = t.sort()
# y = None
```

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# Exercise 10.5
#
# Grading Guidelines:
# - No answer variable is needed. Grading script will call function.
# - Function "is_sorted" should return True if list is sorted ascending
# or False if otherwise.
#
# 1. Write a function called is_sorted that takes a list as a parameter and 
# returns True if the list is sorted in ascending order and False otherwise. 
# For example:
#
# >>> is_sorted([1, 2, 2])
# True
# >>> is_sorted(['b','a'])
# False
#
</code></pre>


+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# Exercise 10.6
#
# Grading Guidelines:
# - No answer variable is needed. Grading script will call function.
# - Function "is_anagram" should return True if a word is an anagram
# or False if not.
#
# 1. Two words are anagrams if you can re-arrange the letters from one to spell
# the other. Write a function "is_anagram" that takes two strings and returns
# True if they are anagrams. 
#
</code></pre>


+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# Exercise 10.7
#
# Grading Guidelines:
# - No answer variable is needed. Grading script will call function.
# - Function "has_duplicates" should return True if a list has duplicates
# or False if not.
#
# 1. Write a function called has_duplicates that takes a list and returns True
# if there is any element that appears more than once. It should not modify the
# original list.
#
</code></pre>


+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# Exercise 10.9
#
# Grading Guidelines:
# - No answer variable is needed. Grading script will call function.
# - Function "version1" and "version2" should both return a list with all words
# in words.txt
# 
# 1. Write a function named "version1" that reads the file words.txt 
# and builds a list with one element per word. Write a second version
# of this function named "version2" using the idiom t = t + [x]. Which 
# one takes longer to run? Why?
#
</code></pre>


+++++

Another thing you might want to do with a list is add all the numbers together.

```python
a = [1,2,3]

def add_all(num):
    total = 0
    for x in num:
        total += x     # total = x + total
    return total
x = add_all(a)
# x = 6
```

Note:
This is called sometimes an accumulator.

+++++

This is a common function so python actually has a built-in function to do it.

```python
a = [1,2,3]

x = sum(a)
# x = 6
```

Note:
An operation that reduces multiple list items to a single item us sometimes called reduce

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# Exercise 10.1
#
#
# Grading Guidelines:
# - No answer variable is needed. Grading script will call function.
# - Function "nested_sum" should output a integer that is a sum of all integers
# in the nested lists.
#
# 1. Write a function called nested_sum that takes a list of lists of integers 
# and adds up the elements from all of the nested lists. For example:
#
# >>> t = [[1, 2], [3], [4, 5, 6]]
# >>> nested_sum(t)
# 21
#
</code></pre>

+++++

Sometimes you want to traverse a list and make a new one concurrently.

```python
def capitalize_all(t):
    res = []
    for s in t:
        res.append(s.capitalize())
    return res
```

Note:
Because this starts with an empty list and adds to it, it can also be called an accumulator.
This could be called a map as well because it maps the .capitalize method on each of the elements

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# Exercise 10.2
#
# Grading Guidelines:
# - No answer variable is needed. Grading script will call function.
# - Function "cum_sum" should output a list of integers that is a stepping 
# cumlative sum of all integers in the nested lists.
#
# 1. Write a function called cum_sum that takes a list of numbers and returns the
# cumulative sum; that is, a new list where the ith element is the sum of the 
# first i + 1 elements from the original list. For example:
# 
# >>> t = [1, 2, 3]
# >>> cumsum(t)
# [1, 3, 6]
#
</code></pre>


+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# Exercise 10.3
#
# Grading Guidelines:
# - No answer variable is needed. Grading script will call function.
# - Function "middle" should output all list elements, but first and last. 
#
# 1. Write a function called middle that takes a list and returns a new list 
# that contains all but the first and last elements. For example:
#
# >>> t = [1, 2, 3, 4]
# >>> middle(t)
# [2, 3]
#
</code></pre>


+++++

You can do similar and return a sublist instead of all the contents:

```python
def only_upper(t):
    res = []
    for s in t:
        if s.isupper():
            res.append(s)
    return res
```

+++++

It also is possible to remove elements from a list. We've seen pop() which will remove, but there are other ways to do it that do not return anything.

```python
t = ['a', 'b', 'c']
del t[1]       # if you know the index
# t = ['a','c']
t.remove('c')  # if you know the value
```
+++++

You can also remove a multiple items with a slice.

```python
t = ['a', 'b', 'c', 'd', 'e', 'f']
del t[1:5]
# t = ['a', 'f']
```

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# Exercise 10.4
#
# Grading Guidelines:
# - No answer variable is needed. Grading script will call function.
# - Function "chop" should remove first and last element in-place. 
#
# 1. Write a function called chop that takes a list, modifies it by removing the
# first and last elements, and returns None. For example:
#
# >>> t = [1, 2, 3, 4]
# >>> chop(t)
# >>> t
# [2, 3]
#
</code></pre>


+++++

We talked earlier that a string is a sequence of characters. If we want this to be a list, there a few easy ways to do so depending on what result you want.

```python
s = 'spam'
t = list(s)
# t = ['s','p','a','m']
```

+++++

list breaks the string down to characters. If you want to convert to words, you can use split().

```python
s = 'I like spam'
t = s.split()
# t = ['I', 'like', 'spam']
```

+++++

By default split() uses space as a delimiter, but you can specify anything you wish.

```python
s = 'I-like-spam'
t = s.split('-')
# t = ['I', 'like', 'spam']
```

+++++

There is also the inverse of split(), join()

```python
s = ['I', 'like', 'spam']
t = s.join()
# t = 'I like spam'   # by default, it uses spaces as the delimiter
u = s.join('-')
# t = 'I-like-spam'   # you can change it the same way as split()
```

+++++

Some logic that might throw you off lies in the memory assignment of variables.

```python
a = 'banana'
b = 'banana'
print(a is b)       # is operator compares the objects and not the values
# True              a is the same object as b

a = [1,2,3]
b = [1,2,3]
print(a is b)
# False             a is not the same object as b
```

Note:
Python tries to be smart with memory management. If the string values are the same, they will be the same object until changed.
With lists, the list will be a different object.

+++++

This leads us to aliasing. Aliasing is not much of a problem with strings, but with lists, it can definitely be.

```python
a = [1,2,3]
b = a        # creates an alias to a
print(a is b)
# True
```

Note:
This object is called a reference. If the referenced object is mutable, changes to one will make changes to another. 

+++++

Along the same lines as above, when you pass a list to a function, it will send a reference to the list. The list will then be modified as the reference is modified.

```python
def delete_head(t):
    del t[0]
    
letters = ['a','b','c']
delete_head(letters)
# letters = ['b','c']
```

+++++

There is also a bad way to do this.

```python
def bad_delete_head(t):
    t = t[1:]
    
letters = ['a','b','c']
bad_delete_head(letters)
# letters = ['a','b','c']
```

Note:
you are making a new t in the fuction and it is removing the reference.

+++++

You can use this to your advantage if you don't want to modify the existing list.

```python
def tail(t):
    return t[1:]
letters = ['a','b','c']
rest = tail(letters)
print(letters)
# ['a','b','c']
print(rest)
# [b','c']
```

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# Exercise 10.10
#
# Grading Guidelines:
# - No answer variable is needed. Grading script will call function.
# - Function "in_bisect" should return the index in list where the word was
# found
# 
# 1. To check whether a word is in the word list, you could use the in operator,
# but it would be slow because it searches through the words in order. Because 
# the words are in alphabetical order, we can speed things up with a bisection 
# search (also known as binary search), which is similar to what you do when you
# look a word up in the dictionary. You start in the middle and check to see 
# whether the word you are looking for comes before the word in the middle of 
# the list. If so, you search the first half of the list the same way. Otherwise
# you search the second half.
# 
# Either way, you cut the remaining search space in half. If the word list has
# 113,809 words, it will take about 17 steps to find the word or conclude that
# it's not there.
#
# Write a function called in_bisect that takes a sorted list and a target value
# and returns the index of the value in the list if it's there, or None if it's 
# not.
#
</code></pre>

+++++

Exercise 10.11 and 10.12 are homework.
