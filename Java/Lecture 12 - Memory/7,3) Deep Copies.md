[[7,1) Copies]] <- Back

---
## Deep Copies
Sometimes, an entirely fresh copy of an object, or collection, is required.
- If performing a deep copy on an object, any objects the object references must have a new object made for them in the deep copy.
- If performing a deep copy on a collection, each element requires a new object to be initialised and values from the old element, in the original collection, to be copied to the new element in the deep copy.

This results in a copy with NO aliases, aka a DEEP COPY. In a deep copy, there are NO aliases shared with the original object or collection (and elements of a collection).

Ways to implement this:
1) Each class has a copy method that returns a new object of itself using it's own parameters.

### Deep Copies of an Object
```java
class Car{
	private int seatNo;
	private int doorNo;
	private int kmCount;
	
	private Engine  carEngine;
	private Tank    fuelTank;
	private Wheel[] wheels;
	
	//suppose a constructor exists for all possible fields.
	
	public Car copy(){
		Wheel[] newWheels = new Wheel[wheels.length];
		for(int i = 0; i < newWheels.length; i++){
			newWheels[i] = wheels[i].copy();
		}
		
		return new Car(
			this.seatNo,
			this.doorNo,
			this.kmCount,
			
			new Engine(
				//pass all parameters
			),
			new Tank(
				//pass all parameters
			),
			newWheels
		)
	}
}
```

### Deep Copies of a Collection or array
1) Initialise a new collection (or array), to have the same data type as the collection (or array) a deep copy is being made of.

```java
Car[] newArray = new Car[oldArray.length];
```

2) Then, for each element of the newArray, assign the return value of copy() when it is called on each element of the old array...

```java
for(int i = 0; i < newArray.length; i++){
	newArray[i] = oldArray[i].copy();
}
```

For data structures that are not accessible by index, such as linked lists, graphs, trees, and maps, different approaches to perform a deep copy are required.