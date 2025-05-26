[[1) Zipping]] <- Back

---
## Unzipping
A zip can be unpacked after whatever has gone into it has been zipped.

```python
aList = ['a', 'b', 'c']
bList = [1, 2, 3]
zipped = [x for x in zip(aList, bList)]

characters, numbers = zip(*zipped)
```

\* performs argument unpacking, which uses the elements of the list of tuples as individual arguments.
- assigns all items of tuples x[0] to first variable, characters in this case, and so on for all items of each tuple in the zipped list.


