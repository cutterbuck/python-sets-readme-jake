# Introduction to Sets

Say you are writing an algorithm to determine whether an incoming email ought to be placed in your inbox or in your spam folder. You need to collect all of the unique words that appear in your your regular emails and your spam emails then check how often these words appear in each category. If the incoming email contains the words "free" and "consultation" and these words appear more often in spam than in regular messages, you know this email should be sent to your spam folder.

A **set** is a type of data collection that is useful for such a task. They are handy whenever you need to collect only unique elements from a large collection. You saw how to use a set in the **Instant Data Science** lesson to remove duplicate words from the list of “Barbara Ann” song lyrics.

Sets are much like lists, but with three key differences:


### 1) Sets remove duplicate elements

```python
all_letters = list("Mississippi")
unique_letters = set("Mississippi")
```

```python
all_letters
Out: ['M', 'i', 's', 's', 'i', 's', 's', 'i', 'p', 'p', 'i']
```

```python
unique_letters
Out: {'M', 'i', 'p', 's'}
```

A list contains all of the characters, whereas a set collects each character only once.


### 2) Individual elements are immutable

Although a set can be operated upon, its constituent elements cannot be changed. For example, you cannot make a set of lists as elements because lists are changeable objects. The code below produces a TypeError:

```python
teams = set((["Yankees", "Red Sox", "Blue Jays"], ["Mets", "Phillies", "Nationals"]))
```

However, you can make a set of tuples since tuples are immutable. Think of tuples as lists that cannot be altered. They are created with parentheses () instead of square brackets [].

```python
teams = set((("Yankees", "Red Sox", "Blue Jays"), ("Mets", "Phillies", "Nationals")))

teams
Out: {('Mets', 'Phillies', 'Nationals'), ('Yankees', 'Red Sox', 'Blue Jays')}
```




### 3) Items in the collection are unordered

Elements of a set do not have order, therefore using an index to select an element produces a TypeError:

```python
teams[1]
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-106-8d1dfec3493a> in <module>()
    ----> 1 teams[1]


    TypeError: 'set' object does not support indexing



## Creating a set

There are two ways to create a set.
