[[4,1 - Function Call and Return]] <- Back

---
## What are Namespaces
Classes and functions both have a purpose. They allow names to be declared, within their scope, without worrying about clashes of names between their scopes.

Classes and functions also have names, allowing us to uniquely call them.

HOWEVER, classes and function names can clash. UNLESS A NAMESPACE IS USED.

Namespaces are a way of grouping declarations. The declarations of a namespace exist only within there.

```c++
namespace LinkedList{
	class Node{
		//...
	}
}

namespace Tree{
	class Node{
		//...
	}
}
```

Without the namespaces above, there would be name clashes between the two node classes.
- Namespaces allow each node to only exist within that scope.

Declarations within a scope can be accessed using the namespace name, plus the scope resolution operator ::

```c++
int main(){
	LinkedList::Node linkedListNode;
	Tree::Node treeNode;
}
```