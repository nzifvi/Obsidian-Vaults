[[5) Loops and Lists]] <- Back

---
## List Comprehension
List comprehension offers shorter syntax, plus a lot of control, when creating a new list based on the values of an existing list.

E.g:
- Based on a list of numbers, you can create a sublist of only the negative integers found in the original list.

WITHOUT list comprehension, the above can still be done, but you would need a list, and a new empty list, and a for loop which checks using conditionals, sometimes many, and then appending, or inserting, to the new list.

List comprehension can reduce all of this into one line of code.

```python
balancePerMonth = [100, -100, 100, -200, -50, 100]
negativeBalances = []

for arr in balancePerMonth:
	if arr < 0:
		negativeBalances.append(arr)
print(negativeBalances)
```

```output
[-100, -200, -50]
```

Instead, using list comprehension, all of this is turned into...

```python
balancePerMonth = [100, -100, 100, -200, -50, 100]
negativeBalances = [arr for arr in balancePerMonth if arr < 0]

print(negativeBalances)
```

```output
[-100, -200, -50]
```

## List Comprehension Syntax

```python
newList = [expression for item in iterable if condition == True]
```

#### 1) expression

the expression is what is stored in the newList. It is the item or a transformation to the item.
- for the expression, you can pass the item to a function and the return of that function would then be the expression.

The expression is what will be appended into the new list.


```python
newList = [expression**2 for item in iterable if condition == True]
```



#### 2) item

The item is each element, that matches the condition specified, from the iterable used.

#### 3) iterable
iterable is the iterable container that is the old list.
- can be list, tuple, set, etc.

#### 4) condition
condition is the logical statement used to filter all elements of the old list to see if they are an item of the new list or not.


