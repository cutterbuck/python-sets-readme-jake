# Introduction to Sets

Say you are writing an algorithm to determine whether an incoming email ought to be placed in your inbox or in your spam folder. You need to collect all of the unique words that appear in your your regular emails and your spam emails then check how often these words appear in each category. If the incoming email contains the words "free" and "consultation" and these words appear more often in spam than in regular messages, you know this email should be sent to your spam folder.

A **set** is a type of data collection that would be useful for such a task. You used a set in the **Instant Data Science** lesson to remove duplicate words from the list of “Barbara Ann” song lyrics. Sets are handy whenever you need to pull only the unique elements from a large collection of data.

Sets are much like lists, but with three main differences:

1) there are no duplicate elements

2) the individual elements cannot be changed

3) the items in the collection are unordered


## Creating a set

There are two ways to create a set.
