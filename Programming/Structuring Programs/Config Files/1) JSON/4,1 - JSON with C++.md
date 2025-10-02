[[3 - JSON Files]]

---
## How to use JSON with C++
To read, and handle, JSON files in C++ a library called nlohmann/json C++ library must be used.

nlohmann/json library allows for...
- json files to be read easily into a C++ program.
- C++ programs to CREATE a json file.

### Reading a JSON file into a C++ program.
Assumption 1: nlohmann/json library is available to program and FULLY works.

#### From json file

The parse function, in nlohmann namespace, takes a file that is in read mode and constructs a JSON object with the data from the JSON file, returning it.
```c++
#include <fstream>
#include <nlohmann/json.hpp>

std::ifstream file("fileName.json");
//perform validation on file, ensure no issues.

nlohmann::json jsonData = nlohmann::parse(file);
```

#### From JSON literals
A JSON object can be initialised, with data, via literals.
- literals = hard coded into the source code.
- still uses parse function.

```c++
#include <nlohmann/json.hpp>

nlohmann::json jsonData = nlohmann::parse(
	R"(
	{
		"name": "Duck",
		"age": 12
	}
	)"
);
```

### Accessing data within a JSON object
Assumption 1: nlohmann/json library is available to program and FULLY works.

JSON class was designed to function like an STL container (vector, etc).
- Can access the elements, once the initialised, within a nlohmann::json object.

#### nlohmann::json arrays:
Functions like the vector class.
```c++
nlohmann::json jsonVec;

jsonVec.push_back(12);
jsonVec.push_back("hello);

// can iterate over the array using a for loop:
for(nlohmann::json::iterator it = jsonVec.begin(); it != jsonVec.end(); ++it){
	// iterate over the array.
}

// can also use for-each loops:
for(auto& element : jsonVec){
	// iterate over the array.
}
```

Other function members of the nlohmann::json array class exist...
1) .size()
2) .empty()
3) .type()
4) .clear()
#### nlohmann::json objects:
```c++
nlohmann::json jsonObj;
// no data members added yet.

// can add data members by...
jsonObj["key"] = value;

// can iterate over the nlohmann::json object class the same as the arrays (shown above).

// can remove a data member previously added using the .erase("key") function member.
jsonObj.erase("key");
```

## Serialising and De-serialising JSON
#### Serialising 
A given data-type can be serialised into it's JSON equivalent implicitly, without any additional steps:
```c++
int xVelocity = 42;
nlohmann::json j = xVelocity;
```

To serialise user-defined data types, such as a struct or object, you have to serialise each data member all the way down to the built-in data types data members.

```c++
class Person{
private:
	int         age;
	std::string name;
public:
	// constructors and encapsulation methods
}

Person p1(12, "Johan");

nlohmann::json j;
j["name"] = p1.getName();
j["age"] = p1.getAge();
```

To serialise a user-defined data type like how built-in data types are, you must declare and define two functions that specify HOW to serialise the user-defined data types.
- Done to reduce the amount of duplicate code and make code cleaner.

```c++
void to_json(json& j, const Person& p){
	j = json{
		{"name", p.getName()},
		{"age", p.getAge()}
	};
}
```

Now, when nlohmann json constructor is called when the user-defined datatype Person is assigned to a nlohmann:json object, it will call the custom defined to_json method.

This allows for...
```c++
nlohmann:json j = Person(12, "Johan");
```

#### De-serialising
When de-serialising (converting a JSON variable into it's built-in, or user-defined, data type equivalent), only explicit conversion can be used.
- Implicit conversion, a = b, is not safe.

To de-serialise a built-in data type...
```c++
auto s2 = js.template get<dataType>();
```
- Must be able to determine the datatype the JSON variable is.

To de-serialise a user-defined data type...

1) De-serialise all of the built in data types of the user-defined data type sequentially

```c++
Person p(json["age"], json["name"]);
```

2) Declare and define from_json which handles the process of explicitly converting to the user-defined data type.
	- Best done by saying from_json is a friend of the user-defined class it works with. Not required if de-serialising to a struct.

```c++
class Person{
private:
	int age;
	std::string name;
public:
	friend void from_json(const nlohmann::json& j, Person& p);
}

void from_json(const nlohmann::json j, Person& p){
	j.at("age").get_to(p.age);
	j.at("name").get_to(p.name);
}
```

This then allows for

```c++
Person pObj1 = js.template get<Person>();
```

## Writing a JSON object to file
Using the ofstream library, which allows for a file to be created, a JSON object/array can be saved to a file and later accessed.
- Saves in correct JSON syntax.

Suppose a nlohmann::json object is created...
```c++
nlohmann::json configFile;

configFile["filtersFilePath"] = "...";
configFile["biasesFilePath"] = "...";
configFile["learningRate"] = 0.5;
configFile["filterNo"] = 1;
configFile["filterZDimension"] = 3;
configFile["filterYDimension"] = 500;
configFile["filterXDimension"] = 500;

// first, create an ofstream object with a new file which will store the nlohmann::json object created

std::ofstream file(filePath); // ensure it has a .json file type
file << configFile.dump(4);

file.close();
```

.dump function member of a nlohmann::json object converts JSON into an std::string, enabling it to be saved in a file in the correct content and later parsed correctly too.
- .dump() takes a singular argument controlling how the json file created will be formatted.
	- If passing int argument, indents will be of that amount.
- .dump() can also return a std::string equivalent of the JSON to std::cout buffer for console printing.
- can assign the std::string return value of .dump() to a std::string variable.