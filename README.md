# Regex Tutorial for Hex Color Codes

Regex is a powerful tool used for searching specifc patterns of text. Possible examples are if you want to find every phone number in a document or check a username meets certain requirements, regex can take care of it. Today we will be going over the regular expression for hex color codes:

    `/^#?([a-f0-9]{6}|[a-f0-9]{3})$/`

## Summary

This comprehensive Regex Tutorial for Hex Color Codes provides a detailed breakdown of regular expressions, emphasizing their application in validating hex color codes. The tutorial covers essential regex components, such as anchors, quantifiers, the OR operator, character classes, grouping, and capturing. Each section explains the relevance of these components in the context of a hex code regex `/^#?([a-f0-9]{6}|[a-f0-9]{3})$/`.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Boundaries](#boundaries)


## Regex Components

It can be daunting to just look at that long string of characters and be expected to know what it all means, but regex expressions can be broken down into 'components' and udnderstood that way. The following sections of the tutorial will go over each component of a regex expression generally then relate it back to our hex code regex.

### Anchors

There are two common anchors, `^` and `$`. 

`^` will find strings that begin with the characters that follow them. `^Hello` will find all the times "Hello" was typed. It's important to note that `^Hello` and `^hello` are NOT the same. 

#### Regex is case sensitive and this will be the case moving forwrd.

`$` will find strings that ends with the characters that preceed it. So `ing$` will find all the strings that end in "ing". 

In our hexfinder regex the `^#` component means its looking for strings that start with a hashtag character.

### Quantifiers

Quantifiers set the limit of the amount of times your regex matches. Can include the minimum and the maximum.

`*` - Matches the pattern any number of times (including 0).
`+` - Matches the pattern one or more times.
`?` - Matches the pattern either zero or one time.
`{}` - Curly braces are slightly more complex and have different notations.
`{1}` - Matches the pattern exactly one time.
`{5,}` - Matches the pattern a minimum of five times.
`{1,5}` - Matches the pattern between one and five times.

In our hex code regex line:

    `/^#?([a-f0-9]{6}|[a-f0-9]{3})$/`

we see two sets of curly braces, a `{6}` and a `{3}` meaning it will find the previous pattern described 6 times and 3 times. (The `|` character means something special we will cover next.)

### OR Operator

In regular expressions, the "or" operator is represented by the pipe character `|`. It allows you to specify alternatives, meaning that either the expression on the left or the one on the right should match. In the provided example `/^#?([a-f0-9]{6}|[a-f0-9]{3})$/`:

`([a-f0-9]{6}|[a-f0-9]{3})` - is a group that denotes two alternatives separated by `|`.
`[a-f0-9]{6}` - specifies the first alternative, requiring a sequence of six characters where each character is a lowercase letter between 'a' and 'f' or a digit between 0 and 9.
`[a-f0-9]{3}` - is the second alternative, requiring a sequence of three characters following the same pattern.

### Character Classes

In regular expressions, character classes allow you to define a set of characters from which the pattern should match a single character. In the example `/^#?([a-f0-9]{6}|[a-f0-9]{3})$/`:

- `[a-f0-9]` is a character class that specifies a range of characters. In this case, it includes all lowercase letters from 'a' to 'f' and all digits from 0 to 9.
- `{6}` and `{3}` following the character class denote the number of times the preceding character class should occur in the string – six times for the first alternative and three times for the second.

So, `([a-f0-9]{6}|[a-f0-9]{3})` means "match either a sequence of six characters or a sequence of three characters, where each character is a lowercase letter between 'a' and 'f' or a digit between 0 and 9."

The entire regular expression `/^#?([a-f0-9]{6}|[a-f0-9]{3})$/` uses character classes within a larger pattern to validate strings that represent hexadecimal color codes. The `#?` at the beginning makes the hash symbol optional, and the following character class and quantifiers enforce the length and composition rules for valid hexadecimal color codes.

### Grouping and Capturing

The primary way you group regex is by using parentesis `()` which we have an example of in our hex code matcher:
    `/^#?([a-f0-9]{6}|[a-f0-9]{3})$/`

The `([a-f0-9]{6}|[a-f0-9]{3})` groups together two patterns the line looks for, `[a-f0-9]{6}` or `[a-f0-9]{3})`

### Bracket Expressions

Bracket expressions, anything inside square brackets like these `[]`, are used to represent a range of characters that we want to match. They are called bracket expressions but can also be refered to as a positive group because they outline the characters we want to include.

They can be written as follows:

`[abc]` - looks for a string with either a or b or c
`[a-z]` - looks for all letters from a to z as lowercase

In our hex code regex line we can see it includes `[a-z0-9]` in two different places. This will include all lowercase letters followed by any single digit number in the match.

### Greedy and Lazy Match

In regex, "greedy" and "lazy" refer to the quantifiers that control the repetition of characters in a pattern.

Greedy: The quantifier matches as much as possible. The default behavior.
    Example: a+ matches one or more 'a' characters, as many as possible.
Lazy (or non-greedy): The quantifier matches as little as possible.
    Example: a+? matches one or more 'a' characters, but as few as possible.

In our hex code example the quantifiers `{6}` and `{3}` are greedy by default, matching the maximum number of characters (6 or 3) that satisfy the pattern.

### Boundaries

In regex, boundaries are positions in the string where certain conditions are met, such as the start or end of a word.

`^`: Asserts the start of the string.
`$`: Asserts the end of the string.
`\b`: Asserts a word boundary.

In our `/^#?([a-f0-9]{6}|[a-f0-9]{3})$/`. The ^ and $ symbols denote the start and end of the string, ensuring that the entire string conforms to the specified pattern.

## Author

Jack Lund
Github [here](https://github.com/lundj227)