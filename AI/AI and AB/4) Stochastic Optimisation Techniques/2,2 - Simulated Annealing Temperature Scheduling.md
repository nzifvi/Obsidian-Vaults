[[2,1 - Simulated Annealing]] $\leftarrow$ Back

---
# Simulated Annealing Temperature Scheduling
Temperature scheduling allows for the temperature to be decreased per iteration: making it tougher for new solutions to be accepted
$$
t \rightarrow 0 \Rightarrow P(\Delta F) \rightarrow 1
$$
![[Pasted image 20260226132800.png]]

Temperature scheduling depends on...
1) Starting and final temperature.
2) Temperature decrement protocol.

# Starting Temperature
The starting temperature...
- Must be hot enough to allow moves to neighbouring states; hill climbing is implemented otherwise.
- Must not be too hot that random search is done for too long: never approaching a local maxima.

Problem is finding a good starting temperature.

