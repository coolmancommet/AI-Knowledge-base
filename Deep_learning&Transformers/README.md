## 1. Deep Learning Foundations

### Core Mechanics

* **Forward Propagation:** Computing predictions via weights, biases, and activations. [link MEDIUM](https://medium.com/gen-ai-adventures/what-is-forward-propagation-in-neural-networks-588882607a80)
* **Backpropagation:** The chain rule in action to compute gradients.[link TDS](https://towardsdatascience.com/neural-networks-forward-pass-and-backpropagation-be3b75a1cfcc/)
* **Gradient Descent:** Updating weights to minimize the loss function.[for learning rate and GD ](https://medium.com/@juanc.olamendy/gradient-descent-in-deep-learning-a-complete-guide-with-pytorch-and-keras-examples-e2127a7d072a)
* **Vanishing & Exploding Gradients [Added - Expanded]:** You must know *why* they happen (compounded matrix multiplications) and how things like **gradient clipping** and proper **weight initialization** (Xavier/He, **[Added]**) fix them.
  (gradient and not weights. gradient is the delta to weights.) [medium link](https://kishanakbari.medium.com/understanding-vanishing-and-exploding-gradients-in-neural-networks-a-deep-dive-with-examples-ca9284863d50)

### Optimizers & Regularization

* **Optimizers:** [optimizerss core and why they are needed](https://towardsdatascience.com/neural-network-optimizers-made-simple-core-algorithms-and-why-they-are-needed-7fd072cd2788/) , [differential and adaptive learning rates optimizers](https://towardsdatascience.com/differential-and-adaptive-learning-rates-neural-network-optimizers-and-schedulers-demystified-2edc589fa2c9/)
* **SGD:** Stochastic Gradient Descent.[SGD](https://towardsdatascience.com/stochastic-gradient-descent-math-and-python-code-35b5e66d6f79/)
* **Adam:** Adaptive Moment Estimation (tracks first and second moments). [adam](https://towardsdatascience.com/the-math-behind-adam-optimizer-c41407efe59b/)
* **AdamW:** Adam with decoupled weight decay (crucial for Transformers; know why standard Adam + L2 regularization fails here).[ adam W vs adam ](https://yassin01.medium.com/adam-vs-adamw-understanding-weight-decay-and-its-impact-on-model-performance-b7414f0af8a1)


* **Activation Functions:** ReLU, GELU (standard in modern LLMs), Sigmoid. Know the dead ReLU problem. [RELu GELU SILU](https://freedium-mirror.cfd/https://pub.towardsai.net/activation-functions-in-focus-understanding-relu-gelu-and-silu-841ed1c6df0c)
* **Normalization & Regularization:** [fast learing regularization](https://medium.com/@dewasheesh.rana/normalizat-2294d50bde56)
* **Dropout:** Randomly deactivating neurons during training.
* **BatchNorm:** Normalizing across the batch dimension. Know the difference between training (using batch stats) vs. inference (using running averages).[batch Norm](https://towardsdatascience.com/batch-norm-explained-visually-how-it-works-and-why-neural-networks-need-it-b18919692739/) beta and gamma for scaling and shifting varience to a specific value 
* **LayerNorm [Added]:** Normalizing across the feature dimension. **Crucial note:** Transformers use LayerNorm, *not* BatchNorm, because batch sizes vary and NLP sequences have dynamic lengths.[ nice example of understanding the LN and BN](https://outcomeschool.com/blog/batch-normalization-vs-layer-normalization)



---

## 2. The Transformer Architecture

* [The concept of attention](https://machinelearningmastery.com/what-is-attention/)
* [The attention mechanism](https://machinelearningmastery.com/the-attention-mechanism-from-scratch/)
* [The Bahdanau attention mechanism](https://machinelearningmastery.com/?p=12940&preview=true)
* [The Luong attention mechanism](https://machinelearningmastery.com/the-luong-attention-mechanism/)

### Core Components [visual representation](https://medium.com/@gokulrajar/attention-mechanism-math-illustration-transformers-series-part-1-37c24ac9d2f2)
[detailed explanation](https://jalammar.github.io/illustrated-transformer/)
* **Self-Attention & Multi-Head Attention:** Mapping queries ($Q$), keys ($K$), and values ($V$). Multi-head allows the model to attend to information from different representation subspaces simultaneously.
* **The Attention Formula:**

$$Attention(Q, K, V) = \text{softmax}\left(\frac{QK^T}{\sqrt{d_k}}\right)V$$


* *Interview Must-Know:* We scale by $\sqrt{d_k}$ because for large dimensions, the dot products grow large in magnitude, pushing the softmax function into regions with extremely small gradients (causing vanishing gradients during backprop).


* **Positional Encoding:** Injecting sequence order since attention is permutation-invariant. Know the difference between absolute (Sinusoidal) and **Relative/Rotary Embeddings (RoPE) [Added]** used in modern LLMs like Llama.
* **Encoder vs. Decoder:**
* **Encoder:** Bidirectional context (e.g., BERT).
* **Decoder:** Autoregressive, uses **Causal Masking [Added]** to prevent looking at future tokens (e.g., GPT).


* **KV Cache [Added]:** A massive interview topic. How storing past Keys and Values speeds up autoregressive decoding during inference.

### Why Transformers Beat RNNs

1. **Parallel Processing:** RNNs must process sequentially (step-by-step); Transformers process the entire sequence at once during training.
2. **Better Long-Range Dependency Handling:** Attention provides a direct path between any two tokens, bypassing the fading memory of RNN paths.
3. **Scalable Training:** Enables training massive datasets on hardware clusters efficiently.

---

## 3. Recommended Study Resources

* **Neural Networks:** *3Blue1Brown Neural Networks playlist* (YouTube) – Best for visual intuition.
* **Transformers:** *The Illustrated Transformer* by Jay Alammar – Mandatory baseline reading.
* **Advanced NLP:** *Stanford CS224n* (Natural Language Processing with Deep Learning).
* **Vision Foundations:** *Stanford CS231n* (Convolutional Neural Networks for Visual Recognition).

---

## 4. Must-Know Interview Questions

> **Q: Explain the vanishing and exploding gradient problems. How do ResNets and LSTMs attempt to solve them?**
> * **Answer Hint:** LSTMs use an internal cell state with additive "gates" so gradients can flow unimpeded. ResNets use residual/skip connections ($f(x) + x$), creating a shortcut path for the gradient to pass backward without being diminished by weight matrices.
> 
> 

> **Q: Why do we use ReLU instead of Sigmoid in deep hidden layers?**
> * **Answer Hint:** Sigmoid saturates at 0 and 1, where its derivative is nearly 0. In deep networks, multiplying these tiny derivatives kills the gradient. ReLU has a constant derivative of 1 for all positive inputs, preventing saturation.
> 
> 

> **Q: What is the difference between Pre-LN and Post-LN in Transformers? [Added Question]**
> * **Answer Hint:** Post-LN places LayerNorm *after* the residual addition; it is unstable and often requires a strict learning rate warmup. Pre-LN places LayerNorm on the input path *before* the sub-layer, which stabilizes training and is the default choice for modern large-scale architectures.
> 
> 

> **Q: How does Batch Normalization work during training vs. inference?**
> * **Answer Hint:** During training, it calculates the mean and variance of the current mini-batch. It also tracks a running average of these metrics. During inference, it locks those running averages to normalize the incoming data deterministically, ensuring predictions don't depend on batch size.
> 
> 

---
If you are preparing for modern AI engineering or research roles, interviewers will expect you to understand how modern Large Language Models (LLMs) scale, stay efficient, and handle huge contexts.

To bridge the gap between basic Transformer theory and practical state-of-the-art networks, you should add these four categories to your syllabus.

---

## 1. Attention Variants (Solving the $O(n^2)$ Bottleneck)

Standard self-attention forces every single token to look at every other token. If you double your text length, the computational cost and memory quadruples ($O(n^2)$ complexity). Modern models use variations to cheat this math:

* **Multi-Query Attention (MQA):** Uses multiple Query heads, but only *one* Key and *one* Value head shared across them. This drastically cuts down memory footprint during generation.
* **Grouped-Query Attention (GQA):** The middle ground used by models like Llama 3. It groups Query heads and assigns one Key/Value head per group. It gives you nearly the speed of MQA but retains the accuracy of standard Multi-Head Attention.
* **FlashAttention:** A hardware-level breakthrough. Instead of writing the massive intermediate attention matrix ($N \times N$) to slow GPU High-Bandwidth Memory (HBM), it calculates attention in blocks using fast GPU SRAM. It doesn't change the output math—it just radically accelerates training and inference.

---

## 2. Advanced Architectural Choices

* **RMSNorm (Root Mean Square Normalization):** A faster alternative to LayerNorm. It skips calculating the mean of the features and only calculates the variance, saving about 10% to 50% of normalization computation time with zero loss in accuracy.
* **SwiGLU Activation:** Modern LLMs have largely abandoned standard GELU for SwiGLU. It is a gated activation function that improves learning capacity, though it requires slightly more parameters per layer.
* **Mixture of Experts (MoE):** Instead of passing a token through one giant Feed-Forward Network (FFN), an MoE layer contains multiple smaller "expert" networks. A router network sends each token to only 1 or 2 experts. This allows a model to have 100B+ total parameters but only use a fraction of them per token (e.g., Mixtral, GPT-4), making inference incredibly fast.

---

## 3. High-Yield System & Inference Concepts

Interviewers love testing your understanding of how models actually run in production.

* **PagedAttention:** Inspired by virtual memory in operating systems. Instead of allocating a huge, continuous block of GPU memory for a single user's KV cache (which wastes tons of memory due to fragmentation), it fragments the KV cache into small blocks and maps them dynamically. This is the core magic behind high-throughput inference engines like vLLM.
* **Speculative Decoding:** A trick to beat the latency of generating text token-by-token. A tiny, fast "draft" model guesses the next 5–6 tokens quickly, and then the massive target model evaluates them all in a single parallel forward pass. If the big model approves, you get a massive speedup.

---

## 4. Expansion Questions for Your Interview List

> **Q: Why does the KV Cache become a major system bottleneck for long-context generation?**
> * **Answer Hint:** While model weights stay fixed in memory, the KV Cache grows linearly with every single generated token and every user in a batch. For long sequences, the KV Cache size can quickly exceed the memory required to hold the model weights themselves, leading to Out-Of-Memory (OOM) errors on the GPU.
> 
> 

> **Q: What is the core architectural difference between BERT, GPT, and T5?**
> * **Answer Hint:** **BERT** is an Encoder-only model (uses bidirectional attention, great for understanding/embeddings). **GPT** is a Decoder-only model (uses causal masking, great for autoregressive generation). **T5** is an Encoder-Decoder model (cross-attention connects them, great for translation or sequence-to-sequence mapping).
> 
> 

---

To get a concrete visual breakdown of how the memory demands of these models scale at the matrix level in production, check out this guide on [Understanding the KV Cache Bottleneck](https://www.youtube.com/watch?v=CxRGWfcGVbs). It breaks down exactly why inference systems struggle with long sequences from a system-infrastructure perspective.