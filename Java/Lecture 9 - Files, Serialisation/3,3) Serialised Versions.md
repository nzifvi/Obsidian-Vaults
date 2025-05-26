[[3,2) Serialisation]] <- Back

---

When loading a serialised object from file, Java requires it to be compatible with the expected class the program has been programmed to receive.

- Java automatically creates an ID for a class to help identify compatible classes.

- Changes to the class definition, or to the compiler, may cause class cast exceptions.

The ID of a class can be controlled via the program, as opposed to the Java VM deciding for you.

```java
public class Test{
    private static final long serialVersionUID = "1";
}
```

the final datatype variable is the ID for any instances of this class.
	- REMEMBER TO UPDATE THE UID if the class fields change.