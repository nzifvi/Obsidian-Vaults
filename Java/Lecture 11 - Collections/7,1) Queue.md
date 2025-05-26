[[6,1 Map]] <- Back
[[8,1) ArrayList]] <- Next

---
## Queue
Interface that implements a queue data structure that is first in first out.
- Extends Collection.
- Implemented by LinkedList, PriorityQueue, plus others.

Queue does not allow accessing of elements by numerical index.
- Can only access the first item in the queue.

Queue provides insertion, removal, and inspection methods.

## Queue Methods
Two versions of the insert, remove, and inspect methods exist.
- One throws an exception when a failure occurs.
- One returns a special value when a failure occurs, no exception has to be handled.

### Add methods
#### boolean add(E e) (Exception version)
add() adds a new item to the queue.
- Returns true if success.
- Throws exception if failure.

#### boolean offer(E e) (Special value version)
offer() adds a new item to the queue.
- Returns true if item added successfully.
- Returns false if item not added successfully (something has gone wrong)

### Remove methods

#### E remove() (Exception version)

#### E poll() (Special value version)

### Inspection methods

#### E element() (Exception version)

#### E peek() (Special value version)