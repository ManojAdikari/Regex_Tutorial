# Regex Tutorial "Matching an Email"

In this tutorial explaining  one of the more commonly used Regular Expressions "Matching an Email " and how it works.
##  /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

## Summary

This will be a Regex used to verify that a specific input is a valid email address.A regex or more officially refered to as a regular expression is a sequence of characters that define a search pattern. These are commonly used to determin patterns within a string. I will explain the basics of Regex and the specific components used in this snippet: /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Back-references](#back-references)

## Regex Components
- "^" - Anchor (Start)
- "$" - Anchor (End)
- "()" - Grouping Construct (Subexpression)
- "[]" - Bracket Expression (Character Group)
- "a-z" - Character Class (Character Range)
- "0-9" - Character Class (Character Range)
- "\" - Escape
- "_", "-", ".", "@" - Character Class (Literal Matches)
- "+" - Quantifier (match previous element between one and unlimited times, as many as possible)
- "{2,6}" - Quantifier (match previous element between 2-6 times, as many as possible)
- "Greedy Match" - Match Type (match largest possible group)

### Anchors
Anchors, also known by their less convienient name: atomic zero-width assertions, are used to set a position in a string where a match must occur. This means that it does not parse through the whole string, but only looks for a match in the specified position.Within our current regex, we have two anchors. The "^" character, also known as a caret, and the "$" character.
* `^` Circumflex (freestanding) shows the start of the string and it shows the position not any character. 

 * `$`The dollar sign, also known as peso sign, is another symbol to shows the position of the end of our Email string.

### Quantifiers
A Quantifier specifies how many instances of the previous element (which can be a character, a group, or a character class) must be present in the input string for a match to occur. They also determine whether a regex will attempt a Greedy match or a Lazy match.
There are two quantifiers within this regex, the first being `+` which is a greedy quantifier. This quantifier will allow connection for the users `email+ email service + .com`.
The other quantifier is the `{2,6}`, this will match everything after the `.` 2-6 times to ensure it has at least 2 characters and no more than 6.


### Character Classes
- "a-z" is a lowercase character range
- "0-9" is a digit character range
- "\d" serves the same purpose as defining the previous digit range
- "_" and "-" match their respective characters literally
- "\." matches a period literally
- "@" and the external "\." match their respective characters literally at certain positions in the input string

### Flags
Regex usually is written in between two forward slashes "/", including our's. After the second forward slash we may specify a flag. However, our current Regex does not have any flags to mention.

### Grouping and Capturing
Each Character Group in this regex is housed within within a Capture Group marked by parenthesis"()". Text that is matched by the regex inside of the Capture Group will be placed into a numbered group (in the case of JavaScript, this is an array) where you may access the matching characters with their index.

### Bracket Expressions
Bracked expressios for email validation includes the character sets of [a-z0-9_\.-], which is matching any letter a-z and is case senstive. It also matches a character 0-9 and matches the characters "_" , "-" , and "."; [\da-z\.-], which is matching a single digit from 0-9, any character a-z (case senstive), and the characters "." and "-".; [a-z\.] matches any character a-z(case senstive) and the character ".".


### Greedy and Lazy Match
A Greedy Match, marked by the Quantifiers "+", "*", and "{#}, all of which tell the regex to parse the input string attempt to match the largest group possible within the given perameters. For example, the 3rd Quantifier tells the regex to attempt to match between 2 and 6 times, as many as possible for the given input string. Even though there is a range here, it still seeks to match the largest group it can within that range and is thus a Greedy Match. Lazy matches are marked by the question mark "?", but there are many different applications for this character that do many different things. For instance, ([a-z0-9_\.-]+?) would attempt to match one or more times, but as few times as possible. A different example may be ([a-z0-9_\.-]??), where the regex matches the element zero or one time but still as few as possible.

### Back-references
Bracketed expressions within the email validation are within the []. In the first part of the regex ([a-z0-9_\.-]+) everything within the [] is going to match any letter a-z, any number from 0-9 and the characters _, .,-. This regex has 3 sets of bracketed expressions each looking for different pieces of information.


## Author

You can view my projects at https://github.com/ManojAdikari
