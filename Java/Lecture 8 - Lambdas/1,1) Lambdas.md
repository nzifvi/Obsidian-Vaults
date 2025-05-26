---
Lecture8:
---

[[4,1) When is Inheritance good]] <- Back

---

### What are Lambdas?
Lambdas are inline methods, aka functions, that ONLY EXIST, in the scope they are defined.
- Good to use when a block of code is used multiple times but ONLY in one method.

Lambdas have no name, they are just a set of input parameters followed by the code block that the lambda uses.

NOTE:
- Lambdas can either be an expression or an entire code block.
	- If an expression, they have to immediately return a value
	- If a code block (encased within { }), you can use conditionals, loops and, when or if you desire to return a value, put it at the end.


### Defining a Lambda
```java

class Example{
    public void exampleFunc(){
	    final int arraySize = 5;
        int[] array1 = new int[arraySize];
        int[] array2 = new int[arraySize - 1
        for(int i = 0; i < arraySize; i++){
            (int i) -> {
                array1[1] = i;
                System.out.println("Array[" + i + "] =" + array[i]);
            }
        }
        
        for(int i = 0; i < arraySize - 1; i++){
            (int i ) -> {
                array2[i] = array1[i] * i;
            }
        }
    }
}

```


#### Storing Lambda as a variable

Using the Consumer interface, from java.util package, a lambda can be stored as a variable.
- Must define n generic types for Consumer for n Lambda parameters.
- The datatypes specified as the generic types MUST be the same as the ones the Lambda uses.

```java
import java.util.Consumer.ArrayList;
import java.util.function.Consumer;

public class Main{
    public static void main(String[] args){
	    ArrayList<Integer> numbers = new ArrayList<Integer>();
	    numbers.add(5);
	    numbers.add(3);
	    numbers.add(1);
	    numbers.add(10);
	    
	    Consumer<Integer> method = (n) -> {
	        System.out.println(n);
	    }
	    numbers.forEach(method);
    }
}
```

Call lambda by using the variable name.

### Passing a Lambda as a function's parameter
- Can initialise a method variable, using interfaces, and assign a lambda to it.
	- Must have an interface which has a SINGLE method with the exact same return datatype and parameter(s) datatypes.
	- In some method, declare a variable with a datatype of the interface name.
	- Assign a lambda function to it.

- Methods can have lambdas as their parameter.
	- To do this, use the datatype as the name of the interface and then assign it a name: same as any other parameter.
	- Then, in the method, you can call the method the interface has.
	- MUST have assigned a lambda expression, or code block, to the lambda in the method that called it the method with a lambda parameter.

```java
interface lambdaFunc{
    int performOperation(int a, int b);
}

public class Main{
    public static void main(String[] args){
	    lambdaFunc l1 = (a, b) -> {return a + b};
	    lambdaFunc l2 = (a, b) -> {return a^a - b};
	    
	    printResult(10, 10, l1);
	    printResult(20, 20, l2);
    }
    
    public static void printResult(int a, int b, lambdaFunc func){
	    System.out.println(func.performOperation(a, b));
    }
}
```
