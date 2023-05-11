# Regex Tutorial: Matching an Email Address

There are many methods in JavaScript to help us find what we're looking for; a specific word, a specific phrase, etc. But what if we need a more dynamic solution? It's one thing to search with "cntrl+F" to find a word we know exists (such as a common email provider,) but there is a more encompassing solution.

## Summary

In this tutorial, we will be breaking down the below regular expression (also known as "regex") for finding an email address. 

```
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
```

While the above regex doesn't appear to be much to look at now, let's dive into the ins and out of a more dynamic way to search for and manipulate an email address.

## Table of Contents

- [Regex Components](#regex-components)
- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Boundaries](#boundaries)
- [Back-references](#back-references)
- [Look-ahead and Look-behind](#look-ahead-and-look-behind)

## Regex Components

As stated above, the regex below is designed to assist in searching for and manipulating an email address. Regex isa formatted as a literal wrapped in slash characters. Let's take a look at the building blocks that make up our regex.

```
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
```


### Anchors

Anchors in regex are characters that are not a part of the matching criteria for the characters. Anchors serve to match a position before, after or between the characters. the character ^ matches the position before the first character in a string, identifying that the string begins with the charachters that follow it, and the character $ matches the position directly after the last character in a string and signify that the string contains the characters that preceed it. 

Below is a table notating common anchors.
![Regex anchor table by slawo-ch](./images/anchors.png)

For our purposes, we can identify ^ and $ as our anchors for the beginning and ending of the string respectively:

```
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
```

### Quantifiers



### OR Operator

### Character Classes

### Flags

### Grouping and Capturing

### Bracket Expressions

### Greedy and Lazy Match

### Boundaries

### Back-references

### Look-ahead and Look-behind

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
