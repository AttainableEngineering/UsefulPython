# UsefulPython
Useful Python Code, Information, and Idioms to use


## Data Types:
### Lists:
A collection of data that is ordered and changeable. Lists allow duplicate members. Lists can hold any data type.
You can store lists of lists (of lists of lists of lists.....), allowing for complex data processing.

#### Syntax:
listname = [item, item2, item3, item, ...]

#### Idiom: Multiple Assignment / Tuple Unpacking:
cat = ['fat', 'gray', 'loud']  
size, color, disposition = cat (assigns multiple values rapidly)

#### Methods:
['\_\_add__', '\_\_class__', '\_\_contains__', '\_\_delattr__', '\_\_delitem__', '\_\_dir__', '\_\_doc__', '\_\_eq__', '\_\_format\_\_', '\_\_ge__', '\_\_getattribute\_\_', '\_\_getitem__', '\_\_gt__', '\_\_hash__', '\_\_iadd__', '\_\_imul__', '\_\_init__', '\_\_init_subclass__', '\_\_iter__', '\_\_le__', '\_\_len__', '\_\_lt__', '\_\_mul__', '\_\_ne__', '\_\_new__', '\_\_reduce__', '\_\_reduce_ex__', '\_\_repr__', '\_\_reversed__', '\_\_rmul__', '\_\_setattr__', '\_\_setitem__', '\_\_sizeof__', '\_\_str__', '\_\_subclasshook__', 'append', 'clear', 'copy', 'count', 'extend', 'index', 'insert', 'pop', 'remove', 'reverse', 'sort']

### Tuples:
A collection of data that is ordered and **unchangeable**. Tuples are used to store multiple items in a single variable, and can have duplicate items.

#### Syntax:
tuplename = (item, )  
tuplename = (item1, item2, item3, ...)
You need to include the comma for a single item list to be recognized as a tuple.  

#### Methods:
['\_\_add__', '\_\_class__', '\_\_contains__', '\_\_delattr__', '\_\_dir__', '\_\_doc__', '\_\_eq__', '\_\_format__', '\_\_ge__', '\_\_getattribute__', '\_\_getitem__', '\_\_getnewargs__', '\_\_gt__', '\_\_hash__', '\_\_init__', '\_\_init_subclass__', '\_\_iter__', '\_\_le__', '\_\_len__', '\_\_lt__', '\_\_mul__', '\_\_ne__', '\_\_new__', '\_\_reduce__', '\_\_reduce_ex__', '\_\_repr__', '\_\_rmul__', '\_\_setattr__', '\_\_sizeof__', '\_\_str__', '\_\_subclasshook__', 'count', 'index']

### Sets:
A collection of data that is **unordered**, **unchangeable**, and **does not** allow duplicate values. Sets cannot be referenced with an index.

#### Syntax:
setname = {data1, data2, data3, ...}

#### Methods:
['\_\_and__', '\_\_class__', '\_\_contains__', '\_\_delattr__', '\_\_dir__', '\_\_doc__', '\_\_eq__', '\_\_format__', '\_\_ge__', '\_\_getattribute__', '\_\_gt__', '\_\_hash__', '\_\_iand__', '\_\_init__', '\_\_init_subclass__', '\_\_ior__', '\_\_isub__', '\_\_iter__', '\_\_ixor__', '\_\_le__', '\_\_len__', '\_\_lt__', '\_\_ne__', '\_\_new__', '\_\_or__', '\_\_rand__', '\_\_reduce__', '\_\_reduce_ex__', '\_\_repr__', '\_\_ror__', '\_\_rsub__', '\_\_rxor__', '\_\_setattr__', '\_\_sizeof__', '\_\_str__', '\_\_sub__', '\_\_subclasshook__', '\_\_xor__', 'add', 'clear', 'copy', 'difference', 'difference_update', 'discard', 'intersection', 'intersection_update', 'isdisjoint', 'issubset', 'issuperset', 'pop', 'remove', 'symmetric_difference', 'symmetric_difference_update', 'union', 'update']

### Dictionaries:
A collection of data that is ordered, changeable, and does not allow duplicates.

#### Syntax:
dictname = { key : value,  key2 : value2 ...}  
var = dictname[key] = value

#### Idiom: Create a Histogram
dictname = dict()  
for items in data:  
  for item in items:  
    dictname[item] = dictname.get(item,0) + 1

#### Methods:
['\_\_class__', '\_\_contains__', '\_\_delattr__', '\_\_delitem__', '\_\_dir__', '\_\_doc__', '\_\_eq__', '\_\_format__', '\_\_ge__', '\_\_getattribute__', '\_\_getitem__', '\_\_gt__', '\_\_hash__', '\_\_init__', '\_\_init_subclass__', '\_\_iter__', '\_\_le__', '\_\_len__', '\_\_lt__', '\_\_ne__', '\_\_new__', '\_\_reduce__', '\_\_reduce_ex__', '\_\_repr__', '\_\_reversed__', '\_\_setattr__', '\_\_setitem__', '\_\_sizeof__', '\_\_str__', '\_\_subclasshook__', 'clear', 'copy', 'fromkeys', 'get', 'items', 'keys', 'pop', 'popitem', 'setdefault', 'update', 'values']

## Useful Features:


### Regular Expressions:
Regular Expressions, or RegEx are not built into python naturally... import re

Python Regular Expression Quick Guide:
* ^        Matches the beginning of a line
* $        Matches the end of the line
* .        Matches any character
* \s       Matches whitespace
* \S       Matches any non-whitespace character
* \*        Repeats a character zero or more times
* *?       Repeats a character zero or more times (non-greedy)
* \+        Repeats a character one or more times
* +?       Repeats a character one or more times (non-greedy)
* [aeiou]  Matches a single character in the listed set
* [^XYZ]   Matches a single character not in the listed set
* [a-z0-9] The set of characters can include a range
* (        Indicates where string extraction is to start
* )        Indicates where string extraction is to end

can re.search() to see if a string matches a regular expression, similar to find() method for strings

can use re.findall() to extract portions of a string that match regular expression, similar to combo of find() and slicing: var[5:10]

Ex:
[0-9]+
everything included in brackets is ONE DIGIT. plus means one or more digits
y = re.findall('[0-9]+', x)
will parse through text in var/str x and return all instances of values / all matches

^X.*: is starting at X at beginning of line, including any character up to colon
spits out anything starting with x and all characters up to colon

^X-\S+:
start at beginning of line matching X and a dash, match any non whitespace character one or more times until colon, and print out


Greedy Matching: wants to be as big as possible, and will return largest possible instance of what it has found

Ex:
x = 'From: using the:'
y = re.findall('^F.+:',x)
Printing y will output texst all the way to second :

for NON GREEDY:
y = re.findall('^F.+?:' , x) is non greedy

Ex:
If you have email data in text starting with "From email@url.url" ... 
y = re.findall('^From (\S+@\S+)', x)
will find the whole string, starting with "From", but only extract email address

Note: To override and write out a symbol, use '\' backslash to make symbols behave as strings
Ex: \$[0-9.]+
looks for string starting w dollar sign (despite being a reserved regex symbol), one or more numbers or dots, then pull it out

