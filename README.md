# UsefulPython
Useful Python Code, Readme's, and Idioms to use


## Useful Features:
### Regular Expressions:
Regular Expressions, or RegEx are not built into python naturally... import re
"
Python Regular Expression Quick Guide:
^        Matches the beginning of a line
$        Matches the end of the line
.        Matches any character
\s       Matches whitespace
\S       Matches any non-whitespace character
*        Repeats a character zero or more times
*?       Repeats a character zero or more times (non-greedy)
+        Repeats a character one or more times
+?       Repeats a character one or more times (non-greedy)
[aeiou]  Matches a single character in the listed set
[^XYZ]   Matches a single character not in the listed set
[a-z0-9] The set of characters can include a range
(        Indicates where string extraction is to start
)        Indicates where string extraction is to end
"

can re.search() to see if a string matches a regular expression, similar to find() method for strings

can use re.findall() to extract portions of a string that match regular expression, similar to combo of find() and slicing: var[5:10]

Ex:
[0-9]+
everything included in brackets is ONE DIGIT. plus means one or more digits
y = re.findall('[0-9]+', x)
will parse through text in var/str x and return all instances of values / all matches

