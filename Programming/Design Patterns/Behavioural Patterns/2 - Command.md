[[1 - Chain of Handlers]] <- Back
[[3 - Iterator]] <- Next

---
## What is a Command Pattern?
A command pattern is a behavioural pattern which turns a request into a stand-alone object.

The stand-alone object contains all...
- Information relevant to the request.
- Information required to perform the request.

### Why use a Command Pattern?
When a function is called with multiple variables, and asked to fulfil some kind of "request" using them, a command pattern can be used instead.

Instead of passing multiple variables all for a single request, you can pass a Command pattern object which is that request.

Allows for...
- Easier function declarations & definitions.
- Data can be validated inside of the Command object.
- Data structures, such as queues, arrays, etc, can be made to store the Command object.

## Example Scenario
Suppose a Convolutional Neural Network program is made. There are multiple layers and each layer has...
- a 4d double array of filters.
- a 1d double array of biases.
- a double value learning rate.

When the program begins runtime, it has to load a lot of files into each layers.

Each time the program begins back propagating, certain parts of the layers could be edited and then the files representing those layers must be updated.

A command pattern can be applied for requests to read/write files.

### Example Solution
```c++
class FileRequest{
protected:
	char requestType;
	std::string filePath;
public:
	FileRequest(const char& reqType, const std::string fileP);
	// assume all encapsulation function members included
}
```
EXPLANATION SO FAR:
- char requestType data member can either equal R or W and represents the type of operation.
- std::string filePath data member is the file path to either write to/read from

Then, create child classes to handle each unique data type involved:
- a 1d array of doubles.
- a 4d array of doubles.
- a double value which is a layer's learning rate.

```c++
class FilterFileRequest : protected FileRequest{
private:
	double data[][][][];
public:
	FilterFileRequest(const char& reqType, const std::string fileP, const double data[][][][]);
	
	// assume all encapsulation function members included
}
```

Then, a queue can be used to contain all file requests and call the relevant functions, depending on whether it is a read/write request, as well as the data type involved.

```c++
void processFileQueue(){
	while(!queue.empty()){
		// dequeue and cast the dequeued file object to the correct subtype.
		if(fileReq.getRequestType() = 'W'){
			// handle the write to file request.
		}else if(fileReq.getRequestType() = 'R'){
			// handle the read from file request.
		}else{
			throw InvalidFileRequest("error message");
		}
	}
}
```