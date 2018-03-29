# Introduction to Sets

## What are sets and why use them?

Say you are writing an algorithm to determine whether an incoming email ought to be added to your inbox or to your spam folder. You need to collect all of the unique words that appear in your regular emails and your spam emails then check how often these words appear in each category, respectively. If the incoming email contains the words "free" and "consultation" and these words appear more often in spam than in regular messages, then you know this email should be sent to your spam folder.

A **set** is a type of data collection that is useful for such a task. They are handy whenever you need to collect only unique elements from a large collection. In the **Instant Data Science** lesson, you saw how to use a set to remove duplicate words from the list of “Barbara Ann” song lyrics.

Sets are much like lists, but with three key differences:



#### 1) Elements are unique

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



#### 2) Elements are immutable

Although a set itself is changeable, as we will see later on, its constituent elements must be immutable. For example, a set's elements cannot be lists, dictionaries, or other sets because these objects can be altered. The code below produces a TypeError:

```python
teams = set((["Yankees", "Red Sox", "Blue Jays"], ["Mets", "Phillies", "Nationals"]))
```

However, you can make a set of multiple tuples. Think of tuples as lists that cannot be altered. They are created with parentheses ```()``` instead of square brackets ```[]```.

```python
teams = set((("Yankees", "Red Sox", "Blue Jays"), ("Mets", "Phillies", "Nationals")))

teams
Out: {('Mets', 'Phillies', 'Nationals'), ('Yankees', 'Red Sox', 'Blue Jays')}
```



#### 3) Elements are unordered

Elements of a set do not have order, therefore using an index to select an element produces a TypeError:

```python
teams[1]
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-20-5bc081d74201> in <module>()
    ----> 1 teams[1]


    TypeError: 'set' object does not support indexing



## Creating a set

A set can be created using Python's built-in ```set()``` function, as seen in the examples above, or with curly braces ```{}```. A single list can be passed into the built-in ```set()``` function. Sets can consist of multiple datatypes as long as they are not mutable objects.

```python
things = {"Python", 3.14159, 1}

languages = set(['JavaScript', 'Perl', 'Python', 'Ruby'])
```





## Operating on a set

As programmers, we tend to be lazy. We want our code to be as concise and clean as possible. Programming is a collaborative effort and concise code makes it easy for others to understand our programs. Fortunately, Python provides us with a variety of built-in functions for operating on sets in a clean and intuitive manner.

#### Adding an element

The ```add()``` function adds a single element to the set, as long as said element isn't already contained in the set.

```python
languages.add("Java")

languages
Out: {'Java', 'JavaScript', 'Perl', 'Python', 'Ruby'}
```


#### Adding multiple elements

Pass a list into the ```update()``` method to add multiple elements to a set.

```python
languages.update(["C", "C++"])

languages
Out: {'C', 'C++', 'Java', 'JavaScript', 'Perl', 'Python', 'Ruby'}
```


#### Removing an element

Both the ```discard()``` and ```remove()``` methods remove a single element.

```python
languages.discard("C++")

# or

languages.remove("C++")

languages
Out: {'C', 'Java', 'JavaScript', 'Perl', 'Python', 'Ruby'}
```

Note that the ```remove()``` method raises an error if the element is not included in the set whereas ```discard()``` does not.

```python
languages.remove("PHP")
```

    ---------------------------------------------------------------------------
    KeyError                                  Traceback (most recent call last)
    <ipython-input-49-de307097e4ca> in <module>()
    ----> 1 languages.remove("PHP")

    KeyError: 'PHP'


#### Removing all elements

The ```clear()``` function removes all of the elements from the set.

```python
languages.clear()

languages
Out: set()
```


#### Is this element in the set?

We can check whether an element appears in our set using the ```in``` and ```not in``` keywords. Both ```in``` and ```not in``` return a boolean depending upon whether the element of interest is found in the set.

```python
languages = set(["Python", "Ruby", "JavaScript", "Perl"])
```

```python
"Python" in languages

Out: True
```

```python
"C++" in languages

Out: False
```

```python
"C++" not in languages

Out: True
```





## Working with multiple sets


#### Union

Let's say we have one set of streets found in New York City and another of streets found in Boston. How can we collect all of the streets in New York City and Boston without double counting the streets that exist in both cities? The **Union** of two sets is a set of elements which are in **either** set. Use the  ```union()``` method or the ```|``` operator to handle these situations.

```python
nyc = set(["34th St", "125th St", "High Street", "Oak St", "Elm St", "14th St", "Horatio St"])
boston = set(["State St", "Beacon St", "Charles St", "High Street", "Oak St", "Elm St", "Boylston St"])
```

```python
nyc.union(boston)

# or

nyc | boston

Out:
{'125th St',
 '14th St',
 '34th St',
 'Beacon St',
 'Boylston St',
 'Charles St',
 'Elm St',
 'High Street',
 'Horatio St',
 'Oak St',
 'State St'}
 ```

Since "High Street", "Oak St", and "Elm St" appear in just about every city in the country, it's not surprising that they exist in both NYC and Boston! ```union()``` and ```|``` count these streets only once.


#### Intersection

What if we only care about the cities that appear in both cities? The **Intersection** of two sets is the set of elements found in **both** sets. As you expected, the ```intersection()``` method and the ```&``` operator work in the same manner.

```python
nyc.intersection(boston)

# or

nyc & boston

Out:
{'Elm St', 'High Street', 'Oak St'}
```


#### Difference

Now imagine that you are writing a history of Boston and you're interested only in streets unique to Boston. The **Difference** of two sets is the set of elements in one set **but not** the other. You can use the ```difference()``` method or simple subtraction ```-``` to eliminate the streets found in both Boston and NYC.

```python
boston.difference(nyc)

# or

boston - nyc

Out:
{'Beacon St', 'Boylston St', 'Charles St', 'State St'}
```



### Summary

In this section we learned how to use sets to find only the unique values from a collection of data. We learned that sets differ from lists because their elements are unique, immutable, and unordered. Python provides a variety of methods to easily add, remove, and clear all elements from the set. Furthermore, we learned how to work with multiple sets using ```union()```, ```intersection()```, and ```difference()```.
