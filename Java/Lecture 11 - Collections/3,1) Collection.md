[[2,1) Arrays]] <- Back
[[4,1) List]] <- Next

---

## What is Collection?
Collection is an interface which most data structures extend.
- Collection is a super class for multiple data structures in Java that are provided via libraries.
- Each of the data structures, provided by Java, have their own unique properties. 
- However, they will tend to share common interfaces.

Collection is a root interface of the collection hierarchy.
- It has no direct concrete implementation.
- Represents a group, aka a collection, of objects.
- Unordered collection classes implement the Collection interface.

## Collection Interface
Collection is an interface, it has multiple abstract methods.
- Note: abstract methods have no definition, they are only a declaration.
- The class which implements the interface must provide a definition by overriding the abstract method

#### boolean add(E e)
Intended to add an item to an unordered collection.
- Returns a boolean value as a signal to inform of result of add() operation (true if success, false is failure).

#### void clear()
Used to clear all items from a collection.

#### boolean contains(Object o)
Used to check if Object o is a member of the unordered collection. Returns a boolean value to indicate result.
- True if o is a member of the unordered collection.
- False if otherwise.

#### Iterator<.E> iterator()
[[3,2) Iterator]]

#### boolean remove(Object o)
Used to remove an Object o from the unordered collection. Returns a boolean value to indicate the result of the operation.
- True if o removed.
- False if o not removed OR if o is not a member of the unordered collection

#### int size()


