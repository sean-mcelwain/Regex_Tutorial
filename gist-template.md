# Regular Expressions ("Regex") Tutorial

Throughout Computer Science applications there is reoccuring need to sort string data in a more encompassing and dynamic way than provided for within the set of string methods of a given programming language.  To serve this need, programming languages contain regular expressions, or regex, which are a series of special characters that define a search pattern universally across programming languages. 

## Summary

Briefly summarize the regex you will be describing and what you will explain. Include a code snippet of the regex. Replace this text with your summary.

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
Anchors allow regular expressions to specify the position in a string to search for a match.  The two specified positions by regex are either at the beginning or the end of the string.  To specify the beginning of a string, regex use the carrot character (^), and for the end of a string regex use the dollar sign character ($).  Anchors will return both an exact string or a range of possible matches. 

### Quantifiers



### Grouping Constructs

### Bracket Expressions

Bracket Expressions allow regular expressions to specify a search parameters using a "positive character group" that we want included in the match results be enclosing them in square brackets ([]).  
- The positive character group can either enumerate all of the characters to match (e.g. [abcefg]), or set a range between given alphanumeric characters using a hypen (-), (e.g. [a-g]). 
- Mulitple sets of paramters can be concated together within a positive character group and provide several limiting conditions.  Because regex are case sensive, in order to find matches containing uppercase and lowercase characters the positive character group would be [a-zA-z]
- Positive character groups can also specify special characters, but special characters will follow any specified alphanumeric characters (e.g. [a-z0-9_-]). 

### Character Classes

### The OR Operator

### Flags

### Character Escapes

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
