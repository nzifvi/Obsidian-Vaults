
---
# Speed Cell
A speed cell measures how fast an entity is moving through the environment.
- Stimulus an entity.
- Attribute of stimulus is the magnitude of velocity of said entity
$$
\bar{r}=s(||\vec{v}||)
$$
Tuning curve is linear

# Head Direction (HD) Cell
HD cells maintain an entity's bearing allocentrically.
- Forms ring attractor: population of neurons which collectively encode a single direction at any moment, updated by the angular velocity input.

Stimulus of HD Cells are an entity. Attribute is an allocentric bearing.
$$
\bar{s}=f(\psi)
$$

Tuning curve is Von Mises: a circular Gaussian.
# Grid Cell
Grid cells accumulate velocity signals, over time, from speed cells to maintain a continuously updated estimate of an entity's position in the environment.
- Performs path-integration: integrating an entity's position, over time, as it follows a path.

Grid cells are organised in a flat, 2D grid known as the neural sheet. 
- Each neuron lies at an intersection.
- Neurons close to each other in the neural sheet are connected via dendrites and axons.
- Neurons far apart are weakly connected or not connected at all.
- Different positions of the neural sheet correspond to different positions in the environment.

Neural sheet has toroidal topology.
- Right edge connects to left edge. Top connects to bottom.
- Ensures no neurons are at an edge making all neurons equivalent.

Only 1 subpopulation of the neural sheet will be spiking strongly at any given time.
- Represents the estimate of an entity's position in space.

Stimulus of grid cells is the velocity vector of an entity. However, velocity never explicitly given.
- Instead spike trains from speed cell and HD cell populations are fed since they encode the velocity vector of an entity.
- Speed cells provide velocity magnitude. HD cell provides bearing. This is enough to reconstruct velocity vector
# BVC Cell
Given a distance, d, and an allocentric direction, $\phi$, boundary vector cell neurons 
encode if a boundary exists there or not.
- Each BVC cell in a population of BVCs has a preferred distance and allocentric direction they spike more frequently for.

BVCs are used to encode persistent surfaces such as walls, fixed edges.
- Permanent stuff which will not go away.
# OVC Cell
Given a distance, d, and an allocentric direction, $\phi$, object vector cell neurons 
encode how confident a population of OVCs is that an object is there.
- Each OVC cell in a population of OVCs has a preferred distance and allocentric direction they spike more frequently for.

OVCs are used to classify objects, such as obstacles or a thing sitting in the environment.

The membrane potential of OVCs is dynamic. It will decay over time.
- Membrane potential increased by active sensor hits.
- OVCs track CURRENT state of environment.

OVC population spiking, at time t, is used to figure out what objects are currently observable and where are they.

# Place Cell
Place cells, given a coordinate from an allocentric environment, encode whether an entity is at said coordinate.
- Used to figure out where an entity is in an environment.

Place cells have a preferred coordinate, called place field centre.
- Place cells spike strongly when an entity is at, or near, their place field centre.

$$
\bar{r} = f(\vec{p})
$$
- where $\vec{p}$ is the position in space.

$\vec{p}$ is NEVER explicitly given. Instead, populations of grid, BVC, and OVC cells have their spike trains fed to a population of place cells.
