[[3,1) Collection]] <- Back

---
## What is Iterator?
Iterator is an interface in Java that provides a way to iterate over a collection element by element.
- Iterator typically used with ArrayList, HashSet, and LinkedList.
- Since it is an interface, each Collection, or sub class of Collection, has to provide a method definition for all methods the Iterator interface provides.

## Iterator Interface
Iterator<.E> comes from java.util.Iterator package.

Iterator is an interface that a collection, or sub class of collection, implements.
- This is because a data structure may have different ways of accessing elements.
- By overriding the methods, each iterator of a data structure can be customised and work for that data structure.
#### boolean hasNext()
hasNext() is used to check if there are more elements to iterate over.
- Returns true if current index < capacity of the collection.
- Returns false if index == capacity of the collection (meaning no more elements to iterate over).

#### E next()
Used to return the next element in the collection, incrementing some kind of internally stored index before returning an element of data type E.
- The data type E, the type parameter, becomes specified upon initialisation of Iterator.
- MUST be same data type, or a sub class of a non-primitive data type, as the data type the collection's type parameter was specified to be.
- Throws NoSuchElementException IF there are no more elements.

```java
@Override
E next(){
	if(this.index == this.capacity){
		throw new NoSuchElementException;
	}else{
		//get element to return
		this.index++; //increment index for a future next() call
		//return element 
	}
}
```


#### Using an Explicit Iterator, aka Manual Iteration
- A collection, or sub class of a collection, will have an iterator that is defined to work for it.

```java
Collection<Car> cars = new Collection<Car>();
//some cars are added...

Iterator<Car> it = cars.iterator();

int sumOfCarValues = 0;
while(it.hasNext()){
	Car carObj = it.next();
	sumOfCarValues = carObj.getPrice();
}
```

Make the iterator of a collection, or sub class of a collection static.
- Each collection, or sub class of collection, has an iterator object as a field.
- Iterator object stores a capacity value that is equal to number of elements a collection, or subclass of collection, has.
- Updates per operation.

When creating an Iterator, external of the class, just return the iterator that is the field of that collection, or sub class of the collection.

```java
class Array <E> implements Collection, Iterator{
	int capacity;
	E[] array;
	Iterator<E> it;
	
	//methods for Array defined and methods for Collection overridden.
	
	Iterator<E> iterator(){
		return this.it;
	}
}
```