# 🧠 Comprehensive Large Language Model (LLM) & RAG Study Guide

A structured refresher on the core concepts, architectures, optimization techniques, and evaluation metrics for modern Large Language Models and Retrieval-Augmented Generation (RAG) systems.

---

## 1. Important Concepts & Foundations

### Tokenization
The process of breaking down text into smaller, machine-readable units (tokens). [tokenizers](https://huggingface.co/docs/transformers/en/tokenizer_summary)
* **BPE (Byte Pair Encoding):** A data compression technique that iteratively replaces the most frequent pair of bytes with a single, unused byte. Widely used in GPT models.
* **SentencePiece:** An unsupervised text tokenizer and detokenizer used for neural network-based text generation. It treats spaces as just another character, making it highly language-agnostic.
* **Tokens vs. Words:** A token is not strictly a word; it can be a part of a word, a single character, or a whole word. (e.g., `1 token ≈ 4 characters` in English).

### Pretraining [good link](https://www.moveworks.com/us/en/resources/ai-terms-glossary/pre-training)
The initial phase where a model learns to understand language by processing vast amounts of data.
* **Next Token Prediction:** The core objective of decoder-only models (like GPT or LLaMA); predicting the most statistically likely next token given the previous context.
* **Massive Corpus Training:** Training on terabytes of diverse, internet-scale text data to build foundational language representations.
* **🌟 Advanced Topic: Mixture of Experts (MoE):** An architecture where only a subset of neural network layers (experts) are activated for a given token, vastly increasing model capacity without proportionally increasing compute costs during inference (e.g., Mixtral 8x7B).

---

## 2. Fine-Tuning & Inference Optimization

### Fine-Tuning Approaches
* **Full Fine-Tuning:** Updating all the weights of the pre-trained model. Highly computationally expensive and prone to catastrophic forgetting if not done carefully.
* **PEFT (Parameter-Efficient Fine-Tuning):** Techniques that update only a small subset of parameters, significantly reducing memory and compute requirements.
* **LoRA (Low-Rank Adaptation):** A PEFT technique that freezes the pre-trained model weights and injects trainable rank decomposition matrices into each layer of the Transformer architecture.
* **QLoRA:** Combines LoRA with model quantization (e.g., 4-bit precision) to allow fine-tuning of massive models on single, consumer-grade GPUs.
* **🌟 Advanced Topic: RLHF & DPO:** * **RLHF (Reinforcement Learning from Human Feedback):** Aligning model behavior with human preferences using a reward model.
  * **DPO (Direct Preference Optimization):** A simpler mathematical alternative to RLHF that skips the reward model and directly optimizes the policy on preference data.

### Inference Optimization
* **Quantization:** Reducing the precision of the model's weights (e.g., from 16-bit float to 8-bit or 4-bit integers) to reduce memory footprint and increase inference speed.
* **KV Cache:** Storing the Key and Value states of previous tokens during self-attention so they don't need to be recomputed for every new token. Crucial for fast text generation.
* **Batching:** Processing multiple prompts simultaneously to maximize GPU utilization.
* **🌟 Advanced Topic: Continuous Batching & PagedAttention:** Techniques used by frameworks like vLLM to dynamically manage KV cache memory, preventing fragmentation and drastically increasing throughput.
* **Distillation:** Training a smaller "student" model to mimic the outputs of a larger "teacher" model.

---

## 3. Prompt Engineering Techniques

* **Zero-shot:** Asking the model to perform a task without providing any examples.
* **Few-shot:** Providing a few examples in the prompt to condition the model's output format and logic.
* **Chain of Thought (CoT):** Instructing the model to "think step-by-step," forcing it to output its reasoning process before arriving at an answer. Greatly improves performance on complex logic tasks.
* **ReAct (Reasoning and Acting):** A framework where the model alternates between reasoning about what to do and acting (calling an external tool/API) to gather information.
* **System Prompting:** The overarching instructions given to the model that dictate its persona, constraints, and general behavior.

---

## 4. Retrieval-Augmented Generation (RAG) 

*(Highly Critical Area)*
[part1](https://medium.com/@rossashman/the-art-of-rag-with-textract-and-mongodb-atlas-e287714a606f)

RAG grounds the LLM in external, proprietary, or up-to-date data, significantly reducing hallucinations.

### Architecture Pipeline
1. **Document Ingestion:** Loading raw documents (PDFs, HTML, Text).
2. **Chunking:** Splitting large documents into smaller, semantically meaningful passages.
3. **Embedding Generation:** Converting text chunks into dense mathematical vectors that capture semantic meaning.
4. **Vector Database:** Storing embeddings for fast similarity search.
5. **Retrieval:** Taking a user query, embedding it, and performing a nearest-neighbor search in the Vector DB to find relevant chunks.
6. **LLM Generation:** Injecting the retrieved chunks into the prompt context and asking the LLM to answer the query based *only* on that context.

### 🌟 Advanced RAG Topics
* **Semantic Chunking:** Splitting text based on natural semantic boundaries (sentences/paragraphs) rather than fixed character counts.
* **Re-Ranking:** Using a specialized cross-encoder model (e.g., Cohere Rerank) to re-order the initial retrieved chunks by actual relevance to the query, discarding noise. [re ranking](https://towardsdatascience.com/advanced-rag-retrieval-cross-encoders-reranking/)
* **HyDE (Hypothetical Document Embeddings):** Having the LLM generate a "fake" answer to the query first, then using that fake answer to search the Vector DB, which often yields better semantic matches than the raw query.

### Essential Tools
* **Orchestration:** LangChain, LlamaIndex
* **Vector Databases:** FAISS (local/in-memory), Pinecone (managed cloud), ChromaDB, Qdrant, Milvus.

---

## 5. Quality, Evaluation, & Mitigation 
[good source about evaluation](https://www.braintrust.dev/articles/what-is-rag-evaluation)
### Hallucination Reduction
* **Grounding with RAG:** Forcing the model to cite sources from retrieved context.
* **Confidence Thresholds:** Using logprobs (if accessible) to gauge model uncertainty and refuse to answer if confidence is low.
* **Response Verification:** Using a second LLM prompt or a rule-based system to fact-check the generated answer.
* **Better Prompting & Domain Fine-Tuning:** Setting strict system constraints ("If you do not know the answer, say 'I don't know'").

### Evaluation Metrics
* **Traditional NLP Metrics (Less reliable for generative tasks):**
  * **BLEU:** Measures n-gram overlap between generated and reference text (Common in translation).
  * **ROUGE:** Measures recall-focused n-gram overlap (Common in summarization).
  * **Perplexity:** Measures how well a probability model predicts a sample (lower is better).
* **Modern LLM Metrics (e.g., RAGAS Framework):**
  * **Faithfulness:** Does the generated answer strictly align with the retrieved context without making things up?
  * **Context Precision:** Are the retrieved chunks actually relevant to the user query?
  * **Context Recall:** Did the retrieval system find all the necessary information required to answer the query?
  * **Answer Relevance:** Does the final answer directly address the user's initial question?
* **Human Evaluation:** Still the gold standard for nuances like tone, helpfulness, and safety.

---

## 6. Where to Learn
* **LLMs & Fine-tuning:** Hugging Face NLP Course.
* **Prompting & RAG:** Prompt Engineering Guide (`promptingguide.ai`) and Pinecone's Learning Center.
* **LoRA/PEFT:** Read the original LoRA paper summary on Hugging Face.
* **RAG Evaluation:** RAGAS documentation.

---

## 7. Test Your Knowledge (Interview Questions)

### Core Concepts
1. **Walk me through the exact differences between Full Fine-Tuning, LoRA, and Prompt Engineering (Few-Shot). When do you use which?**
2. **Explain the KV Cache in transformer inference. How does it speed up text generation, and what is the memory bottleneck associated with it?**
3. **What is the difference between an encoder-only model (like BERT) and a decoder-only model (like LLaMA)?**

### RAG & Engineering
4. **In a RAG system, your retrieval step is pulling irrelevant documents. How do you debug and fix this?** *(Hint: Discuss chunking sizes, overlap, dense vs. sparse/BM25 retrieval, and re-ranking).*
5. **How would you design a RAG system that needs to answer questions based on tables and charts inside a PDF?**
6. **Explain the concept of "Lost in the Middle" in relation to LLM context windows. How does this impact RAG?**

### Evaluation & Advanced
7. **How do you evaluate a GenAI application in production? Explain Context Precision and Faithfulness using the RAGAS framework.**
8. **What is catastrophic forgetting in fine-tuning, and how do techniques like LoRA help mitigate it?**
9. **If your LLM application is too slow (high latency), what are 3 different architectural or infrastructural changes you could make to speed it up?**