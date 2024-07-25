# Matching an Email Address with Regex

Regular expressions, also known as regex, is a tool for pattern matching and data validation in strings. In this tutorial, it is going to focus on how regex will be disgned to match email addres, and will break down each component. In each component, we will see how it works and how it is going to be used effectively when validating emials using different applications, such as Node or MongoDB. 

## Summary

The regex we will be explaing is  /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/ 

This pattern is commonly used to validate email address, to make sure they follow the standard format of an email

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

Anchors are used in regex to define the position of the match wihin a string, to make sure that the entire string is evaluated according to the pattern. 
Caret (^) indicates the start of the string.  It makes sure that ethe email pattern is only match if it appears right atht the start of the string.  It will prevent partial matches where email. 

EXAMPLE 
Match: user@example.com
Non-Match: info@user@example.com (The string starts with "info@" and not "user@")
Dollar Sign ($) indicates that the match must occur at the end of the string.  It does not allow for any trailing characters.
EXAMPLE 
Match: user@example.com
Non-Match: user@example.com is my email (The string contains additional text after the email address)

### Quantifiers

Quantifiers specifiy the umber of times a character or gorup can occur in the string. 
One or more is symbolised by '+', which matches one or more occurances ahead of the element. 
With the matching email code:  /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/ , we can see the quantifier being used multiple places. 
([a-z0-9_\.-]+): The + following the character class [a-z0-9_\.-] ensures that the username part of the email address consists of at least one or more of the specified characters (lowercase letters, digits, underscores, dots, and hyphens).
([\da-z\.-]+): Similarly, the + makes sure that the domain name contains one or more digits, lowercase letters, dots, or hyphens.
{2,6}: This quantifier specifies that the preceding group should occur between 2 and 6 times.

### Grouping Constructs

Grouping constructs are used in regex to group parts of the pattern together. Parentheses () are used for grouping, allowing the enclosed characters to be treated as a single unit. 
([a-z0-9_\.-]+) hooks the username part of the email address.
([\da-z\.-]+) hooks the domain name. 
([a-z\.]{2,6}) hooks the domain extension, such as '.com'.

### Bracket Expressions

Bracket expressions, also known as character classes specify a set of characters that can be matched.
[a-z0-9_\.-]: This character class matches any lowercase letter (a-z) and is case sensitive. It can matches single character between 0-9 (0-9), underscore (_), dot (.), or hyphen (-). It defines the allowable characters in the username part of the email address and is case sensitive. 
[\da-z\.-]: This character class is used for the domain name and matches any digit (\d), lowercase letter (a-z), dot (.), or hyphen (-).
[a-z\.]: This class matches lowercase alphabetic characters and dots, used for the domain extension

### Character Classes

Character classes differentiate kinds of characters between letters and digits. 

[a-z] is for character classes that match a single caracter between a and z, that is case sensitive. 

[\d] matches andy numeric digit zero through nine and is equivalent to [0-9].

### The OR Operator

The OR operator (|) is used to specifcy alternative patterns and means match this or that.  In regex for matching email, this is not explicity used, but can be important for when multiple patterns were to be matched. 

### Flags

Flags are optional parameter to a regex that modifies its behvaior of searching.  It changes the default seacing behabior of a regular expression.  It is usually denoted using a single lowercase alphabetic character.  
Some common flags include 'i', which is case sensitive, and 'g', which is a global search. 
In email regex, we do not use flags, but they can be helpful when creating regex in a different situation.

### Character Escapes

Escapes are used to treat any speical characters, and is must a backaslach infront of it. 
When we use \. , we are specifiying it should only match a period character. 
## Author

[MyGitHub](https://github.com/jmeason)  
