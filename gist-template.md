# Regex Tutorial: Complex Password Strength 

This tutorial will look at Regex (regular expressions) and will explain what they are and how they work.  To accomplish this, we will look at a commonly used Regex for verifying moderate password strength (1 uppercase, 1 lowercase, 1 number, and at least 8 characters long). 

## Summary

Regex (short for regular expressions) is a string of text and text characters that allows a user to search for patterns with a text. It can be used from the command line or within a text editor. 

Using the Regex below (a Regex that verifies moderate password strength) we will define the different parts of the regex and how they are used. 

    
/(?=(.*[0-9]))((?=.*[A-Za-z0-9])(?=.*[A-Z])(?=.*[a-z]))^.{8,}$/

The / at the beginning and the end of the Regex indicates the start and the end of the regular expression. 

## Table of Contents

- [Anchors](#anchors)

- [Quantifiers](#quantifiers)

- [OR Operator](#or-operator)

- [Character Classes](#character-classes)

- [Flags](#flags)

- [Grouping and Capturing](#grouping-and-capturing)

- [Bracket Expressions](#bracket-expressions)

- [Greedy and Lazy Match](#greedy-and-lazy-match)

- [Boundaries](#boundaries)

- [Back-references](#back-references)

- [Look-ahead and Look-behind](#look-ahead-and-look-behind)


## Regex Components

/(?=(.*[0-9]))((?=.*[A-Za-z0-9])(?=.*[A-Z])(?=.*[a-z]))^.{8,}$/

The Regex above contains the following components (in order from left to right)

1. / open
2. ?= positive lookahead
3. () capturing group 1
4. . dot character class
5. * Quantifier
6. [] character set
7. 0-9 range
8. () capturing group 2
9. ?= positive lookahead
10. . dot character class
11. * Quantifier
12. [] character set
13. A-Z range (uppercase)
14. a-z range (lowercase)
15. 0-9 range
16. ?= positive lookahead
17. . dot character class
18. * Quantifier
19. [] character set
20. A-Z range (uppercase)
21. ?= positive lookahead
22. . dot character class
23. * Quantifier
24. [] character set
25. a-z range (lowercase)
26. ^ beginning
27. . dot character class
28. {8,} Quantifier
29. $ end
30. / close 
### Anchors

The anchors can be seen in this part of the Regex: ^.{8,}$

The ^ indicates the beginning of the string and the $ indicates the end of the string.  The anchors appear at the end of the Regex because everything that comes before it is defining the elements that should be (or can be) included in the string. 

### Quantifiers

The quantifier of the above Regex is: {8,}. What this tells us is that the password must match 8 or more of the preceeding tokens. The Regex also includes the * quantifier, which says to match either 0 or more of the preceeding token. 

### OR Operator

The code above does not contain any OR operators. An or operator: | is used to join two different expressions.  It is used to search for text matching either of the adjoined expressions. 

### Character Classes

Character classes include the following: 

. - matches any character
\w \d \s - matches a word, digit, or whitespace 
[abc]- matches any of the letters in the square brackets 
[^abc]- matches anything that is NOT a, b, or c
[a-g]- matches any character between a and g 

The regex contains many character classes: /(?=(.*[0-9]))((?=.*[A-Za-z0-9])(?=.*[A-Z])(?=.*[a-z]))^.{8,}$/

1. . [0-9] matches any number 0-9
2. .[A-Za-z0-9] matches any capital letter A-Z, any lowercase letter a-z, any number 0-9
3. .[A-Z] matches any capital letter A-Z
4. .[a-z] matches any lower case letter a-z

### Flags

This regex does not include any flags. Possible flags used in Regex include: 

d = generate indices for substring matches
g = global search
i = case-insensitive search
m = multi-line search
s = allows . to match newline characters
u = treat a pattern as a sequence of unicode code points
y = perform a "sticky" search that matches starting at the current position in the target string 

*more info can be found here: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions#advanced_searching_with_flags


### Grouping and Capturing

Capturing groups multiple tokens together.  It is denoted by (). The following Regex: /(?=(.*[0-9]))((?=.*[A-Za-z0-9])(?=.*[A-Z])(?=.*[a-z]))^.{8,}$/ contains two capturing groups. 

Group 1: (?=(.*[0-9]))
Group 2: ((?=.*[A-Za-z0-9])(?=.*[A-Z])(?=.*[a-z]))

### Bracket Expressions

Bracket expressions were defined above when discussing character classes.  They consist of one or more of the following expressions: ordinary characters (or literal characters), collating elements (letters that combine together such as ss to make ß or  ou to make Ü), collating symbols, equivalence classes (elements grouped together like a and a with an accent), character classes (telling the computer to match only one part of a class or set), or range expressions.

Range expressions are seen above in [A-Z], [0-9], and [a-z]

### Greedy and Lazy Match

The above Regex does not contain any greedy or lazy quantifiers. Greedy quantifiers could be quotes or a +. A greedy search tries to match the pattern for every position in the string. A lazy search (?) will stop searching once the condition is satisfied. 

Note: the ?= is different from a ? 

### Boundaries

The above regex does not contain any boundaries. A word boundary \b matches a word boundary position between a word character and a non-word character. 

### Back-references

The above Regex does not include a back reference. A back reference might look like: \1 which would mean to match the results of the capture group #1. 
### Look-ahead and Look-behind

This above Regex includes 4 positive look-aheads noted with ?=. The positive lookahead matches a group after the main expression without including it in the result. There are two different possible look aheads and two different possible look behinds: 

1. positive lookahead: Matches a group after the main expression without including it in the result. ?=
2. negative lookahead: Specifies a group that can not match after the main expression. ?!
3. positive lookbehind: Matches a group before the main expression including it in the result. ?<
4. negative lookbehind: Specifies a group that can not match before the main expression ?<!


## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
