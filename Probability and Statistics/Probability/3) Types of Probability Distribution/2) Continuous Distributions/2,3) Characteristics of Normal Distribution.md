[[2,1) Normal Distribution]] <- Back

---
## Characteristics of Normal Distribution

#### 1) Normal Distribution is symmetrical about the mean, $\mu$ 
This means that two values, $x_1, x_2$ that are equidistant from $\mu$ will have the same probability density.

![[Pasted image 20250421122710.png]]

Suppose...
- $\mu$ = 90
- $x_1 = 120$

Let $\Delta x_1 = x_1 - \mu$
$$
\Delta x_1 = 120 - 90 = 30
$$
$$
\Delta x_1 = 30
$$

This gives the distance of a point from $\mu$
- Using this, the point which has an equal distance from mu as $x_1$ has can be found.
- This allows points, with an equal probability density, to be found.

$$
x_2 = \mu - \Delta x_1
$$
$$
x_2 = 90 - 30
$$
$$
x_2 = 60
$$

And... because the Normal Distribution is symmetrical about $\mu$

$$
f(x=120) =f(x=60)
$$

#### 2) The area, underneath the Bell Curve of a Normal Distribution, has sum of 1

The probability density function, f(x), produces probability density 

![[Pasted image 20250421122710.png]]

However, if you integrate the probability density function, you get the area underneath the bell curve.

![[Pasted image 20250421123459.png]]

The area underneath the bell curve is no longer probability density. It is probability.
- Integrating f(x) allows for the probability of a value of x to occur to be found.

$$
\int f(x)dx = P(X=x) 
$$


#### 3) f(x) is asymptotic function at y = 0

This is because the probability of x being a certain value can never be ignored, even if the value of x sounds insane.

- Both directions apply:
	- as x -> $-\infty$ , f(x) -> 0
	- as x-> $\infty$, f(x) -> 0