[[2) Formatting JSON Strings]] <- Next

---
## How to use JSON in Python
Must import `json` library.

## Loading in a JSON file
To load in a JSON file do...

```python
import json

x = # suppose JSON file was read in

dataJSON = json.loads(x) # loads the JSON file into a python JSON object which can be used to retrieve values from given an attribute.

valueJSON = dataJSON["attributeName"]
```

- JSON object parses the given JSON file, puts it into a key value map.
- Given the key (the JSON attribute), JSON object returns corresponding value.

## Converting Strings into JSON strings for saving
A python object, such as a string, can be converted into JSON using the `dumps()` function member.
- object should return a string in JSON format.

```python
import json


str = { # turning dictionary into JSON string (dictionaries good for JSON strings)
	"attribute1", "value1",
	"attribute2", "value2",
}

# JSON string is then passed as an argument to the dumps() function member of json object...
strInJSON = json.dumps(str);

```