[[1 - What are Copy Semantics]] <- Back

---
## What is a Deep Copy?
Any data members that are deep copied result memory being newly allocated and only owned by the class that has copied from another one.
- Avoids double delete bugs

```c++
AClass(const AClass& other):
data(new AClass(*other.data)){

}
```
