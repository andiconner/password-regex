# Password Regex Tutorial

Regular expressions (or regex) are patterns used to match character combinations in strings, in other words, regex is a sequence of characters that defines a specific search pattern. In JavaScript, regular expressions are also objects. These patterns are used with the exec() and test() methods of RegExp, and with the match(), matchAll(), replace(), replaceAll(), search(), and split() methods of String. 

## Summary

In this tutorial I will show how to implement a Regex to Validate a password.

* As a developer, I want to find certain patterns of characters within a string to validate a password.

Password requirements:
  * Must have between 8-12 characters long.`{8,12}`

  * Must have at least 1 lowercase letter. `(?=.*?[a-z])`

  * Must have at least 1 Uppercase letter.  `(?=.*?[A-Z])`

  * Must have at least 1 Number. `(?=.*?[0-9])`
  
  * Must have at least 1 Special Character. `(?=.*?[#?!@$%^&*-])`


This is the regular expression for the Password:
`/^(?=.*?[A-Za-z0-9])(?=.*?[#?!@$%^&*-]).{8,12}$/`

See below each regex component explanation to understand how to come up with this regex.


## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Character Classes](#character-classes)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)

## Regex Components

### Anchors
The characters `^` and `$` are considered anchors. `^` is used at the beggining of the expression and `$` at the end.

### Quantifiers
Set the limits of the string of the expression we want to match. in other words, it includes the minimum and maximum number of the characters.
`{8,12}`


### Character Classes
With a “character class”, also called “character set”, you can tell the regex engine to match only one out of several characters. 
If you repeat a character class by using the `?`, `*` or `+` operators, you’re repeating the entire character class.

Here are some of the other common character classes:

`.` — Matches any character except the newline character (\n)

`\d` — Matches any Arabic numeral digit. This class is equivalent to the bracket expression `[0-9]`.

`\w` — Matches any alphanumeric character from the basic Latin alphabet, including the underscore `(_)`. This class is equivalent to the bracket expression `[A-Za-z0-9_]`.

`\s` — Matches a single whitespace character, including tabs and line breaks


### Bracket Expressions
`[]` are used to express the characters to be matched. For instance, [abc] would search for the lowercase letters "a, b and c" and also could be represented by [a-c]. In our regex we combined uppercase, lowercase letters and numbers inside the bracket expression: `[A-Za-z0-9]`

### Greedy and Lazy Match
Greedy matches as many occurrences of particular patterns as possible. They include the following:

`*` — Matches the pattern 0 or more times

`+` — Matches the pattern 1 or more times

`?` — Matches the pattern 0 or one time

`{}` — Curly brackets can provide three different ways to set limits for a match:

`{ n }` — Matches the pattern exactly n number of times

`{ n, }` — Matches the pattern at least n number of times

`{ n, x }` — Matches the pattern from a minimum of n number of times to a maximum of x number of times

Each of these quantifiers `can be made lazy by adding the ? symbol after it`, meaning it will match as few occurrences as possible.

For the password regex, we had to use a combination `(?=.*?)` of Greedy, Lazy Match and a Character Class to be able to follow the password requirements for "at least" one uppercase letter `(?=.*?[A-Z])` /lowercase letter `(?=.*?[a-z])`/number `(?=.*?[0-9])`/special character `(?=.*?[#?!@$%^&*-])`



## Author 
Andi Conner is a fullstack boot camp student at UCF. You can find more of her work at her gitub profile page: https://github.com/andiconner


