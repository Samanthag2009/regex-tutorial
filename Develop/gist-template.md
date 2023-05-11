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

Quantifiers tell the regex how many times variables occur in matching strings. 
In our email address regex, we can break it down into groups:

#### Capture Group 1

Here we see the + symbol, a quantifier that matches the previous token at least once but up to unlimited times. This means that the first part of our email address (before the @) contains characters from the list in parenthesis, and could occur many times. 
```
([a-z0-9_\.-]+)
```
#### Capture Group 2

Once again, we see the + symbol, a quantifier that matches the previous token at least once but up to unlimited times. This means that the second capture group contains exactly one @ symbol, and characters from the list in parenthesis, which could occur many times. 
```
@([\da-z\.-]+)
```
#### Capture Group 3

Finlly, we see {2,6} at the end of capture group 3. This tells the regex to search for characters within the brackets, but only between 2 to 6 times.

```
([a-z\.]{2,6})
```


### OR Operator

The OR Operator is signified by the | symbol. it allowes the regex to consider alternatives such as the name Jim for the name James. 

```
(James|Jim) Brown
```
The criteria above will search for both Jim and James Brown. The regex we are using today does not contain an OR Operator. 

### Character Classes

Character Classes define the characters that are allowed in our regex. The list of allowed characters is put into square brackets and the characters within the brackets are characters that are allowed in a set of characters. Once again, let's take a look at our code broken up piece by piece.

#### Capture Group 1

Here we see those square brackets specifying characters that are allowed. in this case, the beginning of our email address can ONLY contain letters a-z, numbers 0-9, dashes and periods. The slash indicates the allowance of the period. The brackets are unbroken, indicating one set of characters.
```
([a-z0-9_\.-]+)
```
#### Capture Group 2

Once again, we see our square brackets. This time we see \d, which indicates that digits 0-9 are allowed. Characters a-z are allowed, as are periods and dashes.
```
@([\da-z\.-]+)
```
#### Capture Group 3

Lastly, we see the same brackets indicating that letters a-z and periods are allowed. a set containing a digit would be invalid here.

```
([a-z\.]{2,6})
```

### Grouping and Capturing

Thus far, we have been breaking up bits of our regex into 3 "capturing groups," which seperate the regex into sub-groups based on the parts in parenthesis. Grouping the regex like this allows us to make the intent of our regex clearer, and applies any quantifiers or other expressions.

To visualize this, here they are again:
#### Capture Group 1

```
([a-z0-9_\.-]+)
```
#### Capture Group 2

```
@([\da-z\.-]+)
```
#### Capture Group 3

```
([a-z\.]{2,6})
```

### Greedy and Lazy Match
Greedy quantifiers are intended to find the longest possible string. Conversely, Lazy will match the shortest possible string. 

```
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
```

In our regex above, we see the + quantifier used three times throughout the expression, always indicating that the token can be matched unlimited times. This is a greedy match. 

We do not see an example of a lazy match in this instance, but quantifiers to look for include using a ? symbol after any other quantifier. 

## Author

### Samantha Gosselin

Samantha Gosselin is a fullstack web developer based in Austin, Texas. You can view her work on [github](https://github.com/Samanthag2009) or connect on [linkedIn](https://www.linkedin.com/in/samantha-gosselin-37493517/)
