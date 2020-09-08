# Python Regular Expression
Discover the power of regular expressions with this tutorial. You will work with the re library, deal with pattern matching, learn about greedy and non-greedy matching, and much more!

Regular Expressions, often shortened as regex, are a sequence of characters used to check whether a pattern exists in a given text (string) or not. If you've ever used search engines, search and replace tools of word processors and text editors - you've already seen regular expressions in use. They are used at the server side to validate the format of email addresses or passwords during registration, used for parsing text data files to find, replace, or delete certain string, etc. They help in manipulating textual data, which is often a prerequisite for data science projects involving text mining.

### Regular Expressions in Python

In Python, regular expressions are supported by the re module. That means that if you want to start using them in your Python scripts, you have to import this module with the help of import

`import re`

The` re` library in Python provides several functions that make it a skill worth mastering. You will see some of them closely in this tutorial.

## Basic Patterns: Ordinary Characters
You can easily tackle many basic patterns in Python using ordinary characters. Ordinary characters are the simplest regular expressions. They match themselves exactly and do not have a special meaning in their regular expression syntax

Examples are 'A', 'a', 'X', '5'.
Ordinary characters can be used to perform simple exact matches:

```

pattern = r"Cookie"
sequence = "Cookie"
if re.match(pattern, sequence):
    print("Match!")
else: print("Not a match!")

```
`Match!`

## Summary table
You have already come a long way with regular expressions. It is a lot of information and concepts to grasp! The following table summarizes all that you've seen so far in this tutorial. Don't worry if you can't wrap your head around all the metacharacters just yet. With time and practice, you will be able to see the uniqueness of these characters and learn when to use what...

This tutorial does not discuss all the special sequences provided in Python. Check out the Standard Library reference for a complete list.


**Character(s)** |	**What it does**
-------------    |---------
.                |  A period. Matches any single character except the newline character.
^                |	A caret. Matches a pattern at the start of the string.
\A               |Uppercase A. Matches only at the start of the string.
$                 |Dollar sign. Matches the end of the string.
\Z                |Uppercase Z. Matches only at the end of the string.
[]               |Matches the set of characters you specify within it.
'\ '               |∙ If the character following the backslash is a recognized escape character, then the special meaning of the term is taken.
∙                 | Else the backslash () is treated like any other character and passed through.
∙             |It can be used in front of all the metacharacters to remove their special meaning.
\w              |Lowercase w. Matches any single letter, digit, or underscore.
\W             |Uppercase W. Matches any character not part of \w (lowercase w).
\s             |Lowercase s. Matches a single whitespace character like: space, newline, tab, return.
\S              |Uppercase S. Matches any character not part of \s (lowercase s).
\d              |Lowercase d. Matches decimal digit 0-9.
\D             |Uppercase D. Matches any character that is not a decimal digit.
\t         |Lowercase t. Matches tab.
\n          |Lowercase n. Matches newline.
\r            |Lowercase r. Matches return.
\b              |Lowercase b. Matches only the beginning or end of the word
'+'            |Checks if the preceding character appears one or more times.
'*'            |	Checks if the preceding character appears zero or more times.
?       | Checks if the preceding character appears exactly zero or one time Specifies a non-greedy version of +, *
{}     |Checks for an explicit number of times.
()      |	Creates a group when performing matches.
<>           |Creates a named group when performing matches.










