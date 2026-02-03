[[1,1 - About Convolutions]] $\leftarrow$ Back

---
$$
A = [19, 24, 22, 10, 3,20, 22, 4, 19, 14]
$$
$$
Mask = [+1, -1]
$$
First, produce template:
$$
Template = -1\cdot Mask = [-1, +1]
$$

$$
(19\cdot -1) + (24\cdot1) = -19+24=5
$$
$$
A_{convoluted}=[5]
$$
Advancing template by 1 index...
$$
(24\cdot -1)+(22\cdot 1)=-24+22=-2
$$
$$
A_{convoluted}=[5, -2]
$$
Advancing template by 1 index...
$$
(22\cdot - 1)+(10\cdot 1)=-22+10=-12
$$
$$
A_{convoluted}=[5, -2, -12]
$$
Advancing template by 1 index...
$$
(10\cdot -1)+(3\cdot 1)=-10+3=-7
$$
$$
A_{convoluted}=[5, -2, -12, -7]
$$
Advancing template by 1 index...
$$
(3\cdot-1)+(20\cdot1)=-3+20=17
$$
$$
A_{convoluted}=[5, -2, -12, -7, 17]
$$
Advancing template by 1 index...
$$
(20\cdot -1)+(22\cdot 1)=-20+22=-2
$$
$$
A_{convoluted}=[5, -2, -12, -7, 17, -2]
$$
Advancing template by 1 index...
$$
(22\cdot - 1)+(4\cdot 1)=-22+4=-18
$$
$$
A_{convoluted}=[5, -2, -12, -7, 17, -2, -18]
$$
Advancing template by 1 index...
$$
(4\cdot - 1)+(19\cdot 1)=-4+19=15
$$
$$
A_{convoluted}=[5, -2, -12, -7, 17, -2, -18, 15]
$$
Advancing template by 1 index...
$$
(19\cdot -1)+(14\cdot 1)=-19+14= -5
$$
$$
A_{convoluted}=[5, -2, -12, -7, 17, -2, -18, 15, -5]
$$
