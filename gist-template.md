# Regex Email Validation Breakdown by Joey Porter

## Summary

In this Regex breakdown, you will learn how to validate the featured email address using regular expression (regex): /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/. The breakdown provides an explanation of each component within the regex, simplifying the validation process for easy understanding. Upon completing this breakdown, you will gain a deeper comprehension of how the regex functions to validate and confirm the entry of a valid email address.


## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping](#grouping)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [Character Escapes](#character-escapes)
- [Conclusion](#conclusion)
- [Author](#author)


## Regex Components
```
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
```


### Anchors
The regex begins with an Anchor, "^" and ends with the Anchor, '$'.
```
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
```
Anchors are powerful special characters in regular expressions, they play an essential role in defining the position of the pattern within the input string. Anchors essentially define the boundaries of the text that the regex should match. This regex ends with the "$" anchor.


### Quantifiers
In a regex, quantifiers are metacharacters that specify how many times the previous character or group should be matched. Quantifiers allow you to specify the number of occurrences of a character or group, making it easier to match patterns of varying lengths. In the first and second capture groups "([a-z0-9_\.-]+)@([\da-z\.-]+)" we have the "+" quantifer. This indicates that the previous character must occur at least one or more times. 


### Grouping
Grouping constructs in our regex are used to group together one or more characters or sub-expressions, and treat them as a single unit within the expression. You can tell they are part of a group by the parentheses () and they serve the following purposes:

    - Applying quantifiers to a group of characters.
    - Capturing the designated part of the match.
    - Creating backreference for previously matched group.
    - Applying alternation to a group of characters

Our regex featured in this breakdown contains three groups enclosed among the parentheses ().


### Bracket Expressions
Brackets [] indicate a set of characters to match. Any individual character between the brackets will match, and you can also use a hyphen to define a set. See the breakdown below of the character classes contained inside of each bracket expression our regex uses. Bracket expressions are very useful for creating flexible and concise regular expressions to match specific sets of characters in your text.


### Character Classes
The first, second and third capture groups each have a character class specifying what characters are allowed in each section of the email address.

The bracket expression in the first capture group is for the username of the email and it will allow:
```
([a-z0-9_\.-]+)
```
    - lowercase letters 'a-z'
    - digits '0-9
    - underscore '_'
    - dot '.'
    - hyphen '-'

The bracket expression in the second capture group is for the domain name and it will allow:
```
([\da-z\.-]+)
```
    - digits '\d'
    - lowercase letters 'a-z'
    - dot '.'
    - hyphen '-'

The bracket expression in the third capture group is for the top level domain and it will allow:
```
([a-z\.]{2,6})
```
    - Between 2-6 occurrences of:
    - lowercase letters 'a-z'
    - dot '.'

The '@' - matches the literal @ symbol.


### Character Escapes
The '\' is call the Escape Character, which when used in this manner helps define special characters with special functions. For example, to search for the period you can't simply put a '.'. This would indicate you were searching for 'any character except new line.' using the excape character like so '\.' will search for a period and no the character class of the single dot. There are 4 instances of the escape character in our regex below:
```
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
```


## Conclusion
So, in summary, this regular expression is used to validate an email address with the following pattern:

    - The username can contain lowercase letters, digits, underscore _, dot ., or hyphen -.
    - It must be followed by @.
    - The domain name can contain digits, lowercase letters, dot ., or hyphen -.
    - It must be followed by a dot ..
    - The top-level domain must have between 2 and 6 lowercase letters or dots.

This regex will match strings like johndoe999@website.com or jane.doe-999@website.org, but won't match emails with uppercase letters or invalid characters in the wrong places.


## Author
Follow Joey Porter on Github!
- [joey2522](https://github.com/Joey2522)
