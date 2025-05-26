[[7,1) Copies]] <- Back

---
## Shallow Copies
Shallow copies ensure a new collection, or object, is returned INSTEAD of an alias, or a new collection or object that contains an alias when it should not have.

### Shallow Copies for Collections
- All Data Structures which implement Collection, or a sub-implementation of Collection, come with a method...

```java
addAll(Collection<? extends E> c)
```

The data structures which come with this method usually have a constructor which behaves in the same way.

This method, and the similar constructor, creates a new collection instead of an alias.
- Allows the two collections, one being a copy of a prior collection, to be independent.
- Changes can be made without the changes occurring in the other.
- If the size of 1 collection changes, the other does not.


HOWEVER, if a change occurs to an element that existed in the object a copy was made of, that change will also occur in the copy
- Because it is the container that was copied, NOT the elements of the container.
- Consequently, aliases can still exist, pointing to the same memory address, between a container and a copy of a container.
- This is referred to as shallow copying.
- An object, which is produced via shallow copying another object, is referred to as a shallow copy of an object.


#### Example of Shallow copying of Collection...
```java
ArrayList<Coordinate> firstList = new ArrayList<>();

firstList.add(
	new Coordinate(1.0, 0.0)
);
firstList.add(
	new Coordinate(2.0, 0.5)
);
firstList.add(
	new Coordinate(3.0, 0.0)
);

ArrayList<Coordinate> secondList = new ArrayList<>();
secondList.addAll(firstList);

secondList.get(0).updateXOrdinate(4);
```
OUTPUT
```
firstList = {(4.0, 0.0), (2.0, 0.5), (3.0, 0.0)}
secondList = {(4.0, 0.0), (2.0, 0.5), (3.0, 0.0)}
```

Because, during the shallow copying process, ANY elements will be copied to the shallow copy of a collection, aliases are created.
- Changes made to the elements that are aliases are reflected across all collections containing aliases pointing to the same memory address.

### Shallow Copies for Objects
Objects, from their shared parent class Object, are provided a method...
```java
clone()
```

Clone returns a shallow copy of an object. All fields are copied.
- Primitive references will be new values in memory.

However...
- Any object references, or array fields, will be copied as aliases.


###### CLONE IS USUALLY AVOIDED. IT IS NOT A GOOD IDEA.