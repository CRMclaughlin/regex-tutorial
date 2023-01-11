# Regular Expression Tutorial(Regex) - Matching a URL

A regular expression, or regex for short, is a series of special characters that define a search pattern. In this tutorial we will examine how they can be implemented in code, and how they can be used to validate specific search criteria.

## Summary

In this tutorial I will try and break down the following regex for matching a URL `/^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/` into its basic components. This tutorial could be helpful for anyone that would like to use regex for validating that a string is a URL. 

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)

## Regex Components

There are many individual compentents that make up the building of regular expressions. Regex is considered a literal, so each expression needs to be begin and end with `/`. 

### Anchors

Regex uses the anchors `^` which signifies the start of a string, and `$` which signifies the end of the string. 

### Quantifiers

In regex, quantifiers define numbers of characters or expressions to match. 

* `*` - matches the preceding pattern 0 or more times
* `+` - matches the preceding pattern 1 or more times
* `?` - matches the preceding pattern 0 to 1 times
* `{ x, y }` - matches the preceding pattern a minimum number of `x` times and a maximum number of `y` times

In our code:

`/^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/`

* In the first bit we see a `?` after the https signifying that https may match 0 or 1 times
* We can see a `+` used to signify that the pattern `[\da-z\.-]` must match 1 or more times
* You can see the bracket `{2, 6}` is used to signify that the pattern `[a-z\.]` must match a minimum of 2 times and a maximum of 6 times
* You can also see the `*` used after `[\/\w \.-]` may match 0 or more times


### Grouping Constructs

In regex grouping constructs are used to check multiple parts or sections of a string for different requirements. By using `()` around different sections of the regex, we create subexpressions that have seperate requirements from each other.

In our code:

`/^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/`

* `(https?:\/\/)`, `([\da-z\.-]+)`, `([a-z\.]{2,6})`, `([\/\w \.-]*)` are all examples of group contsructs in our code



### Bracket Expressions

a bracket expression is enclosed in `[]` brackets and shall match a specific set of single characters, and may match a specific set of mutit-character collating elements, based on the non empty set of list expressions contained in the bracket expression.

In our code:

`/^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/`

* `[\da-z\.-]` in theis expample this bracket expression indicates that any numerical digit, any lowercase letter a to z, slash, period, or hyphen wil produce a match
* `[a-z\.]` in this example the bracket expression indicates that any lowercase lettter a to z, slash, or period will produce a match
* `[\/\w \.-]` in this example the bracket expression indicates the any slash, any alphanumeric character, period, or hyphen will produce a match

### Character Classes

Character classes also called a "character sets" are used to define sets of characters 

In our code:

`/^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/`

* From `[\da-z\.-]` `\d` indicates any digit character 0-9 will match
* From `[\/\w \.-]` `\w` indicates any alphanumeric character will match

### Character Escapes

Character escapes are used when a character is not intended to be interpreted literally. Character escapes are notated by using a `\` in regex.

In our code: 

`/^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/`

* `\.` it is used here to indicate the we are looking for the character `.` strictly and not character class. 

## Author

My name is Christopher McLaughlin, and I'm currently a student in a full stack web developement Coding Camp. To view more of my work please visit GitHub [CRMclaughlin](https://github.com/CRMclaughlin).