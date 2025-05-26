[[1,1) Generics]] <- Back

---
## What is the Number Class?
Number class = super class of Integer, Double, etc.
- Note: Number is an abstract class.

Using generics, the following class can be created...
```java
class MyUtils {
	public static double sum(ArrayList<Number> list){
		double sum = 0.0;
		for(Number n : list){
			sum += n.doubleValue();
		}
		return sum;
	}
}
```

Suppose that class is then attempted to be used:

```java
ArrayList<Integer> list = new ArrayList<Integer>();

list.add(1);
list.add(2);
list.add(3);

double sum = MyUtils.sum(list);
```

The above will not compile.
	Error message will be:
	 java: incompatible types: java.util.ArrayList<java.lang.Integer> cannot be converted to java.util.ArrayList<java.lang.Number>

Meaning: Integer is not a subtype of Number, even though it is.

Explanation:
- Polymorphism would allow things to be broken.
- If ArrayList<.Integer> was allowed to be a subtype of ArrayList<.Number> then the following broken (during compilation time) could  work.

This problem can be fixed using Bounded Polymorphism and Wild cards

