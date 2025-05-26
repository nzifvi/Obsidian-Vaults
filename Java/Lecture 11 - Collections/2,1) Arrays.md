[[1,1) Grouping Data]] <- Back
[[3,1) Collection]] <- Next

---
## Array Properties

Arrays are a fixed data structure and are declared as such
```java
int[] arr = new int[arraySize];
```

All items in an array MUST share the same data type.
- Can use subtyping (putting sub classes of a class into an array of the super class).

If using objects in an array, ensure that they are initialised
- Assign an index of an array an initialised object.
OR
- Use a loop to initialise all indices.

Elements of an array are accessed via their index number
- Valid indices are between 0 and array.length - 1


## When to use Arrays
Recall, static arrays are used when the size of a structure is fixed and known on creation
- Dynamic arrays allow for a variable size that can increase/decrease during runtime

When the data, being stored in the array, can be modelled as an n-dimensional table, use arrays.

Arrays are efficient for random, or sequential, access to data.
- Can search by random index, as long as index is validated to be 0 <= index < array.length