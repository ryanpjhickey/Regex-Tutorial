# What is Regex?

Regex, also called regular expressions, search bodies of text for specified characters, more specifically ASCII or unicode characters. It can be used in tandem with almost any programming language with very miniscule deviations in regards to syntax and formatting.

## Summary

Briefly summarize the regex you will be describing and what you will explain. Include a code snippet of the regex. Replace this text with your summary.

Matching an Email – /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

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

### Anchors

# 1. ^

Using ^ before text will match any strings that start with said text.

For example: ^Testing123

This will match any strings that start with "Testing123"

# 2. $

Using $ after text will match any strings that end with said text.

For example: 123Testing$

This will match any strings that end with "123Testing"

# 3. No Anchor

Choosing not to use ^ or $ will match any strings that contain the text anywhere in the string.

For example: lackofanchor

This will match any string that contains "lackofanchor" anywhere in the string.

# 4. ^ and $ used in combination

Choosing to use both ^ and $ in combination will match any strings exactly as they are typed.

For example: ^PerfectMatch$

This will match any string that is typed exactly as "PerfectMatch"

### Quantifiers

# 1. \*

When \* is used, it will match a string to the last character, and for the last character the string can include zero or more of that character.

For example:
Asterisk \*

This will find Asteris, Asterisk, Asteriskk, Asteriskkk, Asteriskkkk, Asteriskkkkk, etc.

# 2. +

When + is used, it will match a string to the last character, and for the last character the string can include one of more of that character.

For example:
Plus+

This will find Plus, Pluss, Plusss, Plussss, Plusssss, etc.

# 3. ?

When ? is used, it will match a string to the last character, and for the last character the string can include either zero or one of that character.

For example:
Question?

This will find Questio or Question.

# 4. {Number}

When {} is used, it will match a string to the previous character, followed by the specified number of instances of that character.

For example:
Six{6}

This will find Sixxxxxx.

# 5. {Number,}

When {Number,} is used, it will match a string to the previous character, followed by the specificied number of instances of that character, or more.

For example:
Four{4}

This will find Fourrrr, Fourrrrr, Fourrrrrr, Fourrrrrrr, etc.

# 6. {Number,Number}

When {Number,Number} is used, it will match a string to the previous character, followed by the specified lower limit of instances of that character, up to the specificed upper limit of instances of that character.

For example:

Between{3,5}

This will find Betweennn, Betweennnn, and Betweennnnn.

### OR Operator

|

[]

### Character Classes

\d

\w

\s

.

### Flags

g

m

i

### Grouping and Capturing

()

(?:)

(?<foo>)

### Bracket Expressions

[abc]

[a-c]

[a-fA-F0-9]

[0-9]%
[^a-za-z]

### Greedy and Lazy Match

(\*+{})

<.+?>

<[^,<>]+>

### Boundaries

\babc\b

\Babc\B

### Back-references

([abc])\1
([abc])([de])\2\1
(?<foo>[abc])\k<foo>

### Look-ahead and Look-behind

d(?=r)
(?<=r)d

d(?!r)
(?<!r)d

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
