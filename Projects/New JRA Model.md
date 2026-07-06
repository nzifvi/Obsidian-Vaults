# Model Structure and Components
Egocentric environment model, encoded in parietal window (PW) network, relative to the current bearing of an entity, are transformed into allocentric environment models for long term storage in medial temporal lobe (MTL).
- PW stores egocentric environment model.
- MTL stores allocentric environment model.

A gain-field transform circuit (GFTC) is used to map PW to MT using a HDC neuron population.
- Since bearing is predicted externally of model, can create a canvas HDC population where the bearing is just injected into and encoded as a spike train.
- Encoded bearing is then fed to GFTC.

![[Pasted image 20260619224955.png]]
- Since only doing egocentric -> allocentric, only worry about bottom-up.

| Allocentric Cell Name      | Egocentric Variant | Purpose                                                                                                                                                                                                                                                            |
| -------------------------- | ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Place Cell (PC)            | N/A                | Spike when an animal enters the preferred (x, y, z) ordinate of a PC in a PC population                                                                                                                                                                            |
| Boundary Vector Cell (BVC) | PWb                | Spike in response to a boundary being detected at a preferred distance and allocentric bearing.<br>- Boundary = a wall, edge, and long barrier.<br>- To be classed as a boundary, must run along a direction.                                                      |
| Object Vector Cell (BVC)   | PWo                | Spike in response to an object being detected at a preferred distance and allocentric bearing.<br>- Object = discretise, localised entities: pillar, box, etc.<br>- To be classified as an object, must sit at a specific point rather than run along a direction. |




| Egocentric Cell Name                 | Allocentric Variant | Purpose                                                                                                  |
| ------------------------------------ | ------------------- | -------------------------------------------------------------------------------------------------------- |
| Parietal Window Boundary Cells (PWb) | BVCs                | Spike in response to a boundary being detected at a preferred egocentric distance and egocentric bearing |
| Parietal Window Object Cells (PWo)   | OVCs                | Spike in response to an object being detected at a preferred egocentric distance and egocentric bearing  |

GFTC maps PWbs to BVCs.
- Acts like mapping a local pose to a global pose, using a rotation matrix.
- GFTC synaptic connections encodes all discrete set of rotation matrices $R(\theta)$.
	- The output of the HDC population provides the bearing that results in the rotation matrix being selected.
- GFTC performs gain modulation, selecting the correct rotation matrix, and applies the rotation matrix to the PWb population input to produce the BVC output.
	- Comparable to producing a global pose vector using a local pose vector and a rotation matrix.

![[Pasted image 20260619233100.png]]
NOTE: 2 separate GFTCs must exist for OVCs and BVCs.
- A single GFTC cannot calculate boundary and object spike trains independently.
- Non-independent spike trains would sum and the distinctive signals would be lost.
# Neuron and Synapse Population Description and Math
## Dimensions
Let...
- $N_{PWb}$ denote the number of PWb neurons.
- $N_{PWo}$ denote the number of PWo neurons
- $N_{HDC}$ denote the number of HDC neurons.
- $N_{GFTC}$ denote the number of GFTC neurons.
- $N_{BVC}$ denote the number of BVC neurons.
- $N_{OVC}$ denote the number of OVC neurons.
- $D$ denote distance bins.
- $\Phi_{e}$ denote the egocentric bearing bins.
- $\Phi_{a}$ denote the allocentric bearing bins.
$$
N_{PWb} = D \Phi_e
$$
$$
N_{PWo} = N_{PWb}
$$
$$
N_{HDC} = \text{HDC HEADING BINS}
$$
$$
N_{GFTC}(PWb) = N_{PWb}N_{HDC} 
$$
$$
N_{GFTC}(PWo) = N_{PWo}N_{HDC}
$$
$$
N_{BVC} = D\Phi_{a}
$$$$
N_{OVC} = N_{BVC}
$$
## Inputs (Non-synapse)
### Sensory $\rightarrow$ PWb or PWo
```functionDefinition
injectIntoPWb()

injectIntoPWo()
```

Act as injection functions, using a von Mises kernel.
- No synapse population required.
- Injected directly into target PW neuron population.

BOTH sensory injection functions will pass an egocentric distance and bearing.

Injects into $I_{ext}$ var of `_NEURON` model.

### Odometry $\rightarrow$ HDC Pop
```functionDefinition
injectIntoHDC()
```
Act as injection function using von Mises Bump.
- No synapse population required.
- Injected directly into canvas HDC pop
## Synapse Populations
### PWb $\rightarrow$ GFTC(PWb)
Synapse population delivers egocentric egocentric boundary encoded spike train, from PWb population, into UNKNOWN.

- Synaptic connections are sparse.
- Pre-size = $N_{PWb}$
- Post-size = $N_{GFTC}(N_{PWb})$
- Weights: UNDECIDED CURRENTLY
- Postsynaptic: ExpCurr

### PWo $\rightarrow$ GFTC(PWo)
Synapse population delivers egocentric egocentric boundary encoded spike train, from PWo population, into UNKNOWN.

- Synaptic connections are sparse.
- Pre-size = $N_{PWo}$
- Post-size = $N_{GFTC}(N_{PWo})$
- Weights: UNDECIDED CURRENTLY
- Postsynaptic: ExpCurr
### HDC $\rightarrow$ (GFTC(PWb) $\wedge$ GFTC(PWo) )
Selects which bearing rotation matrix is active when transforming egocentric PW boundary representation to allocentric MTL ones.

- Synaptic connections are sparse.
- Pre-size = $N_{HDC}$
- Post-size = $N_{GFTC}$
- Each HDC cell k, with a preferred heading of $\theta_k$, connects to EVERY GFTC cell in column $k$.
- Weights: custom multiplicative model, not ExpCurr
	- Gain-modulation input.

### GFTC(PWb) $\rightarrow$ BVC $\wedge$ GFTC(PWo) $\rightarrow$ OVC
- Synaptic connections are sparse.
- Pre-size = $N_{GFTC}$
- Post-size = $N_{BVC}$
	- $N_{OVC}$ if considering GFTC(PWo) -> OVC.
- Weights: uniform suprathreshold.
- Postsynaptic: ExpCurr, additive.

# About GFTC
Each GFTC cell represents a conjunction between...
1) BOUNDARY AT EGOCENTRIC BEARING $\phi_e$ 
	- ALSO OBJECT AT EGOCENTRIC BEARING $\phi_e$
AND
2) robot bearing $\theta_k$

A GFTC cell should only fire when both are true.
- Each cell is an implementation of an AND gate.

## Custom Mutliplicative Model
![[Pasted image 20260620003110.png]]
