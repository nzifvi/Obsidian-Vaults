[[2 - PyGenn Models]] $\leftarrow$ Next

---
# What is PyGenn?
PyGenn is a python package used for creating and simulating spiking neural networks (SNNs).
- Written in C++ under the hood.
- Uses GPU-accelerated CUDA code.

PyGenn is used because...
1) Speed:
	- PyGenn enables long simulations of complex models to run almost two orders faster.
2) Flexibility:
	- PyGenn allows bespoke neuron and synapse models to be defined by users.
3) Hardware range:
	- PyGenn can be used on variety of NVIDIA GPUs.

# PyGenn Core Concepts

## 1) GeNNModel
GeNNModel is the central object of PyGenn. 
- Defines the SNN model which can later be simulated.

When defining a GeNNModel, you do it in 2 parts:
1) Constructor.
2) Simulation timestep.

The constructor has 3 parameters:
1) Name of the model.
2) Precision.
3) The backend to run the model on.
```python
model = pygenn.GeNNModel(
	"float",
	"tenHH",
	"CUDA"
)
model.dT = 0.1
```

`model.dT` defines the timestep.
## 2) Neuron & Synapse Populations
Two types of populations exist in a model:
1) Neuron populations.
2) Synapse populations

### 2.1) Neuron Populations
A neuron population = a group of neurons, in a model, which share the same neuron type AND parameters.
- Can have different state variable values per neuron.

### 2.2) Synapse Populations
Synapse populations define the connections and transmission rules between 2 neuron populations in a model.

## 3) Simulation Pipeline
![[Pasted image 20260315000746.png]]

Components of the simulation pipeline are...
1) Define Model
2) Build Model
3) Load
4) Initialise
5) Simulate
6) Extract Data

### Define Model
Model definition stage is when the model and neuron plus synapse populations are defined.
- Also relevant parameters of the model are set.

### Build Model
The function member of the `GeNNModel` called `build()` is called.
- Creates optimised CUDA, or CPU, C++ code.
- Then compiles it.

PyGenn is lazy:
- If no change in code has happened since last compilation, PyGenn skips recompilation: making repeated runs fast.
- Generated code is saved to a local directory named after the model.
### Load
The function member of `GeNNModel` called `load` is called.
- Loads model into memory.
- Allocates GPU buffers.

`load` function member has a parameter called num_recording_timesteps:
- Pre-allocates a spike recording large enough to store spikes across that many timesteps.

### Initialise
After loading model to GPU, state variables of neuron and synapse populations must be initialised BEFORE simulation loop begins.
- Done by directly assigning values to population variables views.

### Simulate
Simulation loop occurs until a previous duration, equal to the one assigned to the `GeNNModel` type variable when `load` function member was called.

Skeleton code loop structure is:
```python
for t in range(duration):
	# do some stuff to the model such as update input current per time step.
	
	model.step_time()
```

`step_time()` is a function member of a `GeNNModel` type variable which advances the simulation by one `dT`: the value given during the build model phase.
- MUST be done at the end of each iteration of the loop.

Other things CAN be done during simulation loop.
### Extract Data

## 4) State Variables & GPU Sync
