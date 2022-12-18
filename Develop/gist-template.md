# What is Regex?

Regex, also called regular expressions, search bodies of text for specified characters, more specifically ASCII or unicode characters. It can be used in tandem with almost any programming language with very miniscule deviations in regards to syntax and formatting.

## Summary

Matching an Email – /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

This regex tutorial will teach you how to read and understand regular expressions such as the one noted above.

/^([a-z0-9_\.-]+)@ Checks for any hexadecimal characters followed by an "@" afterwards.

@([\da-z\.-]+)\. then checks for any hexidecimal characters after the "@" but before the ".", but this time not including the "\_" from last time.

\.([a-z\.]{2,6})$/ checks for any characters "a-z" after the ".", including more "."s if necessary. the {2,6} will allow for a repeated character up to 6 times in a row.

The /^ and $/ at the beginning and end of the expression allow for a perfect read, capture, and match of the read e-mail address.

This regex allow for matching of e-mail addresses such as:

ryan@ryan.com

PeguinLovr84@comcast.net

tester@test.deploy.com

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

When | is used, it will match the previous string followed by two options denoted on either side of the |.

For example x(y|z) will match a string as xy or xz.

[] can be used similarly, such as x[yz],

The difference is that in the first example, | will capture y or z, while [] will not capture y or z.

### Character Classes

\d matches a single character that is a digit

\w matches an alphanumeric character followed by an underscore, which is a "word" character

\s matches a whitespace character (i.e. tabs and line breaks)

. matches any character

\d, \w, & \s all will perform the inverse by using a capital letter instead. For example, \D would match a single character that is not a digit, etc.

### Flags

g does not return after the first match, restarting the subsequent searches from the end of the previous match.

m when enabled ^ and $ will match the start and end of a line, instead of the whole string.

i makes the whole expression case-insensitive (for instance /aBc/i would match AbC).

### Grouping and Capturing

Parentheses allow you to create a capturing group for whatever value is within the parentheses

Example:

x(yz)

Using this in conjuction with ?: allows you to disable the capturing group like so:

x(?:yz)

Finally, using ?<foo> in conjuction with x(yz) allows you to associate a name with the groyp, like so:

x(?<foo>yz)

### Bracket Expressions

[] allows you to match a string that has any of the characters inside.

For example [xyz] will match any string with an x, a y, or a z. x|y|z is also the same thing, as well as [x-z].

[w-zW-Z0-9] This will return a string that has a single hexadecimal digit and it is case insensitive.

[0-9]% This will return a string with any number 0-9 that happens to occur before a % symbol.

[^a-za-z] This will return a string that HAS NOT used any letter from a-z, regardless of case. The ^ acts as a negator in this case, similiar to !=

### Greedy and Lazy Match

(\*+{}) These quantifiers are greedy operators which means that they look as far as they can for a match in the provided text.

<.+> for example would match <h1>Awesome Title</h1> from:

"This is a <h1>Awesome Title</h1>!!"

<.+?> The addition of the question mark here allows us to only catch the h1 tag and its content, making it "lazy."

<[^,<>]+> is another solution here that should be used to avoid usage of the global "." as it is a stricter regex.

### Boundaries

\blanguage\b performs a whole words only search that will search for the word "language"

\Blanguage\B performs the inverse of that and will only match the word language if it is in the midst of other characters. For example, it will find: "reallycoollanguage"

### Back-references

([xyz])\1 using \1 will match the text that is captured in the first capturing group.
([xyz])([efg])\2\1 we can use \2, \3, etc. to reference the text in the second, third capturing group as well
(?<foo>[xyz])\k<foo> allows us to put a name to the group and we can reference it later with \k<foo>

### Look-ahead and Look-behind

d(?=r) matches a d only if is followed by r, while also allowing for r to not be included in the final regex match
(?<=r)d matches a d only if is preceded by an r, while also allowing for r to not be included in the final regex match

d(?!r) matches a d only if is not followed by r, while also allowing for r to not be included in the final regex match
(?<!r)d matches a d only if is not preceded by an r, while also allowing for r to not be included in the final regex match

## Author

My name is Ryan Hickey and I created this regex tutorial. Please check out some of my other projects at:
https://github.com/ryanpjhickey

Thank you for reading!
