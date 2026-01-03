[[1,2 - Classification Trees]] $\leftarrow$ Back

---
# Data Sample
| Loves Popcorn | Loves Soda | Loves Ice |
| ------------- | ---------- | --------- |
| Y             | Y          | N         |
| Y             | N          | N         |
| N             | Y          | Y         |
| N             | Y          | Y         |
| Y             | Y          | Y         |
| Y             | N          | N         |

Building decision tree to predict if somebody loves ice...
# 1) Choosing Root Node

Evaluating Loves Popcorn as root node:
![[Pasted image 20251230010114.png]]

$$
GI(LovesIce, TRUE)=1-P(X=Yes)^2 - P(X=No)^2
$$
$$
P(X=Yes)=\frac{1}{1+3}=\frac{1}{4}
$$
$$
P(X=No) = \frac{3}{1+3}=\frac{3}{4}
$$
$$
GI(LovesIce, TRUE)=1-\biggr(\frac{1}{4}\biggr)^2-\biggr(\frac{3}{4}\biggr)^2=0.375
$$
$$
GI(LovesIce, FALSE)=1-P(X=Yes)^2 - P(X=No)^2
$$
$$
P(X=Yes)=\frac{2}{2+0}=1
$$
$$
P(X=No)=\frac{0}{2+0}=0
$$
$$
GI(LovesIce, FALSE)=1-(1)^2 - (0)^2 = 0
$$

$$
TGI_{LovesPopcorn}=\frac{Sum{(LovesIce,TRUE)}}{1+3+2+0}GI(LovesIce, TRUE)+ \frac{Sum{(LovesIce, FALSE)}}{1+3+2+0}GI(LovesIce, FALSE)
$$
$$
TGI_{LovesPopcorn}=\frac{4}{6}\cdot0.375+\frac{2}{6}\cdot0 = 0.25 \Rightarrow TGI = 0.25
$$

Evaluating Loves Soda as root node...
![[Pasted image 20251230010926.png]]
$$
GI(LovesIce, TRUE)=1-P(X=Yes)^2-P(X=No)^2
$$
$$
P(X=Yes)=\frac{3}{3+1}=\frac{3}{4}
$$
$$
P(X=No)=\frac{1}{3+1}=\frac{1}{4}
$$
$$
GI(LovesIce, TRUE)=1-\biggr(\frac{3}{4}\biggr)^2-\biggr(\frac{1}{4}\biggr)^2=\frac{3}{8}
$$
$$
GI(LovesIce, FALSE)=1-P(X=Yes)^2 - P(X=No)^2
$$
$$
P(X=Yes)=\frac{0}{2+0}=0
$$
$$
P(X=No)=\frac{2}{2+0}=1
$$
$$
TGI_{LovesSoda}=\frac{Sum{(LovesIce,TRUE)}}{1+3+2+0}GI(LovesIce, TRUE)+ \frac{Sum{(LovesIce, FALSE)}}{1+3+2+0}GI(LovesIce, FALSE)
$$
$$
TGI_{LovesSoda}=\frac{4}{6}\cdot\frac{3}{8} + \frac{2}{6}\cdot 0 \Rightarrow TGI_{LovesSoda} = 0.25
$$

VERDICT:
- TGIs equivalent, both lead to equally good decisions. CHOOSE LOVES POPCORN.


# 2) Branching: 1st iteration.