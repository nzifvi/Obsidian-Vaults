
---
## What is a Function Class?
A function class (functors) is a class with the singular purpose of being treated as a function.
- It is even called as a function.

#### Why use Functors?
- When a class requires some constants, or wanting to have multiple variants of a base functor to have more specialised functors.
	- Can use subtyping.



## How to Declare & Define a Functor
Functors are declared, and defined, as any other class with a notable exception. They overload the () operator WITHIN the class so that it is a function member of the functor.

```c++
class Example{
private:
public:
	Example(){
		// Constructor definition
	}
	
	overload ()() const{
		// overloaded () operator definition
	}
}
```


## How to Call a Functor
To call a functor, do it as you would with any function.
- Refer to it by it's identifier.

```c++
Example();
```