

---

# LLMs
Large language models, LLMs, aim to predict a sequence of tokens: next token prediction.
- Given a sequence of tokens, what is the most probable token to occur next?

Tokenisation takes words and converts them into symbols which can be represented by an int.

# Self-Attention
Self-attention is what allows LLMs to produce context dependent output.
- One of major reasons why transformer architecture was so successful for LLMs.
- Original paper introducing transformers was called "attention is all you need. "

Self-attention allows transformers to consider the context it is working in and limit it's output, statistically, to the probability of that output being in that context.

Overall idea: constrain
## Context Windows
A context window is the amount of info a model retains.

Models use context windows to compare it's long-term knowledge (it's statistical profile and feedforward network)  with what is happening now.
- Allows for responses to be given dependent on the context from all possible info rather than from all possible info alone.


# Retrieval Augmented Generation

# Memory Augmented LLM vs Human Episodic Memory