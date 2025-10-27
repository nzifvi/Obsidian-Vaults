[[1) Reading CSV into DataFrame]] <- Back

---
## How to Read a JSON string into a DataFrame
Two possible ways:
1) Read in JSON file
2) Read in JSON from Python Dictionary 

### 1) Read in JSON file
Can read in a json file, via the `pd.read_json()` function member of pandas object.
- Requires filePath argument on function call.

```python
df = pd.read_json('data.json')
```

