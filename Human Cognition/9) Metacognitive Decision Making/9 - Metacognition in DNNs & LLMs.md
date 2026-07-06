[[8 - Confidence Models]] $\leftarrow$ Back
[[10 - Building Metacognitive Evaluation and Control into Artificial Systems]] $\leftarrow$ Next

---
# 1) Metacognition in DNNs
## Confidence without Metacognition
When a CNN is given the same noisy stimuli, a noisy input image in this case, used on humans in experiments, the output of the CNN fluctuates IF CNN's confidence is viewed as the output layer nodes.
- Output of CNN fluctuates similar to how human confidence reports do in the presence of noisy stimuli.
- CNN may get answer wrong (low accuracy) yet, because visual features of noise looked like the target, output node activation remains high (high confidence.)

CNNs do not have metacognition by design. They are just simple neural networks.
- Suggests that metacognition might be a "free" by-product of processing with neural networks.

If a simple feed-forward neural network with no "self-awareness" can produce human-like pattern confidence, maybe humans do not need a specialised "metacognitive" brain area to report confidence.
- Sense of "knowing" might just be a direct output of primary sensory neurons.

## Estimating Confidence without Metacognition
CNNs are deterministic. Given same image, same response is produced.
- Humans are stochastic (noisy). If the same noisy image is seen twice, the primary visual cortex may process it differently due to variance in V1 simple neurons firing.

To model human evidence accumulation, to then model confidence, a CNN must be made to mimic human evidence accumulation.
- This type of CNN is called RTNet.

RTNet mimics stochastic human brain dynamics by using a Bayesian neural network architecture (BNN)
- In BNN, weights are a probability distribution rather than a fixed value.
- Every time a model processes an input, it pulls a slightly different set of weights from the probability distribution.
- This mimics noisy evidence.
- Accumulate the activations at the output layer, for each option, to get the final decision.

RTNet reproduces key relationships between human confidence and accuracy well.
- Acts as evidence that metacognition is not needed for confidence.

# 2) Metacognition in LLMs.
# LLM Confidence
Currently, LLMs are overconfident in their responses.
-  LLMs only do next token predicted: many models of human confidence cannot be applied to LLMs.
- LLMs providing meaningful confidence estimates is important. Users must know how reliable an output is.

## Human vs LLM Metacognition
Expressing confidence:
- LLMs tend to be over-confident when expressing confidence both verbally or numerically.
- LLMs also have a limited capacity to report numeric confidence which discriminates between correct and incorrect answers.

- Humans also tend to exhibit overconfidence although this may be due to strategic trade-offs.

Mechanisms for assessing uncertainty:
- In LLMs, token likelihoods and response consistency are used to estimate uncertainty.

- In humans, confidence may reflect internal consistency or access to task-relevant info.


Metacognition
- Metacognition of LLMs differ from humans quite a lot.

- LLMs appear to have limited introspective behaviours. They are better at predicting their outputs.

- Humans have privileged introspective access to at least some internal processes.


## Implicit Confidence in GPT-4
Chain of Thought (CoT) reasoning can be enhanced using self-consistency.
- Self-consistency is a measure of implicit confidence.

CoT can be given self-consistency by...
1) Using a set of different approaches to solve a task.
2) Assess the consistency across answers.
3) Select most consistent answer.
4) Confidence COULD be estimated by the degree of self-consistency.


High self-consistency = high confidence.
- If 20 different approaches result in the same answer, the model has high confidence in that answer.

Low self-consistency = low confidence.
- If 20 different approaches result in 15 different answers, low self-consistency reveals model's internal uncertainty.
- Low self-consistency can be used to reveal model's internal uncertainty even if a single approach results in a completely confident result.

## Eliciting Explicit Confidence from LLMs
Explicit confidence can be reported by an LLM by prompting them to report their confidence about an answer.
- Must explain the concept of confidence to them at the end of prompt.

Multiple possible prompts exist, each providing a different way confidence is reported

| Method       | Prompt                                                                                                                                                                                        |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Vanilla      | Read question, provide your answer, and your confidence in answer                                                                                                                             |
| CoT          | Read question, analyse step by step, provide your answer and your confidence in your answer                                                                                                   |
| Self-Probing | Question:<br>Possible answer:<br>Q: How likely is the above answer to be correct? Analyse the possible answer, provide your own reasoning concisely, and give your confidence in this answer. |
| Multi-step   | Read question, break problem down into K steps, think step by step, give your confidence in each step, and derive your final answer and your confidence in this answer.                       |
| Top-K        | Provide your K best guesses and the probability that each is correct (0% to 100%) for the following question                                                                                  |

