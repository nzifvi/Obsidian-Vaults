
---
# Primer
- $s(r)$ denotes the tangential spacing, between neurons, on ring r.
- $N(r)$ denotes the number of neurons on ring r.
- $d(r, r+d)$ denotes the radial spacing between rings of the circle.
- $d$ is the radial spacing between rings.
- $\theta_{w}$(r) is the tangential spacing between neurons on a ring.
Since each ring has a uniform radial spacing of d...
$$
d(r,r+d) = d \wedge d(r,r+2d)\wedge ... 
$$
$$
r=id
$$
$$
s(r)=r\theta_{w}(r) \Rightarrow s(id)=id\theta_{w}
$$

# Claim
Equivalent radial and tangential spacing, as well as non-equivalent radial and tangential spacing, cannot produce uniform tangential spacing across all rings.

For uniform tangential and radial spacing, the following must be true:
$$
\forall r, s(r)=d(r,r+d)
$$


$$
s(r)=d(r,r+d) \Rightarrow id\theta_w =d 
$$
$$
\frac{id\theta_{w}}{id} = \frac{d}{id} \Rightarrow \theta_{w} = \frac{1}{i}
$$


# Case 1: Equivalent Radial and Tangential Spacing
Suppose the tangential spacing, between neurons on the same ring, and the radial spacing between rings is equivalent. This means that:
$$
\theta_{w}=d
$$
$$
s(r)=rd
$$
$$
s(r)=rd \wedge s(r)=d(r, r+d) \Rightarrow rd = d
$$
$$
\forall i, i \in \mathbb{Z^+} \wedge i > 2 \Rightarrow rd \cancel{=}d
$$
- Only equal for one single ring: r = 1.
# Case 2: Non-equivalent Radial and Tangential Spacing
Suppose the tangential spacing and radial spacing is different. This means that:
$$
\theta_{w}=\frac{1}{i}
$$
$$
r(s) = s\theta_{w} \Rightarrow r(id)= id\theta_{w}
$$
$$
s(id)=d(id, id+d) \Rightarrow id\theta_{w} = d
$$
$$
id\theta_{w} = d \Rightarrow \frac{id\theta_{w}}{id} = \frac{d}{id} \Rightarrow \theta_{w} = \frac{1}{i}
$$
Theta becomes a function of i...
$$
\forall i, i \in \mathbb{Z^+} \Rightarrow \theta_{w}(i) \cancel{=} \theta_{w}(i+1)
$$

Equivalent tangential spacing of neurons, across all rings, is not possible.


# Consequence
Tangential spacing between neurons increase as the ring number, i, increases.
- Outer rings have larger gaps, between neurons, than inner rings.

This means that the distance, between neurons, is not uniform for all rings.
- Obstacles which may be detected in 1 neuron may be detected across 3 neurons in inner rings.
- Obstacles which may be detected in 3 neurons may be detected across 1 neurons in outer rings.

Result: planned paths become either dangerous, due to an object being larger than a neuron can represent, in inner rings and inefficient in outer rings due to massive gaps between neurons.
