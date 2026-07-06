[[1 - About PyGenn]] $\leftarrow$ Next
[[3 - Neuron Population]] $\leftarrow$ Next

---
# Defining Models in PyGenn
To define a model, which will be a `GeNNModel` typed object, call it's constructor:

```python
model = pygenn.GeNNModel(
	precision = "float",  # precision
	model_name = "WPSNN", # naming model for it's directory.
	backend = "CUDA"      # what hardware to run it on.
)
```

Has 3 parameters:
1) `precision`
	- Determines the numerical precision used.
	- Can be `float` or `double`
	- `float` is 32-bit. It results in faster models which use less memory: good for more SNNs.
	- `double` is 64-bit. It is more accurate which is important for more complex ODEs.
2) `model_name`
	- Names the model.
3) `backend`
	- Defines what hardware is used so PyGenn knows what code to generate when model is built.
	- Can be `CUDA`, `OpenCL`, or `SingleThreadedCPU`
	- `CUDA` is for NVIDIA GPUs.
	- `OpenCL` is for AMD/Intel GPUs or CPUs.
	- `SingleThreadedCPU` is for CPUs. It will run the entire model on a single thread.

Models also have key data members which should be specified BEFORE calling `build` function member.
## model.dT
Controls the simulation time step, in ms, which determines how much an internal clock by by per iteration.
- ALL time constants, decay rates, and integration steps are done relative to `model.dT`
- smaller `dT` values results in higher accuracy but slower models.
## model.batch_size
Controls the number of parallel simulations to run.
- EACH simulation in the batch gets it's own copy of all state variables.
## model.seed
Random seed for reproducibility.
- Giving this a set value makes the simulation deterministic.
- Allows for outcomes to become reproducible. 
## model.fuse_postsynaptic_models

## model.fuse_pre_post_weight_update_models

# Types of Models
The type a SNN `GeNNModel` becomes depends on what neuron and synapse models are added to it.

# Model Population Management
## Adding Populations
To add a neuron population to a model, use `GeNNModel` function member `add_neuron_population()`

To add a synapse population to a model, use `GeNNModel` function member `add_synapse_population()`
## Accessing Existing Populations
Both neuron and synapse populations are stored as dictionaries.
- Each population is stored in (popName, population) pairs.

Two dictionaries exist in `GeNNModel` type variables.
1) `neuron_populations`
2) `synapse_populations`

To iterate over ALL of them, do...
```python
for populationName, population in model.neuron_populations.items():
	# use
	
```
- can just iterate over .keys() or .values().

To access a single population, the name (which is the key in the dictionary) is required
```python
model.synapse_populations["test"]
```

# Push/Pull 
Push operations used to send things to GPU. Pull operations used to retrieve things from GPU.

Two types of push/pull operations exist: model level and population level.

## Model Level Push/Pull
Model Level Push/Pull function members operate on ALL populations, in a model, at once.
1) `push_state_to_device()`
2) `pull_state_from_device()`
3) `pull_recording_buffers_from_device()`

### `push_state_to_device`

### `pull_state_from_device`

### `pull_recording_buffers_from_device`
## Population Level Push/Pull