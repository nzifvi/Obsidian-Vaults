[[5,1) Set]] <- Back
[[7,1) Queue]] <- Next

---
## Map
Map is an interface, for containers, that maps a key to a value.
- Each element of a map is a 2-tuple of (key, value).
- Not an indexable data structure. A value is accessed by it's key.

Maps come from java.util.Map<K, V> package.
- K, V are type specifiers. The data type they later become, once specified, does not have to be the same.

A key is used to look up a value
- At most one value per key.
- At minimum, no value per key (meaning no value has been found that has a key with the one passed as a parameter).

The order of a map is defined by how the interface is implemented...
- Arrays.
- Trees.
- Hash map
- etc...

Map is implemented by ArrayList, LinkedList, Vector, Stack.

## Map Interface Methods
Recall that any map has <K, V> type parameters.
- K is the key.
- V is the value.

#### V get(Object k)
get() searches the Map for a key value k and returns it if found. Otherwise, an exception is thrown or a null value is returned.

#### V put(K key, V value)
Put is used to insert a new item with a key and value into a map.
- If there is already an item with a key equivalent to the key parameter passed, put() replaces the already existing item and returns the old item with an equivalent key.
- If there is no item with a key equivalent to key parameter passed, put() inserts the item and returns null.

#### V remove(Object k)
remove() is used to remove, and return, an item which has a key equal to k.
- Returns the item after removing it if an item with a key equal to k is found.
- Returns null if, after searching the Map, an item with a key equal to k cannot be found.

#### int size()
size() returns the number of elements currently part of the Map as a primitive integer value.+

#### Set<.K> keySet()
keySet() returns all of the keys a Map has as a Set.
- Returns as a Set due to the fact that there cannot be duplicates of keys.

#### Collection<.V> values()
values() returns a collection of values that are a part of the Map.

#### boolean containsKey(Object k)
containsKey() searches the key set of a map for a given key.
- Returns true if key k is a key in the map.
- Returns false if key k is NOT a key in the map.

#### boolean containsValue(Object v)
containsValue() searches the values of a map for a given value v.
- Returns true if value v is a part of the map.
- Returns false if value v is NOT a part of the map.