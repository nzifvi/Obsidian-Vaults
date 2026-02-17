[[5,1 - Decision Thresholds]] $\leftarrow$ Back
[[6 - Signal Detection Theory]] $\leftarrow$ Next

---

First, transform the transfer function results to a probability value.
- Use sigmoid transfer function if only differentiating between 2 classes.
- Use softmax transfer function if differentiating between n classes.

Then, using a decision rule, perform classification for input x.
- Let $output_i = p(x = class_i)$
$$
result(x) = max\biggr(output_1,...,output_n\biggr)
$$
