[[2 - JSON Types]] <- Back
[[4,1 - JSON with C++]] 
[[4,2 - JSON with Java]]

---
## JSON Files
Any of the given data types ([[2 - JSON Types]]), when put into a file with a .json file type, is valid JSON.
- JSON is obviously used in a more complex way, storing entire objects.
- In JSON file, most likely the start of a JSON file will be arrays and objects.

To create an object in JSON, use braces to define an object.
```json
{

}
```
- All data within the brackets treated as data of that object.

The data of objects come in key value pairs.
- Key denotes the name of the data.
- Data is self-explanatory (value of that name).

```json
{
	"name": "duck"
}
```
- Key must be surrounded by double quotes, then a colon, and then the value.
- If multiple key value pairs, separate them using commas.

```json
{
	"name": "Duck",
	"age": 42
}
```

- FINAL key: pair value must not have a closing comma.
### JSON Arrays
An array can be defined in JSON as a key value pair.
```JSON
{
    "carBrands": ["BMW", "Porsche", "Audi"]
}
```
Or by itself.
```JSON
["BMW", "Porsche", "Audi"]
```

To define an array, encase the contents within square brackets and separate each element with a comma.

Arrays can also store objects.
```JSON
{
	name: "Kyle",
	age: "500",
	"friends": [
	{
		name: "Joe",
		"age": "10",
		"friends": [...]
	}]
}
```