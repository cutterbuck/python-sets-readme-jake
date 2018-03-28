# Introduction to Sets

## What are sets and why use them?

Say you are writing an algorithm to determine whether an incoming email ought to be added your inbox or to your spam folder. You need to collect all of the unique words that appear in your your regular emails and your spam emails then check how often these words appear in each category, respectively. If the incoming email contains the words "free" and "consultation" and these words appear more often in spam than in regular messages, you know this email should be sent to your spam folder.

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

Although a set can be operated upon, its constituent elements cannot be alterable objects. For example, you cannot make a set featuring multiple lists or dictionaries as elements because these objects can be changed. The code below produces a TypeError:

```python
teams = set((["Yankees", "Red Sox", "Blue Jays"], ["Mets", "Phillies", "Nationals"]))
```

However, you can make a set of multiple tuples because tuples are immutable. Think of tuples as lists that cannot be altered. They are created with parentheses ```()``` instead of square brackets ```[]```.

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


#### Adding an element

Use the ```add()``` function to add single elements to the set, as long as the element isn't already contained in the set.

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

Both the ```discard()``` and ```remove()``` methods remove elements from a set.

```python
languages.discard("C++")

# or

languages.remove("C++")

languages
Out: {'C', 'Java', 'JavaScript', 'Perl', 'Python', 'Ruby'}
```

The ```remove()``` method raises an error if the element is not included in the set whereas ```discard()``` does not.

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


#### Determining whether element is in the set

Python easily allows us to check whether an element appears in our set. The ```in``` and ```not in``` keywords return a boolean depending upon whether the element of interest is found in the set.

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

"C++" not in languages

Out: True
```





## Working with multiple sets

fsdf
