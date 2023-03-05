# WGT Regex Tutorial

As a new web developer I am always interested in learning new tools that can assist in the coding process.  Regular Expressions, or regex, are one such tool.

## Summary

`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

In this tutorial I will be explaining components of a regex and where they are found in the regex above which matches an email address.  This is very useful for validating that a user has entered a valid email address while using your application.  In our example, all aspects of an email address are checked such as presence of alphanumeric characters in the address, the `@` symbol, a valid url, followed by a `.` and domain extension.

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

### Quantifiers

Unsurprisingly, quantifiers deal with the quantity of characters in a regex.  When contained in `{}` they signal either the exact number of characters needed, or a minimum and maximum number.    

In our email example we see `{2,6}` after the `.` character.  This is for the domain extension of an email address such as .com, .org, or .gov.  The minimum lenght for these extensions is 2 characters and the maximum is 6.    

We also find the example of `+` which checks for the pattern more than once.  We find this in our example 2 times.

### Grouping Constructs

Grouping constructs allow a long and complex regex to be broken up into smaller components.  The `()` characters are used to enclose individual grouping contructs, also called subexpressions.   

In the email regex, there are 3 subexpressions:    

`([a-z0-9_\.-]+)` : checks against contained bracket expression which will be explained in the next section and does so multiple times as indicated by the `+`    
`([\da-z\.-]+)` : same as above but with different bracket expression    
`([a-z\.]{2,6})` : checks against a different bracket expression while also containing a quantifier of between 2 and 6 characters    

### Bracket Expressions

The `[]` characters are used to contain bracket expressions.  These denote a ***range*** of characters rather than a ***specific*** character.

There are 3 bracket expressions in our email address regex:   
`[a-z0-9_\.-]` : denotes any letter from a-z, any digit from 0-9, and the special characters  `_` `\` `.` `-` which are also valid to use in email addresses    
`[\da-z\.-]` : also checks for numerical digits (explained in next section), letters, and those special characters in the email domain    
`[a-z\.]` : checks for letters a-z as well as only the `\` and `.` special characters    

### Character Classes

Bracket expressions are technically a type of character class.  These define groups of characters that are searched for.    

In the email regex we find another example of a character class:    

`\d` matches any digit 0-9.  Therefore in `[\da-z\.-]` we are checking for both numbers 0-9, letters a-z, and those special characters.    

### The OR Operator

The character `|` is used to signify "or" in a regex just like it is used in JavaScript.  There are no or operators in our email address example.    

### Flags

Flags are characters that can be placed at the end of a regex after the final `/` character.  While there are none in our email example, the 3 most common are:    
`g` : tests regex against all posibilities in a string    
`i` : ignores case when matching    
`m` : treats multiple line strings as multiple lines    

### Character Escapes

The character `\` is used a an escape.  When using it before another character it stops it from being read literally.  There are no examples of this in the email regex. 

## Author

This gist was created by Will Thomas.  Visit my [GitHub profile](https://github.com/WilliamGeorgeThomas) for more information about me.
    