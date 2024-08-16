# Regex URL Filtering

This tutorial will show you how to use Regular Expressions (regex) to match URLs in strings using JavaScript. Regex is a powerful tool for pattern matching and text manipulation.

## Summary

This tutorial provides an in-depth guide on using Regular Expressions (regex) in JavaScript to match URLs. It covers essential regex components like anchors, quantifiers, grouping constructs, bracket expressions, character classes, the OR operator, flags, and character escapes. Through examples, you'll learn how to create powerful regex patterns that can accurately identify URLs in text, enhancing your ability to manipulate and extract information from strings effectively.

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

### Anchors

Anchors are used to assert the position within a string. There are two main anchors:

- ^: Asserts the start of a string.
- $: Asserts the end of a string.

To match a URL that starts at the beginning of a string:

` const pattern = /^https?:\/\/[^\s/$.?#].[^\s]*$/; `

### Quantifiers

Quantifiers specify how many instances of a character, group, or character class must be present for a match:

- *: 0 or more times.
- +: 1 or more times.
- ?: 0 or 1 time (also makes quantifiers non-greedy).
- {n}: Exactly n times.
- {n,}: At least n times.
- {n,m}: Between n and m times.

To match a URL with at least one character after "http://":

` const pattern = /https?:\/\/.+/; `

### Grouping Constructs

Grouping allows you to capture parts of the regex for use later or apply quantifiers to the entire group:

- (...): Capturing group.
- (?:...): Non-capturing group.

To optionally match "www." in a URL:

` const pattern = /https?:\/\/(www\.)?[^\s/$.?#].[^\s]*/; `

### Bracket Expressions

Bracket expressions (also known as character sets) match any one of the characters inside the brackets:

- [abc]: Matches 'a', 'b', or 'c'.
- [^abc]: Matches any character except 'a', 'b', or 'c'.

To match any character except whitespace:

` const pattern = /https?:\/\/[^\s]+/; `

### Character Classes

Character classes allow you to specify a set of characters to match:

- \d: Matches any digit (equivalent to [0-9]).
- \D: Matches any non-digit.
- \w: Matches any word character (equivalent to [a-zA-Z0-9_]).
- \W: Matches any non-word character.
- \s: Matches any whitespace character.
- \S: Matches any non-whitespace character.

To match a URL with digits in it:

` const pattern = /https?:\/\/\w+\.\w+\.\d+/; `

### The OR Operator

The OR operator (" | ") allows you to match one of several patterns:

To match URLs starting with "http" or "https":

` const pattern = /http:\/\/|https:\/\/[^\s/$.?#].[^\s]*/; `

### Flags

Flags modify the behavior of the regex:

- g: Global search (find all matches).
- i: Case-insensitive search.
- m: Multi-line search.

To match URLs case-insensitively:

` const pattern = /https?:\/\/[^\s/$.?#].[^\s]*/gi; `

### Character Escapes

Some characters have special meanings in regex. To match these characters literally, you need to escape them with a backslash ( \ ):

To match URLs with a dot ( . ):

` const pattern = /https?:\/\/[^\s\/$.?#]+\.[^\s]+/; `

## Author

Written by Mike Duffey

- Github: https://github.com/Mtduffey36
- Repo: https://github.com/Mtduffey36/regex-tutorial
- Gist: https://gist.github.com/Mtduffey36/f735a3353c570c13bb826717c574e633
