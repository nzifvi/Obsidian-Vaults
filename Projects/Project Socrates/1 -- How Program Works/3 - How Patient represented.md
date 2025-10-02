
---

Patient represented as a class.
- Has a reference to a condition (one of it's child classes) object which will change the state of the body over time potentially.
- Patient class must simulate the body's function over time.

Patient class would have to have states such as...
- consciousness (determines if awake, able to talk, etc).
- temperature (to model what happens to the body at various states of temperature).
- some kind of "health" which would have to determined by multiple feedbacks (if patient loses enough blood, they lose health and die, if patient cannot fight infection, they die due to whatever the infection destroys, etc).


Patient class would also have to have references to objects which are each system of the body.
- Skeletal system.
- Immunological system.
- GI system.
- Cardiovascular system.
...

Each system would be different but would need a way to interact with each other to perform the simulation.
- Make systems as abstract as possible, only want to have cause -> effect type of simulation over time.
- Example of abstraction being do not make a fully realistic GI system. Just have a queue which pops food objects and consumes the nutrients of each food object, over time.

