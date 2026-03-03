[[3 - Hierarchy of Vision]] $\leftarrow$ Back
[[5 - Faces]] $\leftarrow$ Next

---
# Human Visual Cortex vs. DNNs/CNNs
DNNs & CNNs designed based on features of human visual system.

Important questions:
- Do DNNs/CNNs classify similar to how humans do, using the visual system.
- Are DNNs & CNNs good models of human vision.
- Can DNNs & CNNs be improved by making them more like the human visual system.

# Modern CNN Architecture
A modern CNN has the following architecture:

![[Pasted image 20260224112912.png]]

Each convolutional layer of filters produces feature maps.
- Similar to how V1 neuron cells in primary visual cortex function.

Pooling layers reduce dimensions of visual input.
- Similar to how receptive field changes based on the region of primary visual cortex being used.

Layers of CNN are often stacked.
- Similar to hierarchical structure of primary visual cortex.

Processed image has to be transformed into a decision, using a decision rule.
- Similar to what humans must do based on visual input via visual system.

# Key Structural Similarities of CNNs and Human Vision

## 1) CNN Nodes that activate like how Neurons fire
Neurons "fire" when they depolarise enough above a threshold.
- Eventually depolarise enough to achieve action potential: neuron firing.

Nodes in CNN simulate neuron firing with their transfer function.
- Output of transfer function simulates strength of neuron firing.

![[Pasted image 20260224113131.png]]

## 2) Hierarchical Feature Extraction
In primary visual cortex of brain, vision processing is hierarchically ordered.
- Higher regions process more complex, abstract features.
- The higher the region is, the larger the receptive field.

CNNs are hierarchically ordered into layers.
- Each layer either is a convolutional or pooling layer.
- Convolutional layers extract features. 
- Pooling layer reduces dimensions of input, producing an output with smaller dimensions.

![[Pasted image 20260224113345.png]]

# Functional Similarities of CNNs and Human Vision

## 1) CNNs and Human Vision are both used to make classifications

## 2) Classifications are often correlated: both a CNN and Human vision can do the same task.
Just because they are correlated, doing the same task, does NOT mean they achieve the task in the same way.
- Only the task being done is the same.
- The way the task is being done differs.

## 3) Neural Activity and NN Activity have shown to be correlated.


# Main Differences between CNNs and Humans

## 1) CNNs make very un-human errors


## 2) CNNs have non-human-like biases

