---
title: "Python Basics"
last_modified_at: 2022-06-20
categories:
- CS
tags: 
- Python
toc: true
---

## Setup

- [Python](https://www.python.org/)
- Editor: [Atom](https://atom.io/)
    - Try not to use Integrated Development Environment (IDE)
    - Atom: enter the path for a new file
        - filename.py
- Create directory

## Features of Python

- Interpreted language
    - Source code not directly translated by the target machine
- Compact and readable
    - High-level data type
    - Statement grouping by indentation
    - No variable or argument declarations necessary
- Extensible

## Using Python interpreter

### Invoking interpreter

- `python` command in shell
- Exit: `Ctrl + Z` or `quit()`
- or <code>python -c <i>command</i> [arg] ...</code> to execute the statement in command
- <code>python -m <i>module</i> [arg] ...</code> to execute the source file for module
- `-i` before script to run script and enter interactive mode afterwards

### Argument passing

- Interpreter turn the scripte name and additional arguments into a list of strings, and assign to `argv` variable in `sys` module
- `import sys` in script to use `argv` variable
- Length of the list is at least one
    - `sys.argv[0]` is empty string, if no script and no arguments are given
    - `sys.argv[0]` is set to `-` (standard input), if script name is given as `-`
    - `sys.argv[0]` is set to `-c`, if `-c` commant is used
    - `sys.argv[0]` is set to the full name of the module, if `-m` module is used
- Options after `-c command` or `-m module` left in `sys.argv` for the command or module to handle, not by interpreter's option processing

### Interactive mode

- `>>>` primary prompt for the next command
- `...` secondary prompt for continuation lines

### Interpreter and environment

- Defualt encode in UTF-8
- Declare an encoding other than default, at first line:
    - <code>-\*- coding: <i>encoding</i> -\*-</code>
    - <code><i>encoding</i></code> is [codec](https://docs.python.org/3/library/codecs.html#module-codecs) registry and base classes

## Basics

### Comment

- `#` for single line
- `''' ... '''` for multiple lines

### Variable

- Variable casting
    - `str()`
    - `int()`
    - `float()`
- Variable name
    - Case sensitive
    - Naming format
        - Camel case `myVariableName`
        - Pascal case `MyVariableName`
        - Snake case `my_variable_name`
- Assign value to variables
    - `x, y = 3, "test"`
    - `x = y = "test"`
    - Unpack a collection of a value in list or tuple
- Global and local variable
    - Global variable
        - Created outside a function
        - `global` keyword, created inside a function
    - Local variable
        - Created inside a function
- Assignment operator
    - `=`, `+=`, `-=`, `*=`, `/=`, `%=`, `//=`, `**=`

### `print()` function
- `print('Hello world.\nI'm back.')`
- `print('8' + '+ 8 =', 8 + 8)`
- <code>print(<i>variable</i>)</code>
- Add `r` to use raw string instead of interpreting special characters by `\`
    - `print('C:\some\location')`
- Multiple lines by `''' ... '''` or `""" ... """`

### Data type

- Text type: `str`
- Numeric type: `int`, `float`, `complex`
- Sequence type: `list`, `tuple`, `range`
- Mapping type: `dict`
- Set type: `set`, `frozenset`
- Boolean type: `bool`
- Binary type: `bytes`, `bytearray`, `memoryview`
- None type: `NoneType`
- `type()` to get data type

#### Number

- Arithmetic operator
    - `+`, `-`, `*`, `/`
    - `//` return integer for floor divisoin discarding any fractional result
    - `%` for reminder
    - `**` for powers
- Numeric type
    - `int`
    - `float`: division always return floating point nunmber
    - `complex`: `j` for imaginary part of complex number
- `_`
    - In interactive mode, the last printed expression is assigned to the variable `_`
- Random number
    - `import random` - built-in module
    - `random.randrage(1, 10)`

#### String

- In single or double quotes <code>\`...\`</code> or <code>"..."</code>
- Multiline string `"""..."""`
- Escape special character with balckslash
    - `\'` --> `'`
    - `\\` --> `\`
    - `\n` --> new line
    - `\r` --> carriage return
    - `\t` --> tab
    - `\b` --> backspace
- Concatenation
    - Concatenate string with `+`, repeat with `*`
        - `3 * 'm' + 'os'` --> `"mmmos"`
    - Auto concatenate for two or more string literals enclosed between quotes
        - `'py' 'th' 'on'` --> `"python"`
- Index and slice
    - String is array
    - First character having index 0
    - Indices can be negative, counting from the right from -1
        - `'python'[1]` --> `"y"`; `'python'[-1]` --> `"n"`
        - `'python'[0:2]` --> `"py"` # include position 0, exclude position 2
        - `'python'[:2] + 'python'[2:]` --> `"python"`
        - `'python'[:]` --> `"python"`
        - `'python'[0:5:2]` --> `"pto"` # at interval of 2
        - `'python'[::2]` --> `"pto"` # `::` for whole string
        - `'python'[::-1]` --> `"nohtyp"` # negative interval to reverse string
    - Out of range index
        - Error for get the character of index
        - Ok for slicing
    - String is immutable, cannot assign value to an indexed position
    - Loop through a string
        - `for x in "banana": print(x)`
    - Check if characters in string `in` & `not in` (membership operator)
        - `"ba" in "banana"` --> `True`
        - `"ya" not in "banana"` --> `True`
- `len()`: return length of a string
- [String method](https://docs.python.org/3/library/stdtypes.html#string-methods)
    - Case
        - `upper()` & `lower()` & `capitalize()` & `capwords()`
    - Remove whitespace
        - `strip()`
    - Replace character
        - `"abcd".replace("ab", "cd")` --> `"cdcd"`
    - Split
        - `"ad cd".split(" ")` --> `["ab", "cd"]`
    - Join
        - `join()`
    - Count
        - `count()`
    - End with
        - `endswith()`
    - Find position
        - `find()` & `index()`: return first position
        - `rfind()` & `rindex()`: return last position
    - Check type & format
        - `isalnum()`: if all are alphanumeric, alphabet or number
        - `isalpha()`: if all are alphabet
        - `isdecimal()`, `isnumeric()`, `isdigit()`, `isidentifier()`
        - `islower()`, `istitle()`, `isupper()`, `isspace()
    - Fill 0 at the beginning
        - `"90".zfill(4)` --> `0090`

#### Bollean

- `True` or `False`
- Comparison operator: `<`, `>`, `==`, `!=`, `<=`, `>=`
- Logical operator: `and`, `or`, `not` # `not` has higher priority
    - Sequence can be compared
        - Compare first two items, if equal then anther two
- Identity operator: `is`, `is not`
- False values
    - `bool(None)`
    - `bool(0)`
    - `bool("")`
    - `bool(())`, `bool([])`, `bool({})`

## Control flow tools

### `if` statement

- `if ... elif ... (else ...)`
    - `elif` stands for else if
- Short hand
    - `if a == b: print ("equal")`
    - `print("A") if a > b else print("<") if a <b else print("=")`
- `pass` statement
    - `if` statement cannot be empty, use `pass` if no content
- Nested if

### `while` statement

- `break` statement to stop the loop
- `continue` statement to stop the current iteration, and continue with the next iteration in loop
- `else` statement
- Nest while

### `for` statement

- For iterating over a sequence
    - List, tuple, set, dict, string
    - `for x in "test": print(x)`
- `break` statement
- `pass` statement
- `continue` statement
- `else` statement
- `range()` function
    - `range(start, end, increment)`
    - Return a sequance of number
    - Starting from 0 by default, increment by 1 by default
    - Include left, exclude right
    - `for x in range(0, 10, 3): print(x)` --> `4`
- Nested for

~~~
# Modify a collection by iterating
users = {'A': 'active', 'B': 'active', 'C': 'inactive'}

# Strategy: iterate over a copy
# items() return dict pairs in list
for user, status in users.copy()items():
    if status == 'inactive':
        del users[user]

# Strategy: create a new collection
active.users = {}
for user, status in users.items():
    if status == 'active':
        active.users[user] = status
~~~

### `match` statement

- Compare value to successive patterns given as case blocks
- Can unpack collections, patterns can bind variables

    ~~~
    #point is an (x, y) tuple
    match point:
        case (0, 0):
            return "Origin"
        case (x, 0) | (0, y):           # '|' for or
            return "On axis"
        case (x, y):
            print(f'X = {x}, Y = {y}')
        case _:                         # '_' as wildcard and never match
            raise ValuyeError('Not a point')
    ~~~

- `match` and `class`

    ~~~
    class Point
        x: int
        y: int

    def where_is(point):
        match point:
            case []:
                print('No point')
            case [Point(0, 0)]:
                print('origin)
            case Point(x=0, y=y):
                print(f'Y = {y})
            case [Point(0, y1), Point(0, y2)]:
                print(f'Two on the Y axis at {y1}, {y2}')
            case Point(x, y) if x==y
                print(f'Y = X at {x}')
    ~~~


### Define function

- `def func(argument)`

- Variables defined in function is local
    - `global` for global variable
    - `nonlocal` for variable of enclosing function

        ~~~
        # nonlocal
        x = 0
        def outer():
            x =1 
            def inner()
                nonlocal x
                x = 2
                print("inner:", x)
            
            inner()
            print("outer:", x)

        outer()
        print("global:", x)

        >>> inner: 2
        >>> outer: 2
        >>> global: 0
        ~~~

        ~~~
        # global
        x = 0
        def outer():
            x =1 
            def inner()
                global x
                x = 2
                print("inner:", x)
            
            inner()
            print("outer:", x)

        outer()
        print("global:", x)

        >>> inner: 2
        >>> outer: 1
        >>> global: 2
        ~~~

- Function definition associates the function name with function objects
    - `out = outer`
    - function `outer` can be accessed by function name `out`

- End of function
    - Functions without a `return` statement return `None`
    - `print` cannot replace `return`

- Method is a function belongs to an object named `obj.methodname`

- Argument
    - Can be any data type
    - Arbitrary argument `*args`
        - Unknown numbers of arguments
        - Function receive a tuple of arguments

        ~~~
        def func(*name):
            print("Middle name is " + name[2])

        func("Wang", "Frank", "Dazhi")
        ~~~

    - Keyword argument
        - Send argument with `key = value` syntax
        - `func(last = "Wang", middle, first = "Dazhi")`
            - `middle` is required argument
            - `last` & `first` is optional argument
    - Arbitrary keyword argument `**args`
        - Function receive a dictionary of arguments
        - `def func(**name)`
    - Default parameter value
        - If call function without argument, use default value
        - Evaluate only once, may pass to subsequent call
        - `def func(a, L = [])`
    - Speical parameter
        - `def f(pos1, pos2, /, pos_or_kwd, *, kwd1, kwd2):`
        - `f("position 1", "position 2", "both ok", kwd1 = 1, lwd2 = 2)`
            - `pos` positional argument
                - Order matters, cannot be passed by keyword
            - `kwd` keyword argument
                - Order not matters, passed by keyword
        - Pass by
            - Position only, before `/`
            - Position or keyword
            - Keyword only, after `*`
        - Names of positinoal-only parameters can be used in keyword argument without ambiguity
            ~~~
            def foo(name, /, **kwds):
                return 'name' in kwds
            ~~~
- `pass` statement
- Recursion
    - Function can call itself
    
    ~~~
    results = []
    def tri_recursion(k):
        if(k > 0):
        result = k + tri_recursion(k - 1)
        results.append(result)
    else:
        result = 0
    return result

    tri_recursion(6)
    print(results)

    >>> [1, 3, 6, 10, 15, 21]
    ~~~

- Lambda expression
    - A small anonymous function, can take any number of arguments, but only one expression
    - `x = lambda a , b : a * b + 10`

    ~~~
    pairs = [(1, 'one'), (2, 'two'), (3, 'three)]  # tuple in list
    pairs.sort(key = lamdba pair: pair[1])  # sort key is by the first index of pair

    >>> [(1, 'one'), (3, 'three'), (2, 'two')]
    ~~~

    - Anonymous function inside another function

    ~~~
    def myfunc(n):
        return lambda a: a * n
    
    mydoubler = myfunc(2)
    mytripler = myfunc(3)

    print(mydoubler(11), mytripler(11))

    >>> 22 33
    ~~~

- Documentation strings
    - First non-blank line after the first line of string determines the amount of indentation for the entire documentation string.
    - `__doc__` to print documentation string

    ~~~
    def my_function():
        ''' Short, concise summary of the object's purpose.
        <BLANK>
        Description of the object. 
        '''
        pass

    print(my_function.__doc__)
    ~~~

- Function annotations
    - Optional metadata information
    - Store in `__annotations__` attribute of the function as a dictionary
    - Return annotations defined by `->`

    ~~~
    def f(ham: str, eggs: str = 'eggs') -> str:
        print("Annotations:", f.__annotations__)
        print("Arguments:", ham, eggs)
        return ham + ' and ' + eggs

    f('spam')

    >>> Annotations: {'ham': <class 'str'>, 'eggs': <class 'str'>, 'return': <class 'str'>}
    Arguments: spam eggs
    'spam and eggs'

    # return value also annotated
    ~~~

### Coding style

- [PEP8](https://peps.python.org/pep-0008/) - style guide for Python
- Do not mix tab and space
- Wrap lines so that they don't exceed 79 characters
- Use blank lines to separate
- Put comments on a line of their own if possible
- Use docstrings
- Use spaces around operators and after comma
- Name consistently
    - `UpperCamelCase`
    - `lowercase_with_underscores`
    - Always use `self` as the name for the first method argument

## Data structures

### Sequence

#### List

- Might contain items of different types
- Ordered, changeable, allow duplicate
    - `test = list((1, 2, 3))`
    - `test = [1, 2, 3]`
- Index and slice
    - Same as string
        - Left index included, right index excluded
    - Can assign new value to slice
        - `test[:1] = []` --> `[3]`
        - `test[:] = []` --> `[]`
- `in` & `not in` to check membership
- `len()` return the number of items
- Unpacking into variable
    - Add `*` to a vairable, if the number of variables is less than value
        - `(a, b, *c) = thisList`
        - `c` is a list
- List comprehension
    - <code>newlist = [<i>expression</i> for <i>item</i> in <i>iterable</i> if </i>condition == True]</code>
    - `newlist = [x.upper() for x in oldlist if x != "apple"]`
    - `[(x, y) for x in [1,2,3] for y in [3,1,4] if x != y]`
- List method   
    - Insert item
        - `insert(index, insertContent)`
            - `test.insert(1, 0)` --> `[1, 0, 2, 3]`
    - Append item at the end
        - `append()`: append item
            - `for x in list2: list1.append(x)`
        - `extend()`: append items from another iterable object: 
            - Iterable object: list, typle, set, dictionary
            - `list1.extend(list2)`
        - `+`: `list3 = list1 + list2`
        - `insert(i, x)`: `a.insert(len(a), x)`
    - Remove item
        - `remove(value)`: remove item
        - `pop(index)`: remove by sepcified index
            - `pop()` --> remove the last item
            - `popleft()` --> remove from left
        - `del` statement
    - Clear the list
        - `clear()` --> `[]`
    - Sort
        - `sort()`: sort alphanumerically
        - `sort(reverse  = True)`: sort reversely
        - `sort(key = myfunction)`: sort
            - `myfunction` return a number used to sort the list
            - Sort will be from the lowest to highest
            - e.g. `def myfunction(n): return abs(n - 50)`
                - `abs()`: absolute value
            - e.g. `thislist = sort(key = str.lower)`
        - Case sensitive: capital letters sorted before lower case letters
    - Reverse order of list
        - `reverse()`
    - Shallow Copy a list
        - `copy()`: `list2 = list1.copy()`
        - `list2 = list1[:]`
    - Count spec value in list
        - `count(value)`
    - Find
        - `index(item, start, end)`

- Shallow copy
    - Should not modify mutable input data
    - Should shallow copy `a = b[:]`instead of direct copy `a = b` (still referencing) 

#### Tuple

- Ordered, unchangeable, allow duplicate
    - `thisTuple = "a", "b", "c"`
    - `emptyTuple = ()`
    - `thisTuple = tuple(("a", "a", "b", True))`
    - `thisTuple = ("a",)` #need to have a comma to create one-item tuple
- Change tuple value by changing type to list

#### Set

- Unordered (unindexed), unchangeable (can remove or add items), no duplicate
    - `myset = set(("a", "b", 33.1))`
    - `myset = {"a", "b", 33.1}`
    - Duplicated item auto deleted/merged
- Set operations
    - `set('aboc') - set('abc') = {'o'}`
    - `set('ab') | set('ac') = {'a', 'b', 'c'}` # or
    - `set('ab') & set('ac') = {'a'}` # both
    - `set('ab') & set('ac') = {'b', 'c'}` # or but not both
- Set method
    - Add item
        - `add(value)`
    - Add any iterable
        - `update(mylist)`
    - Remove
        - `remove()`: if the item to remove not exist, `remove()` will raise ERROR
        - `discard()`: if the item to remove not exist, `discard()` will not raise ERROR
        - `pop()`: cannot spec index, can only remove the last item
        - `clear()`: empty set
        - `del()`: delete set completely
        - `del` statement
    - Join sets
        - `union(set2)`
        - `update(set2)`
    - Duplicates and differences
        - Keep duplicates
            - `set1.intersection_update(set2)`: keep duplicates and update `x`
            - `set3 = set1.intersection(set2)`: return a new set of duplicates
        - Keep all but duplicates
            - `set1.symmetric_difference_update(set2)`
            - `set3 = set1.symmetric_difference(set2)`
        - Items only exist in `set1` not `set2`
            - `set3 = set1.difference(set2)`
        - Whether two sets have a intersection or not
            - `isdisjoint()`
        - Whether `set2` is subset(part of)/superset(contain) `set1`
            - `set1.issubset(set2)`
            - `set1.issuperset(set1)`

#### Dictionary

- Ordered, changeable, no duplicate
    - Store data in key:value pairs
    - Any immutable object can be key
    - `thisdict = {"brand": "Cola", "year": 1998, "color": ["red, "yellow"]}`
    - `thisdict = dict([("brand", "Cola"), ("year", 1988)])`
    - `dict(year=1988, age=15)`
    - `x: x**2 for x in (2, 4, 6)`
- `list(dictionary)` returns a list of all keys
- `in` & `not in`: check if key exists
- Dictionary method
    - Get from dict
        - Get value
            - `thisdict["owner"] = "John"`
            - `thisdict.get("owner")`
            - `values()`: get list of all values
        - Get list of all keys
            - `keys()`
        - Get items
            - `items()`: return each pair of item as tuple in a list
    - Update item
        - `update({"year": 2020})`: must in key:value pair
    - Remove item
        - `pop("year")`
        - `del thisdict["year"]`
        - `clear()`: to empty dict
    - Copy
        - Copy cannot by `dict1 = dict2` - just a reference that changes auto following `dict1`
        - `copy()`
    - Set default value of key
        - `setdefault("color" : "white")`
        - If the key not exists, inser the key with the specified value
    - Create dict by specified keys and value
        - `dict.fromkeys(keys, value)`
        - `thisdict = dict.fromkeys(x, y)`
            - If value not specified: `None`
- Nested dict
    - Dict can contain dict as item value

### Looping techniques

>
> Loop through a list
>

~~~
thislist = ["apple", "banana", "cherry"]
for x in thislist:
    print(x)
~~~

>
> List comprehension loop
>

~~~
thislist = ["apple", "banana", "cherry"]
[print(x) for x in thislist]
~~~

>
> Loop through list index
>

~~~
thislist = ["apple", "banana", "cherry"]
for i in range(len(thislist)):
    print(thislist[i])
~~~

~~~
thislist = ["apple", "banana", "cherry"]
i = 0
while i < len(thislist):
    print(thislist[i])
    i += 1
~~~

## Modules

- A file containing Python difinitions and statements
    - `import module`
    - `from module import itemname as itemname2`
    - `from module import *`
    - `modname.itemname`
- Only imported once per interpreter session
    - Restart interpreter or `importlib.reload()`
- Run Python module
    - `python mod.py <arguments>`
    - Set `__name__` to `__main__`
        - Adding at start: `if __name___ == "__main__"`
- Module search path
    - Search for built-in module listed in `sys.builtin_module_names`
    - Search for `module.py` in a list of directories given by `sys.path`
        - `sys.path` intialized from
            - Directory containing input script
            - `PYTHONPATH`
            - Installation-dependent default
- Compiled modules
    - Python caches the compiled version of each moduile in the `__pycache__` directory under `module.version.pyc`
- Standard modules
    - Some built into the interpreter
- `dir()` function
    - `dir()` finds out which names a module defines, return a sorted list of strings
- Packages
    - A way of structuring Python's module namespace by using "dotted module names"

    ~~~
    sound/                          Top-level package
      __init__.py               Initialize the sound package
      formats/                  Subpackage for file format conversions
              __init__.py
              wavread.py
              wavwrite.py
              aiffread.py
              aiffwrite.py
              auread.py
              auwrite.py
              ...
      effects/                  Subpackage for sound effects
              __init__.py
              echo.py
              surround.py
              reverse.py
              ...
      filters/                  Subpackage for filters
              __init__.py
              equalizer.py
              vocoder.py
              karaoke.py
              ...
    ~~~

    - ` __init__.py` to make Python treat directories containing the file as packages
    - Import individual modules from package
        - `import sound.effects.echo`
        - `from sound.effects import echo`
        - Imported item can be submodule or package or name defined in the package
    - Importing * from package
        - First need to provide an explicit index of the package
            - Defined list of module names `__all__`
            - Imported when `*` encountered
            - Maintained and updated by package author
    - Intra-package references
        - Realtive imports
            - `from . import echo`
            - `from ..filters import equalizer`

## Input and output

- Output format
    - Formatted string literal (f-string)
        - Prefixed with `f`, replacement fields `{}`
            - <code>f'Hello, my name is {<i>name</i>.lower()}'</code>
            - `f"1 + (1 - 2) = {1 + (1 - 2)}"`
            - `f'''He\'ll say {"I'm Eric"}'''` --> `"He'll say I'm Eric"`
        - `=` can be added after expression, casues `repr()` by default
            - `foo = "bar"`
            - `f"{ foo = }"` --> `" foo = 'bar'" 
            - `f{foo:5}` --> `"bar  "`
            - Before `:` to indicate position int he arg list
            - After `:` to indicate min width of the field
        - Specify conversion
            - `!s` calls `str()` on the result
            - `!r` calls `repr()` on the result
            - `!a` called `ascii()` on the result
        - Format specifier `:`
            - Alignment
                - `:<` - left
                - `:>` - right
                - `:^` - center
                - `:=` - place sign to the left most position
                - Add int afterwards to spec available space for the value
            - Sign
                - `:+` - show + sign
                - `:-` - show - sign only
                - `: ` - use a space before positive number
            - Separator
                - `:,` - comma as thousand separator
                - `:_` - underscre as thousand separator
            - Number format
                - `:b` - binary format
                - `:c` - convert to unicode character
                - `:3d` - decimal format --> `  5`
                - `:e` - scientific format with lower case e
                - `:E` - scientific format with upper case E
                - `:.2f` - fix point number format --> `5.00`
                - `:o` - octal format
                - `:x` - hex format
                - `:.2%` - percentage format --> `5.00%`
    - `str.format()`
        - `full_name = "{} {}".format(first_name, last_name)`
        - `print("{1} and {0} and {0[other]:.2f}").format("a", "b", other = 3))` --> `"b and a and 3.00"`
            - `[]` to access the key
        - Passing `table` dictionary by `**`
            - `print('Jack: {Jack:d}; Sjoerd: {Sjoerd:d}; Dcab: {Dcab:d}'.format(**table))`
    - Old printf-style string formatting
        - `%`: string formatting or interpolation operator
        - `%(language)s has %(number)03d quote types' % {"language": "python", "number": 2}` --> `"pyhon has 002 quote types"`
            - `(language)`: mapping key, optional
            - `0`: conversion flag, optional
                - <img src="https://raw.githubusercontent.com/zoe-gif/images/master/20220710235621.png" width="600" height="">
            - `3`: minimum field width, optional
            - Precision `.2`, optional
            - Length modifier, optional
            - `d`: conversion type
                - <img src="https://raw.githubusercontent.com/zoe-gif/images/master/20220711000041.png" width="600" height="">
    - `str.rjust()`
        - Padding string with spaces on the left
        - `str.ljust`, `str.center`
    - `str.zfill()`
        - Pad a numeric string on the left with zeros

- Reading and writing files
    - `open(filename, mode, encoding=None)`
        - `r` to read only (defualt)
        - `w` to write only
            - Existing file with the same name will be erased
        - `a` to open the file for appending at the end
        - `r+` to read and write
        - `b` to open in binary mode
    - Close file
        - `with` to properly close file after finish
            - `with open('workfile') as f: read_data = f.read()`
        - `f.close()` # not recommended
    - Method of file objects
        - `read()`
            - Read entire by default
            - `read(size)`
        - `readline()`
            - Or `print line for line in f`
            - `list(f)` or `f.readlines()` to read all lines
        - `write(string)`
            - Convert object to string or bytes
                - `f.write(s)`
        - `tell()`
            - Tell the file object's current position
        - `seek(offset, whence)`
            - To change the file object's position
            - `whence` reference point
                - `whence == 0` (default): beginning of the file
                - `whence == 1`: current file location
                - `whence == 2`: end of the file
                - If text files, only refer to the beginning of the file allowed
    - `json` to save structured data
        - `json`: javascript object notation
        - Serializing: take Python data hierarchies and convert to string
        - Deserializing: reconstruct data from string
        - `json.dumps(object)` to view json string
        - `json.dump(object, text_file)` to serialize to text_file
        - `json.load(text_file)` to decode

- `print()`
    - `print(*objects, sep=' ', end='\n', file=sys.stdout, flush=False)`
    - `*object`: objects to be printed
    - `sep = '\n'`: separator between printed objects
    - `end = '@'`: print `@` at the end
    - `file`: specify the output file (console by default)
    - `flush`: flush the stream/file forcibly if set `True`


## Errors and exceptions

- Syntax errors
- Exceptions
- Handling exceptions
    - `try` & `except`
    - `except` can have multiple lines, order matters

    ~~~
    while True:
        try:
            x = int(input("enter a number:"))
            break
        except (ValueError, TypeError):
            print("try again")
    ~~~

- Raise exceptions
    - `raise` statement: force a speficied exception to occur
- Exception chaining
    - Optional `from` enables chaining exceptions
    - Disabled by `from None`
- User-defined exceptions
- Define clean-up actions
    - `finally` executes the last task before `try` completes
    
    ~~~
    def divide(x, y):
        try:
            result = x / y
        except ZeroDivisionError:
            print("division by zero!")
        else:
            print("result is", result)
        finally:
            print("executing finally clause")

    >>> divide(2, 1)
    result is 2.0
    executing finally clause

    >>> divide(2, 0)
    division by zero!
    executing finally clause

    >>> divide("2", "1")
    executing finally clause
    Traceback (most recent call last):
    File "<stdin>", line 1, in <module>
    File "<stdin>", line 3, in divide
    TypeError: unsupported operand type(s) for /: 'str' and 'str'
    ~~~

- Predefined clean-up actions
    - `with`

    ~~~
    with open("myfile.txt") as f:
    for line in f:
        print(line, end="")
    ~~~

## Classes

- Class
    - Class creates a new type of object
    - Class instance can have attributes and methods
    - Base class and derived class
- Attribute
    - `object.attribute`
    - Read-only or writable
        - `del object.attribute`
- Namespace
    - Mapping from names to objects
    - Types
        - Built-in namespace
            - Created when Python intepreter starts up
            - Never deleted
        - Global namespace
            - Created when module definition is read in
            - Deleted until interpreter quits
        - Local namespace for a function
            - Created when function is called
            - Deleted until function returns
- Scope
    - Textual region of a Python program where a namespace is directly accessible
    - Types
        - Innermost scope
            - Searched first
            - Contain local names
        - Scope of any enclosing functions
            - Searched from the nearest enclosing scope
            - Contain non-local but also non-global names
        - Next-to-last scope
            - Contain the current modules's global names
        - Outermost scope
            - Searched last
            - Contain built-in names
- `global` and `non-local` statement
    - `global`: variable lives in the global scope
    - `nonlocal`: variable lives in an enclosing scope

## Standard library

## Virtual environments and packages


## Uncategorized


- `eval()`: if the expression is legal python statement, it will be executed
- `repr`()`: return a string containing a printable representation of an object
- `variable = input('enter the value')`
- `map(function, iterable)`: execute function for each item in iterable
    - Multiple variables: `map(function, list1, list2)`
- `reversed()`: function of method `reverse`
- `sorted()`: function of method `sort`
- `min()`: return lowest value in an iterable
- `sum()`: return sum of all in an iterable
- `import math`
    - `math.sqrt()`: square root
- `bin()`: return binary value start with `0b`
- `zip(iterator1, iterator2, iterator ...)`: zip iterator together
- `enumerate(iteratble, [start])`: return as an enumerate object
    - `enumerate(['a', 'b'])` --> `[(0, 'a'), (1, 'b')]`
- `vars()`: return a dictionary containing all local variables
- `round(number, number of digits)`: round up
- `p = p//1`: round down to integer
- `re`
    - [regular expression operations](https://docs.python.org/3/library/re.html)
    - **********to be read*************
- `ord`: return the int that represents string
- `enumerate(iterable, start=0)`: add counter to iterable and return
- Import alpha

~~~
import string
alphabet_lower = list(string.ascii_lowercase)
alphabet_upper = list(string.ascii_uppercase)
~~~

- `yield` keyword
    - Suspend a function's execution and send a value back to the caller