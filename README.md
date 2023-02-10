# Python Fundamentals

---


**Python standard library manual, or run a `help(name)` or `dir(name)`**

```python
help(list)
```

---

- **Data** **types**:
    - Text Type: `str`
    - Numeric Types: `int, float, complex`
    - Sequence Types: `list, tuple, range`
    - Mapping Type: `dict`
    - Set Types: `set, frozenset`
    - Boolean Type: `bool`
    - Binary Types: `bytes, bytearray, memoryview`
- Python an object’s memory space is automatically re- claimed as soon as the object is no longer referenced anywhere in the program.
- **Strings**: Like many other popular programming languages, strings in Python are arrays of bytes representing unicode characters. However, Python does not have a character data type, a single character is simply a string with a length of 1. Square brackets can be used to access elements of the string. They are - *“immutable sequence”*
    1. Difference between single and double quotes in python strings ?
        
        They are same. The reason for supporting both is that it allows you to embed a quote character of the
        other variety inside a string without escaping it with a backslash.
        
    2. Backslashes are used to introduce special byte codings known as *escape sequences*.
    3. Null doesn’t terminate a string in python instead, Python keeps both the string’s length and text in memory
    4. Raw string: If the letter r (uppercase or lowercase) appears just before the opening quote of a string, it turns off the escape mechanism. 
    5. The print statement provides a more user-friendly format that shows that there is actually only one backslash in each spot. And python itself uses double slash scheme. *see 📝* 
    6. **Block String:** Single and double quotes embedded in the string’s text may be, but do not have to be, escaped— the string does not end until Python sees three unescaped quotes of the same kind used to start the literal.
    7. Strings can be concatenated using the + operator and repeated using the * operator
    8. The step is added to the index of each item extracted. The full-blown form of a slice is now X[*I*:*J*:*K*], which means “extract all the items in X, from offset *I* through *J*−1, by *K*.”
    9. The `repr` function (and the older backquotes expression, removed in Python 3.0) also converts an object to its string representation, but returns the object as a string of code that can be rerun to recreate the object.
    10. `chr` - taking an ASCII integer code and converting it to the corresponding character, `ord` this returns the actual binary value of the corresponding byte in memory
    11. The method call expression *object*.*method*(*arguments*) is evaluated from left to right—Python will first fetch the *method* of the *object* and then call it, passing in the *arguments*
    12. ***String formatting expressions :*** The original technique, available since Python’s inception; this is based upon the C language’s “printf” model and is used in much existing code.
        
        ```python
        print('That is %d %s bird!' % (1, 'dead'))
        # Dict can aslo be used to formate
        print(print('I am %(name)s of age %(age)s '%{'name': 'Bob', 'age': 40})
        ```
        
    13. ***String formatting method calls:*** A newer technique added in Python 2.6 and 3.0; this is more unique to Python and largely overlaps with string formatting expression functionality. *see 📝* 
        - `format()` - build-in function
            - strings are immutable, so format really *must* make a new object. It can name object attributes and dictionary keys—as in normal Python syntax, square brackets name dictionary keys and dots denote object attributes of an item referenced by position or keyword.
            
            ```python
            template = '{0}, {1} and {2}'
            print(template=template.format('spam', 'ham', 'eggs'))
            ```
            
            - For the formatting method, we use a colon after the substitution target’s identification, followed by a format specifier that can name the field size, justification, and a specific type code. `{*fieldname*!*conversionflag*:*formatspec*}`
                - *`fieldname`* is a number or keyword naming an argument, followed by optional “`.name`” attribute or “`[index]`” component references.
                - *`conversionflag`* can be r, s, or a to call `repr`, `str`, or `ascii` built-in functions on the
                value, respectively.
                - *`formatspec`* specifies how the value should be presented, including details such as field width, alignment, padding, decimal precision, and so on, and ends with an optional data type code. `[[*fill*]*align*][*sign*][#][0][*width*][.*precision*][*typecode*]`. *See 📚*
- Files - After calling open, you can transfer strings of data to and from the associated external file by calling the returned file object’s methods. Optional third argument can be used to control output buffering—passing a zero means that output is unbuffered.
- Referencing - Python mutable objects make references
    1. `copy` -  we can explicitly  copy an object
        1. Slice expressions with empty limits (L[:]) copy sequences. (*Don’t copy the deep nested parts*)
        2. The dictionary and set copy method (X.copy()) copies a dictionary or set. (*Don’t copy the deep nested parts*)
        3. Some built-in functions, such as list, make copies (list(L)). (*Don’t copy the deep nested parts*)
        4. The copy standard library module makes full copies.
- `is` - operator tests for identity. In case of string sit may act unusual as strings internally caches
- Non empty objects and non zero numbers are true
- `None` - build-in real object with memory
- Cyclic object - If a collection has reference to itself. python prints `[...]`
- Encodings - rules for translation strings to sequence of bytes to storre in memory
    1. ASCII - 0-127 , trivial translation process
    2. Latin 1  - 0-255 ,  trivial translation process
    3. Unicode - 2 byte , complex processs