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

### The OR Operator

### Flags

### Character Escapes

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
