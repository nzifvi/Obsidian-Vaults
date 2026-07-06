[[2 - Approaches to Face Alignment]] $\leftarrow$ Back

#CV #AppliedMachineLearning #CV-FaceAlignment #CV-FaceAlignment-Metrics

---
# Recall
The facial features of an image of a face is represented as...
$$
S = \begin{bmatrix}
s_{(1,1)}&...&s_{(1,N)}\\
s_{(2,1)}&...&s_{(2,N)}
\end{bmatrix}
$$
Where, for each element s...
- $s_{(1, i)}$ denotes the $i^{th}$ x-ordinate.
- $s_{(2, i)}$ denotes the $i^{th}$ y-ordinate.

EACH facial feature can be described as a vector

$$
\vec{s} = \begin{bmatrix}
s_x\\s_y
\end{bmatrix}
$$
Therefore... $S$ is a matrix of facial feature vectors

$$
S=\begin{bmatrix}
\begin{bmatrix}
s_{(1,1)}
\\
s_{(2,1)}
\end{bmatrix}
&...&
\begin{bmatrix}
s_{(1,n)}
\\
s_{(2,n)}
\end{bmatrix}
\end{bmatrix}
$$
# Methods of measuring Error between Facial Features
Suppose...
- $\vec{s}_{pred}$ denotes a facial feature, predicted by a model.
- $\vec{s}_{actual}$ denotes the CORRECT facial feature that should have been predicted.

One method of measuring error between facial features is the Euclidian distance between the predicted and actual facial feature


$$
\mathcal{L}(\vec{s}_{pred}, \vec{s}_{actual})= \sqrt{\sum_{i=1}^2\biggr[(s_{actual_i} - s_{pred_i})^2\biggr]}
$$
