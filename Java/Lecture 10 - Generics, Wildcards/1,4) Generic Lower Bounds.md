[[1,1) Generics]] <- Back

A lower bound, for a type parameter, can also be specified.
- By specifying a class as a lower bound, it means that the type parameter cannot be specified to be a sub classes of the lower bound class.
- Only the lower bound class, or super classes of the lower bound class, can be specified as the type parameter.

```java
class A1(T super RequiredClass)
```

super is used instead of extends.