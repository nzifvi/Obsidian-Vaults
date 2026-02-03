[[2,1 - Levels and Layers]] $\leftarrow$ Back

---
# 1) Control Layers
Idea of Levels of competence, LOC, allow for control layers to be built corresponding to each LOC.
- New control layers can be added to an existing set to move to the next highest LOC.

To start, a control system which achieves level 0 competence is built: $L_0$.
- It is debugged thoroughly.
- $L_0$ is never altered.
- Referred to as zeroth level control system ($L_0$ control system).

When wanting to build another layer, $L_1$ control system, it...
- Is able to examine data from $L_0$ control system.
- Able to inject data into internal interfaces of $L_0$ control system, disrupting normal data flow.
- $L_0$ control system continues to run: unaware of the above layer which sometimes interferes with it's data path.
- Same process is achieved to build higher competence levels.

![[Pasted image 20260201222411.png]]

This style of architecture is called subsumption architecture.

# 2) Subsumption Architecture
Subsumption architecture solves the requirements for control systems.
#### Solution: Multiple Goals
Individual control layers can work on their individual goals in parallel.
- Suppression mechanism then mediates the actions, out of the possible actions, can be taken.

Advantage: no need to make an early decision of which goal should be pursued.
#### Solution: Multiple Sensors
Subsumption architecture solves the problem of fusing multiple sensors, as well as the errors associated with said sensors.
- Each layer can process sensor readings as they wish independently: allowing for representations of sensor readings to be customised per layer.
	- Allows for representations best to achieve a goal of a layer to be used, rather than 1 central representation for all layers.



#### Solution: Robustness
Multiple sensors add robustness to the system when sensor readings are used intelligently.

Subsumption architecture ALSO provides robustness.
- Lower control layers, which are debugged well, are unchanged and continue to run when new higher layers are added.

#### Solution: Additivity