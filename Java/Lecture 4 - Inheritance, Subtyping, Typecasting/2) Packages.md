---
Lecture4:
---
[[1.1) Access Specifiers]] <- Back

Classes and packages can be grouped into packages (a separate file) and imported.

Packages allow for...
1) Better organisation.
2) More reusability.
3) Avoiding name conflicts


### Package Syntax

```java
package packageName;

class Car{

}

```

Package files must be specified, as shown above...

To import a package...

```java
import packageName.Car; //can import a specific class from a package

//or...

import packageName.*;
//can import all classes from a package
```