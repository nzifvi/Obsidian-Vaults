[[2) Accessing List Items]] <- Back

---
## Adding to and Removing from Tuples
Whilst tuples are unchangeable after their items have already been defined, there is a way to work around them being unchangeable.

Do this by converting the tuple into a list and assigning it to a variable:

```python
aTuple = (1, 2, 3)
y = list(aTuple)
```

perform the change required...

```python
y.append(3)
```

And then convert the list, with the change, and assign it to the original tuple variable.

```python
aTuple = tuple(y)
```

