[[3 - JSON Files]] <- Back

---
## JSON with Java
Like C++, Java does not provide a built-in way to handle JSON file types. A library must be used.
- Gson is a java library which enables JSON file types to be handled.
- Gson is simple to use.

Handling JSON with Java, especially with the Gson library, is a much easier and more simple process than how it has to be done in C++
- A lot of the processes in C++ which have to be implemented by programmer are done automatically behind the scenes.

## Serialising and De-serialising Primitives
A gson object, once initialised, can be used to...
1) Turn a primitive data type into JSON string format.
2) Turn JSON data into it's primitive type again.

```Java
Gson gsonObj1 = new Gson();

gsonObj1.toJson(1);
gsonObj1.toJson(2);
```

toJson function member, given a primitive data type, will append the passed argument and add it to a string which is formatted as a JSON file.

To de-serialise...
```Java
dataType varName = gsonObj1.fromJson("key", dataType.class);
```

fromJson function member takes 2 arguments and will ultimately return the expected value, in the specified form (dataType).
- argument 1: key, encased within "" as everything is stored in one large string within the Gson object.
- argument 2: the class to convert the JSON substring to before returning it.