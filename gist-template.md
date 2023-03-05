# WGT Regex Tutorial

Introductory paragraph (replace this with your text)
As a new web developer I am always interested in learning new tools that can assist in the coding process.  Regular Expressions, or regex, are one such tool.

## Summary

In this tutorial I will be explaining components of a regex and where they are found in the following regex which matches an email address.  This is very useful for validating that a user has entered a valid email address while using your application.  
`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

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

A regex begins and ends with a `/` character.  These slashes denote the code as a literal.

### Anchors

The first component of a regex is an anchor.  These are used for matching strings, either exactly or from a range.  We use the `^` and `$` characters as anchors.  The difference between the two characters is the order of the character and string.  The `^` is used for strings that ***follow*** the character while the `$` is used for strings that ***precede*** it.

In the email address example 
`^([a-z0-9_\.-]+)`

### Quantifiers

Unsurprisingly, quantifiers deal with the quantity of characters in a regex.  When contained in `{}` they signal either the exact number of characters needed, or a minimum and maximum number.    

In our email example we see `{2,6}` after the `.` character.  This is for the domain extension of an email address such as .com, .org, or .gov.  The minimum lenght for these extensions is 2 characters and the maximum is 6.    

### Grouping Constructs

Grouping constructs allow a long and complex regex to be broken up into smaller components.  The `()` characters are used to enclose individual grouping contructs, also called subexpressions.   

In the email regex, there are 3 subexpressions:    

`([a-z0-9_\.-]+)`    
`([\da-z\.-]+)`    
`([a-z\.]{2,6})`    


`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`



### Bracket Expressions

The `[]` characters are used to contain bracket expressions.  These denote a ***range*** of characters rather than a ***specific*** character.

There are 3 bracket expressions in our email address regex:   
`[a-z0-9_\.-]`   
Denotes any letter from a-z, any digit from 0-9, and the special characters  `_` `\` `.` `-` which are also valid to use in email addresses.   
`[\da-z\.-]`   

`[a-z\.]`   

### Character Classes

Bracket expressions are technically a type of character class.  These define groups of characters that are searched for.    

In the email regex we find another example of a character class:    

`\d` matches any digit 0-9.  Therefore in `[\da-z\.-]` we are checking for both numbers 0-9, letters a-z, and those special characters.    

### The OR Operator

The character `|` is used to signify "or" in a regex just like it is used in JavaScript.  There are no or operators in our email address example.    

### Flags

### Character Escapes

The character `\` is used a an escape.  When using it before another character it stops it from being read literally.  In our example it stops 
`[\da-z\.-]+)\.([a-z\.]{2,6})$/`




## Author

This gist was created by Will Thomas.  Visit my [GitHub profile](https://github.com/WilliamGeorgeThomas) for more information about me.
    