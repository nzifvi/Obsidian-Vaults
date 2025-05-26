[[3,1) Processing File Data]] <- Back

---

## What is Serialisation?
Serialisation = process of saving an Object to a file, aka disk.

What can be saved?
- Fields of the object (can store fields that are also references to other objects.)
- Multiple objects to one file.

What cannot be saved?
- Local variables or parameters in methods.

## How to make a Class Serialisable?
1) A class MUST implement Serializable interface
2) All fields must also implement Serializable
	- Means that no methods have be written (in most cases.)

Above process enables Java runtime support for additional saving features.

However, it does not save them. That requires code.

## Writing an Object to File

```java
clas Test implements Serializable {
	private Collection<Contact> contacts;
	private static final String FILE_PATH = "contactData";
	
	public void saveData() throws IOException{
		File f = new File(FILE_PATH);
		ObjectOutputStream os = ObjectOutputStream(
			new FileOutputStream(f);
		);
		os.writeObject(contacts);
		os.close();
	}
}
```

## Reading an Object from File

```java
class Test implements Serializable{
	private Collection<Contact> contacts;
	private static final String FILE_PATH = "contactData";
	
	public void loadData() throws IOException {
		File f = new File(FILE_PATH);
		ObjectInputStream is = new ObjectInputStream(
			new FileInputStream(f);
		)
		
		Type newData = (Type) is.readObject();
		is.close();
	}
}
```

## Customising Serialisation
- The Serialisation process can be customised by overriding writeObject and readObject methods.

NOTE: static variables cannot be serialised.