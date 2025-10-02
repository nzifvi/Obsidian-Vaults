[[1) Using JSON in Python]] <- Back

---
## Formatting JSON strings
Via the `dumps()` function member, a JSON string can be formatted to be easier to read.
- `dumps()` has additional parameters passed on call to format the JSON string.

```python
json.dumps(strVar, indents, seperators)
```

- indents defines the amount of indentation.
- separators is a set of characters used to delimit the attribute name from the value.

Can also sort the keys via letting a parameter called sort_keys equal True