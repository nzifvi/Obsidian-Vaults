[[5,1) Reference]] <- Back
[[7,1) Copies]] <- Next

---
## Aliases
An alias occurs when multiple references point to the same location in memory.
```java
int[] x, y; //references are null as they have not been assigned...

x = {1, 2, 3};
y = x; //y is an alias of x...
```

Because y was assigned x, the pointer, not the value stored at the memory address x points to, y is now an alias of x.
- Both references x, y now point to the same memory address.

When a change is made to an alias, or to the original reference, the change is shared for all aliases and the original reference.
- Because the aliases, and the original reference, all point to same memory address.
- If update is made to memory at the memory address, changes happen for everything that points to it.

```java
int[] x,y;

x = {1, 2, 3};
y = x; //y becomes an alias of x.

x[0] = 42;

System.out.println(x);
System.out.println(y);
```

OUTPUT:
```
42, 2, 3
42, 2, 3
```

## Advantages of Aliases
Aliases mean that different parts of code can share objects by aliases pointing to the same memory address.

Two objects can each have a variable pointing to the same object INSTEAD of an object having to get a reference from another object each time it wants to access the shared object.

NOTE: the above works as long as if one of the object updates the pointer stored in their alias, the other object must ALSO have it's alias updated.
- Otherwise they will no longer share the same thing. One object's alias will point to the old value. The other will point to a new value.

## Disadvantages of Aliases
If passing objects into a method, and then modifying the object (updating a field, etc), then any object which has an alias to the now modified one will also change.

The object changes inside the method that has been called.

Anywhere else the object is referenced by an alias, it changes there too.

For example...

Suppose an object of Contact class is called object1.
```java
class Contact{
	static class Person{
		String name;
	
		public Person(final String name){
			this.name = name;
		}
	}

	Person person;
	int contactID;
	
	public Contact(Contact contact){
		this.person = contact.person;
	}
	//...
}
```

suppose that you are creating a new contact and, to do so, you use an existing one... A method is called

Let return be an object called contact2.
```java
public Contact createContact(Contact contact){
	return new Contact(
		contact.getPerson(); //returns contact's person
	)
}
```

The above returns a pointer of the contact object and then the new Contact object stores an alias for an existing contact's person.

Therefore, any changes made to the old contact also occurs in the new contact...

```java
contact1.getPerson().setName(
	"Jane"
);

contact2.getPerson().setName(
	"John"
);

System.out.println(contact1.getPerson().getName());
```
OUTPUT:
```
John
```

Even though contact2's person field's name field was set to John, and contact1's person field's name field was set to Jane because, when contact2 was initialised, a reference of contact1's person was passed, they share the same Person object.

- If requiring a new object, based on the properties of an old contact, you should transfer the required primitive values.
- If a new object is required, create a new object using primitive values from the object passed as a parameter.

Instead of previous initialisation of contact2, it should be done this way...

1) Should not use an object as a parameter for a constructor. Instead have a constructor that takes in primitive values.

```java
public Contact(final String personName, final int contactID){
	this.person = new Person(
		personName
	);
	this.contactID = contactID;
}
```

- If an object is required to be initialised, pass the required parameters from the old object and initialise a new object within constructor.

OR 

- Can initialise a new object in a method and then PASS it to the constructor.

```java
public Contact createContact(Contact contact){
	return new Contact(
		new Person(
			contact.getPerson.getName(), //returns String...
			contact.getID();
		);
	)
}
```

This prevents an alias from being made in the event one is not required.