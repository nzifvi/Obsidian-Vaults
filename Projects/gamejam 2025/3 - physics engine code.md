[[2 - mathematics for motion]] <- Back

---

# Vector Classes

```c++
class VelocityVector {
protected:
    // PROTECTED DATA MEMBERS:
    double xRecComponent;
    double yRecComponent;

public:
    // CONSTRUCTORS AND DESTRUCTORS:
    VelocityVector(): xRecComponent(0), yRecComponent(0){}
	VelocityVector(const double xRec, const double yRec): xRecComponent(xRec), yRecComponent(yRec){}
	
	// PUBLIC FUNCTION MEMBERS:
	void updateVelocity(const double xAcceleration, const double yAcceleration, const double timeInSeconds){
	    xRecComponent = xRecComponent + (xAcceleration * timeInSeconds);
	    yRecComponent = yRecComponent + (yAcceleration * timeInSeconds);
	}
	
	// ENCAPSULATION FUNCTION MEMBERS:
	double getXComponent(){ return xRecComponent; }
	double getYComponent(){ return yRecComponent; }
	
	void setXComponent(const double xRec){ xRecComponent = xRec; }
	void setYComponent(const double yRec){ yRecComponent = yRec; }
}

class PositionVector : public VelocityVector{
private:
    // PRIVATE DATA MEMBERS
    VelocityVector* ptrVelocityVector = nullptr;
    
protected:
public:
    // CONSTRUCTORS AND DESTUCTORS:
    PositionVector(const double xRec, const double yRec):
    VelocityVector(xRec, yRec),
    ptrVelocityVector(new VelocityVector(0, 0)){}
    
    
}
```