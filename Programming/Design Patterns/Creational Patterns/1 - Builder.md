[[2 - Abstract Factory]] <- Back

---
## What is a Builder Pattern?
Builder pattern allows for complex objects to be constructed in a more organised, clean way.
- When objects have many parameters in their constructors, builder pattern is useful to simplify. 

Instead of an object's constructor doing everything to construct the object, a builder object performs the initialisation of the object and returns the object it has built.


## How do Builders Work?
A builder will have multiple function members which are executed in a specific order to fully initialise all data members of the object it is building.
- Each initialisation step from the constructor is separated into function members of the builder.

### Example:
The following is a constructor for the Layer class
```c++
class Layer{
private:
	// ...
public:
	Layer(double[][][][] filters, double[] biases, double learningRate, std::filePath controlFile){
		// assign filters to data members of class ...
		// open file and read from ...
		// perform validation on file, etc ...
		// done
	}
}
```

The above would result in quite a complex and difficult to read constructor. Instead, a builder for Layers can be created.

```c++
class LayerBuilder{
private:
	Layer product;
public:
	LayerBuilder(Layer& layer){
		this->layer = layer;
	}
	
	void buildFilters(std::string& filePath){
		/*
		Open file in read mode, validate, and assign to
		relevant fields in layer object using encapsulation
		methods.
		*/
	}
	
	void buildBiases(std::string& filePath){
		/*
		Open file in read mode, validate, and assign to
		relevant fields in layer object using encapsulation
		methods.
		*/
	}
	
	void buildLearningRate(std::string& filePath){
		/*
		Open file in read mode, validate, and assign to
		relevant fields in layer object using encapsulation
		methods.
		*/
	}
	
	Layer& get(){
		return this->layer&;
	}
}
```

Calling the builder to build a Layer would be done by...

```c++
#include <iostream>  
  
class Layer{  
private:  
    int x;  
public:  
    Layer(){  
  
    }  
    void setX(int x) {  
        this->x = x;  
    }  
  
    int getX() {  
        return this->x;  
    }  
};  
  
class LayerBuilder {  
private:  
    Layer& layer;  
public:  
    LayerBuilder(Layer& layer): layer(layer) {}  
  
    void buildX(const int x) {  
        layer.setX(x);  
    }  
  
    Layer& get() {  
        return layer;  
    }  
};  
  
Layer* buildLayer(Layer* layer);  
  
int main(){  
    Layer* layer = buildLayer(new Layer());  
    std::cout << layer->getX();  
    delete layer;
    
    return 0;
}  
  
Layer* buildLayer(Layer* layer) {
	// External build function which interfaces to the builder and calls the
	// builder's function members in the intended order, returning the product
	// once built.
    LayerBuilder builder(*layer);  
    builder.buildX(1);  
    return &builder.get();  
}
```


## Director
Instead of an external function which handles the actual use of the builder, a Director object can be created.

A director is an object which, given a builder and argument to operate on with the builder, will call the builder's function members in the intended order.
- All arguments are given to the director, which passes these arguments to the correct build function member of the builder object it is currently using.

```c++
class LayerBuilder{
};

class BuilderDirector{
private:
	
public:
	Layer* makeLayer(Builder& builder, std::string& fp1, std::string& fp2);
};
```

## Handling Child Classes
A director can be made to build multiple types of objects given that the correct builder is given with the correct arguments.

To do this, declare and define a builder interface which has the function members used are shared commonly between ALL other builders
- c++ interfaces do not exist. Just create a class which has only function members that are all public and inherit from it.
- Do NOT declare any data members in the interface.

```c++
class LayerBuilder{
public:
	LayerBulder(){
		
	}
	
	virtual ~LayerBuilder() = default;
	
	virtual 
}

class ConvolutionalLayerBuilder : public LayerBuilder{
private:
	Layer& layer;
public:
	ConvolutionalLayerBuilder(Layer& layer){
		this->layer = layer;
	}
	
	// all other building function members.
}

class PoolingLayerBuilder : public LayerBuilder{
private:
	Layer& layer;
public:
	PoolingLayerBuilder(Layer& layer){
		this->layer = layer;
	}
	
	// all other building function members.
}
```

Now a director for building layers can build these 2 objects using function overloading:
- Subtyping can also be used here, assuming the 2 types of layers are children of a Layer class too.

```c++
class BuilderDirector{
private:
public:
	Layer& makeLayer(LayerBuilder& builder, std::string& fp1, std::string& fp2);
}
```

Instead of subtyping, might be cleaner to declare and define separate function members for different child objects.

```c++
class BuilderDirector{
private:
public:
	ConvolutionalLayer& makeConvolutionalLayer(std::string& fp1, std::string fp2);
	PoolingLayer& makePoolingLayer(std::string& fp1, std::string fp2);
}
```