[[1,1) Generics]] <- Back

---

## Declaring a Generic Method
Using n type parameters, a generic method can be created...

```java
public <K>
K getElement(ArrayList<T> arr, int index){
	//code here
}
```

## Calling a Generic Method
Often, the datatypes of the parameters of the method call are used to specify the datatype of the type parameter
- Meaning: the data type the type parameter should adopt is not required to be specified. It is interpreted from the datatype of the parameter in the method call.

```java
ArrayList<String> arr = new ArrayList<>();
//elements added to arr...
System.out.println(getElement(arr, 4));
```
