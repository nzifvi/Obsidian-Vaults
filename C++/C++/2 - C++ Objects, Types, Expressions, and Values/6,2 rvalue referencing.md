[[6,1 - lvalues and rvalues]] <- Back

---
## What is an rvalue reference?
rvalue references are a type of reference which can only bind rvalues.
- rvalues are either an xvalue or prvalue.

T& is an lvalue reference.

T&& is an rvalue reference which binds rvalues to it, preventing their lifetime expiring whilst the reference remains in-scope.

## Uses of rvalues?
Recall the return of a function is a prvalue. It immediately vanishes once the scope ends.
- rvalues CANNOT be stored outside of a function, without a reference to them (rvalue references).
- therefore, rvalue references enable move semantics, allowing for resources (dynamic memory) to be moved instead of copied
	- Significantly optimises performance by avoiding deep copies.