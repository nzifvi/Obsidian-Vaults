
---
## F-Strings
F-Strings are a special type of string variable which allow for part of a given f-string to be formatted.

F-strings are declared during the definition of a string variable.
- Affix f before the string literal to define an f-string.

```python
str = f"something here i do not know"
```

To modify an f-string, placeholders and modifiers are used.
- Placeholders indicate a variable previously defined in a scope of the program.
- Encase the placeholder with curly braces

```python
var1 = 59
str = f"Rate of engine: {var1}"
print(str)
```
- Will substitute in the value of var1 into

Modifiers can be appended to the placeholder via a colon at the end.
- Allows formatting of placeholder to be changed (cutting off at given decimal place, etc)

```python
var1 = 59
str = f"Rate of engine: {var1:.2f}"
print(txt)
```

Can also perform operations, logical conditions, etc in the placeholder.
- Can also execute functions in the placeholder