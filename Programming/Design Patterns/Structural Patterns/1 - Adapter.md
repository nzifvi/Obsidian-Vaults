[[2 - Bridge]] <- Next

---
## What is an Adapter Pattern?
An adapter is a structural design pattern which allows objects, with incompatible interfaces, to collaborate.

Instead of having to add specific function members, or change existing function members, of the objects to enforce collaboration, an adapter can be made for those 2 specific objects.

## Example Scenario
Suppose 1 class has encapsulation methods which return 3d arrays.

Suppose another class expects a 1d array.

For some reason, the class which expects a 1d array wants the 3d array but as a 1d array...

An adapter can be used for this purpose, allowing these 2 classes to interface by converting the 3d array into a 1d array.

```c++
class 3dArray{
	// let 3dArray be fully defined. Assume it has no bugs and works as intended.
}

class 1dArray{
	// let 1dArray be fully defined. Assume it has no bugs and works as intended.
}

class 3d1dAdapter{
	public static int* 3DTo1DAdapter(const int[][][] array, int xSize, int ySize,
	int zSize){
		int* arrayPtr = new int[xSize * ySize * zSize];
		for(int k = 0; k < zSize; k++){
			for(int j = 0; j < ySize; j++){
				for(int i = 0; i < xSize; i++){
					arrayPtr[index(i, j, k)] = array[k][j][i];
				}
			}
		}
		return arrayPtr;
	}
}
```

The adapter allows for a 3d array, from the 3d array class, to be converted into a 1d array class: enabling the 2 classes to interface indirectly via the adapter.


## Constraints of an Adapter

### 1) An adapter should ONLY adapt an input to become an output form
- An adapter should only adapt an input from 1 object into an acceptable output for another object.
- Should not do ANYTHING else which does not involve adapting that input (performing unrelated calculations, having unrelated data members, etc).

### 2) An adapter should be a 1:1 or a 1:many, ONLY CHILD SUB CLASSES, type of adapter.
An adapter should either be...
- 1:1, which means that an adapter only adapts for 1 type of object to another type of object.
or...
- 1:many, which means that an adapter adapts 1 type of objects to many type of other objects which are all children of a parent class OR the parent class itself.

NOTE: the adaptation can be 2 way, if required.


### 3) ONLY allow 2 way adaptation if required
Instead of always allowing for 2 way adaptation (enabling adaptation back and forth between objects), start of as 1 way by default.

ONLY add 2 way adaptation if it is required.

WHY?
- Avoid redundant code.