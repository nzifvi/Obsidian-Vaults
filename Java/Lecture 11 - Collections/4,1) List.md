[[3,1) Collection]] <- Back
[[5,1) Set]] <- Next

---

## What is List?
List is another interface that extends Collection
- Comes from java.util.Set<.E>
```java
interface List extends Collection{

}
```

Meaning that the methods, which are part of the Collection interface, are also part of the List interface.


## Methods of List Interface

#### All methods part of Collection, plus...

#### boolean add(int index, E, e)
Used to add an item of data type E at position specified by index.
- Returns true if success.
- Returns false is failure.

#### int indexOf(Object o)
Used to search a List for an Object o, returning an int which is the index where Object o was found.
- Returns -1 if not found.
- Returns the value of the index Object o was found at if Object o was found.

#### ListIterator<.E> listIterator()
ListIterator is a specialised iterator that provides 2 ways of traversing a list (backwards and forwards).

#### boolean remove(int index)
Removes an element of a list which is at an index specified by the index parameter.
- Returns true if element was found and removed.
- Returns false if element cannot be found and or was not removed.