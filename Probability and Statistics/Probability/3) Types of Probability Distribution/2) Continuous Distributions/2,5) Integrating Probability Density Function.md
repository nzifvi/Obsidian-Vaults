[[2,1) Normal Distribution]] <- Back

---
## Integrating Probability Density Function
Getting the area underneath the bell curve has one mandatory step and then 2 options to actually get the probability of a value x occurring.

![[Pasted image 20250421132031.png]]

### Mandatory Step: Standardisation

Z-transform, aka standardisation, allows part of the integrand to be simplified.

$$
f(x)=\frac{1}{\sigma \cdot \sqrt{2\pi}}e^{-\frac{1}{2}\biggr(\frac{x-\mu}{\sigma}\biggr)^2}
$$
$$
\int f(x)= \int\frac{1}{\sigma \cdot \sqrt{2\pi}}e^{-\frac{1}{2}\biggr(\frac{x-\mu}{\sigma}\biggr)^2} dx
$$


Let $z = \frac{x-\mu}{\sigma}$ (z-score)

$$
\frac{d}{dx}[\frac{x-\mu}{\sigma}]= \frac{1}{\sigma}
$$
$$ 
\frac{dz}{dx} = \frac{1}{\sigma} \Rightarrow \frac{dx}{dz} = \sigma \Rightarrow dz\biggr(\frac{dx}{dz} \biggr) = dz\cdot \sigma
$$
$$
dx = dz \cdot \sigma
$$

Performing integration by substitution to simplify integrand...
$$
\int\frac{1}{\sigma \cdot \sqrt{2\pi}}e^{-\frac{1}{2}\biggr(\frac{x-\mu}{\sigma}\biggr)^2} dx =  \int \frac{1 \cdot \cancel{\sigma}}{\cancel{\sigma} \cdot \sqrt{2\pi}}e^{-\frac{1}{2}z^2}dz
$$

Ultimately simplifying to...

$$
\int \frac{1}{\sqrt{2\pi}}e^{-\frac{z^2}{2}}dz
$$

Mandatory step done.

NOTE:
If the integral has an upper and lower bound, they BOTH must be converted into their z-score equivalents too

$$
\int^{z_a}_{z_b}
$$

### Option 1: z-score table
To use this approach, the values a and b must be known.

$$
\int^{a}_{b}\frac{1}{\sigma \cdot \sqrt{2\pi}}e^{-\frac{1}{2}\biggr(\frac{x - \mu}{\sigma} \biggr)^2}
$$
And the mean and standard deviation must be known.
- convert the values a, b into their z score equivalents...

$$
z_a = \frac{a-\mu}{\sigma}
$$

$$
z_b = \frac{b-\mu}{\sigma}
$$

Now, using a z-score table to get the area underneath the curve at the 2 specified z-scores, subtract...

$$
P(X=x) = F(z_a)-F(z_b)
$$
### Option 2: integrate the Gaussian function
$$
\int \frac{1}{\sqrt{2\pi}}e^{-\frac{z^2}{2}}dz
$$
One more u-sub is required to integrate the gaussian from this stage.
- At this stage, the integrand can be further simplified to reduce the complexity.

1) Remove constants

$$
\int [ax]dx = a\int [x]dx \Rightarrow \int\frac{1}{\sqrt{2\pi}}e^{-\frac{z^2}{2}}dz = \frac{1}{\sqrt{2\pi}}\int e^{-\frac{z^2}{2}}dz
$$
Post simplification:
$$
\frac{1}{\sqrt{2\pi}}\int e^{-\frac{z^2}{2}}dz
$$

Now the exponent of e can be further simplified...

$$
-\frac{z^2}{2} = -\biggr(\frac{z}{\sqrt2}\biggr)^2
$$
Substituting the simplified exponent into the integrand...

$$
\frac{1}{\sqrt{2\pi}}\int e^{-\biggr(\frac{z}{\sqrt{2}}\biggr)^2}dz
$$
Perform u-sub to simplify the ENTIRE integrand by letting $u = \frac{z}{\sqrt2}$
$$
\frac{d}{dz}\biggr[\frac{z}{\sqrt2}\biggr] = \frac{1}{\sqrt{2}} \Rightarrow \frac{du}{dz} = \frac{1}{\sqrt{2}}
$$

$$
\frac{du}{dz} = \frac{1}{\sqrt{2}} \Rightarrow \frac{dz}{du} = \sqrt{2} \Rightarrow du(\frac{dz}{du}) = du \cdot \sqrt{2}
$$

Therefore...
$$
u = \frac{z}{\sqrt{2}}
$$
and
$$
dz = du \cdot \sqrt{2}
$$
Perform u-sub by substituting these values into the integrand...

$$
\frac{1}{\sqrt{2\pi}}\int e^{-u^2}\sqrt{2} du
$$
Factor out constants...

$$
\frac{1}{\sqrt{2\pi}}\int e^{-u^2}\sqrt{2} du \Rightarrow \sqrt{2}\frac{1}{{\sqrt{2\pi}}} \int e^{-u^2}du \Rightarrow \frac{1}{\sqrt{\pi}}\int e^{-u^2}du
$$
Ultimately simplifying the integrand to...

$$
\frac{1}{\sqrt{\pi}} \int e^{-u^2}du
$$

Now, perform integration : )

$$
\frac{1}{\sqrt{\pi}} \int e^{-u^2}du = \frac{1}{\sqrt{\pi}}\biggr(\frac{\sqrt{\pi}}{2}erf(u) \biggr) + C
$$
The anti-derivative of the Gaussian simplifies to...

$$
\frac{1}{2}erf(u) + C
$$

By substituting what u equals back into the anti-derivative in place of u, you transform the anti-derivative back into using z-score ordinates.
- Allowing integration to then be performed : )

$$
u = \frac{z}{\sqrt{2}} \Rightarrow \frac{1}{2}erf(u) + C = \frac{1}{2}erf\biggr(\frac{z}{\sqrt{2}}\biggr) + C
$$

Giving the FINAL, SIMPLIFIED anti-derivative that uses z-scores:

$$
\frac{1}{2}erf\biggr(\frac{z}{\sqrt{2}}\biggr) + C
$$

Then, to get the area underneath the curve between 2 z-score bounds, do...

$$
\frac{1}{2}erf\biggr(\frac{z}{\sqrt{2}}\biggr) + C\int^{z_a}_{z_b} = \biggr(\frac{1}{2}erf\biggr(\frac{z_a}{\sqrt{2}}\biggr) + C \biggr) - \biggr(\frac{1}{2}erf\biggr(\frac{z_b}{\sqrt{2}}\biggr) + C \biggr)
$$
