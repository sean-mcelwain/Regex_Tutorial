# Regular Expressions ("Regex") Tutorial

Throughout Computer Science applications there is reoccuring need to sort string data in a more encompassing and dynamic way than provided for within the set of string methods of a given programming language.  To serve this need, programming languages contain regular expressions, or regex, which are a series of special characters that define a search pattern universally across programming languages. 

## Summary

This Tutorial will introduce the major concepts and uses of Regular Expressions through examining a specific regex designed to match an email address from a string.  

|Regex of matching an Email  |
| ------------------------------------- |
| `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`        |

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
 
|Starting Anchor (^) &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Ending Anchor ($)|
| ----------------------------------------------------|
|&nbsp;&nbsp; ↓ &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↓                                                 |
|`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`  |



### Quantifiers

Quantifiers allow regular expression to specify how many instances of a character must be present to return a match. As a default, regex quantifiers return as many occurrences of a particular pattern as possible and are described as "greedy" quantifiers.  Alternatively, appending the question mark character (?) to a quantifier will causes the regex quantifier to match as few occurrences as possible and are descripted as "lazy" quantifiers. To specify a number of instances to match, or a range of instances, curly brackets ({}) are used in the regex with the number or range specified inside the curly brackets. 
Quantifiers:
- To match zero or more times: Greedy quantifier: * Lazy quantifier: *?
- To match one or more times: Greedy quantifier: + Lazy quantifier: +?
- To match zero or one time: Greedy quantifier: ? Lazy quantifier: ??
- To match exactly n times: Greedy quantifier: {n} Lazy quantifier: {n}?
- To match at least n times: Greedy quantifier: {n,} Lazy quantifier: {n,}?
- To match from n to m times: Greedy quantifier: {n,m} Lazy quantifier: {n,m}?

### Grouping Constructs

Grouping Constructs allow regular expressions that are more complicated to check multiple different sections, or subexpressions, of a string.  The primary way to group subexpressions is to contain that section of the expression in parentheses (()). Subexpressions look for an exact match unless otherwise specified.  

Grouping Constructs are categorized as either "capturing" or "non-capturing," with the capturing groups retaining the matched character sequence for possible re-use with a numbered backreference, and non-capturing groups do not.  Adding the question mark and colon characters (?:) at the beginning of an expression makes the grouping construct non-capturing.  

### Bracket Expressions

Bracket Expressions allow regular expressions to specify a search parameters using a "positive character group" that we want included in the match results be enclosing them in square brackets ([]).  Alternatively, regex can specify a "negative character group" to exclude from the result by preceding the expression within the brackets with the carrot character (e.g [^a-z])
- The positive character group can either enumerate all of the characters to match (e.g. [abcefg]), or set a range between given alphanumeric characters using a hypen (-), (e.g. [a-g]). 
- Mulitple sets of paramters can be concated together within a positive character group and provide several additional qualifiers.  Because regex are case sensive, in order to find matches containing both uppercase and lowercase characters the positive character group would be [a-zA-Z].
- Positive character groups can also specify special characters, but special characters will follow any specified alphanumeric characters (e.g. [a-z0-9_-]). 

### Character Classes

Character classes allow regular expressions to define a set of characters for finding a match within a given string. 

Common Character Classes Include:
- Positve and Negative Character Groups using Bracket Expressions ([]) (discussed above in Bracket Expressions)
- Any Character - using the dot character (.) in a regex returns a wildcard character that matches any charcter except for \n, which is used to specify a new line. The bracket expression equivalent is: [A-Za-z0-9_]
- Decimal Digit Character - using the slash and d characters (\d) matches any numeral digit. The bracket expression equivalent is: [0-9].  Whereas using the slash and D characters (\D) matches a non-digit character.
- Word Character - using the slash and w characters (\w) matches any alphanumeric character including the underscore.  The bracket expression equivalent is: [A-Za-z0-9_]. Whereas using the slash and W characters (\W) matches a non-word character.
- Whitespace Character - using the slash and s characters (\s) matches a single whitespace character, including tabs and line breaks. Whereas using the slash and S characters (\S) matches a non-whitespace character.


### The OR Operator

The OR Operator, designated by the vertical bar character (|) allows regular expressions to match either a specified parameter, or another specified parameter.  And it can be used for multiple parameters (e.g.(a|b|c)).

### Flags

Flags are a component of regular expressions that define additional functionality or limitations for the search and are appended to the end of the regex following the second slash.  

Some Available Flags
- Global Search (g) - searches for all occurences in the string
- Case-insensitive Search (i) - removes case-sensitivity from the search
- Multi-line Search (m) - searches for all occurences in the string
- Sticky Search (y) - makes the expression start its searching from the index indicated in its lastIndex property
- Unicode Search (u) - makes the expression assume individual characters as code points, not code units, and thus match 32-bit characters as well

### Character Escapes

Charcter Escapes allow a regular expression to find matches including characters that would otherwise be interpreted as a literal.  Character Escapes are designated by the backslash character (\) preceeding the character to be escaped. As an example, the backslash and open curly brace characters (\{) returns matches for the open curly brace character ({) rather than the regex interpreting the open curly brace literally and expecting it to define a quantifier (discused above in Quantifiers).

## Author

Sean McElwain, the author of this tutorial, prepared this Regular Expressions ("Regex") Tutorial as part of Assignment 17 of the University of Kansas Coding Bootcamp Program.  Sean is currently a practicing attorney in the Kansas City Metro Area seeking to transition to a more technologically centered practice and pursuant to that goal, Sean is completing a Bachelors of Science in Electrical and Computer Engineering at the University of Missouri-Kansas City, and elected to participate in the University of Kansas Coding Bootcamp Program.  The purpose in obtaining the B.S.E is to meet eleibility requirements for the USPTO exam (also referred to as the Patent Bar Exam) and the purpose for the Coding Bootcamp is to obtain foundational knowledge for a software engineering patent law practice. 
