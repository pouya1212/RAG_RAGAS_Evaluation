## What is RAG?

RAG (Retrieval-Augmented Generation) is a technique used to improve the performance of Large Language Models (LLMs). It helps address the problem where an LLM may lack specific or up-to-date information because it was not part of its training data, or when it generates incorrect information (hallucinations).

This is especially useful when working with data that is private, frequently updated, or not included in the model’s training data.

If your data is static and does not change often, fine-tuning a model is an option. However, fine-tuning can be expensive and may lead to unwanted changes in the model’s behavior over time (also known as model drift).

Instead of fine-tuning, RAG retrieves relevant information from an external knowledge source and provides it as additional context to the LLM. This helps the model generate more accurate and reliable responses without retraining.

---

##  RAG Pipeline

**Figure 1: RAG Architecture**

![RAG Pipeline](./figures/rag-pipeline.png)
