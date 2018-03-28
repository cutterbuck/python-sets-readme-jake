# Introduction to Sets

A set in Python is another type of data collection that is useful for tracking only unique elements. You used a set in the **Instant Data Science** lesson to remove duplicate words from the list of “Barbara Ann” song lyrics. Sets are handy whenever you need to build a histogram to count the frequency with which a certain element appears in a large collection of data.

Say you are writing an algorithm to determine whether an incoming email ought to be placed in your inbox or in your spam folder. You could use a set to collect the unique words that appear in your all of your regular emails and all of your spam emails. If the incoming email contains the words "free" "consultation" and these words appear more often in spam messages, you know this email should be sent to your spam folder.

Sets are much like lists, but with three main differences:

1) there are no duplicate elements

2) the individual elements cannot be changed

3) the items in the collection are unordered


## Creating a set

There are two ways to create a set.
