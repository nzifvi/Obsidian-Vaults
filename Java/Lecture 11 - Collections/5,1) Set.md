[[4,1) List]] <- Back
[[6,1 Map]] <- Next

---
## Set
Set is another interface which extends Collection.
- Comes from java.util.Set<.E>

Set = a collection which has NO duplicate elements.
- For any two elements e1, e2, in a set... e1.equals(e2) will be false.
- .equals() checks the equality of objects in memory, using hashCode(). If e1 has the same memory address as e2, they will be deemed as equivalent.
- .equals() can be overridden to check for equality in object's fields rather than memory addresses.

Set is implemented by EnumSet, HashSet, and TreeSet.