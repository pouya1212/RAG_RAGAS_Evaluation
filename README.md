##  About This Repository

In this repository, an RAG pipeline was implemented, and its performance was evaluated using RAGAS metrics. The goal was to apply RAG on a set of PDF files related to pathology report generation using Vision-Language Models (VLMs). To evaluate the performance of the RAG system, a synthetic dataset was created from question–answer pairs derived from these papers. This dataset was then used to assess the RAG pipeline using LLM-based evaluation through RAGAS metrics.

CSV file contains Question and answers can be found here

`RAG_RAGAS_Evaluation.ipynb`

For the complete Python framework and step-by-step implementation, please refer to the Jupyter Notebook:

👉 `RAG_RAGAS_Evaluation.ipynb`


## What is RAG?

RAG (Retrieval-Augmented Generation) is a technique used to improve the performance of Large Language Models (LLMs). It helps address the problem of an LLM lacking specific or up-to-date information not part of its training data, or of generating incorrect information (hallucinations).

This is especially useful when working with data that is private, frequently updated, or not included in the model’s training data.

If your data is static and does not change often, fine-tuning a model is an option. However, fine-tuning can be expensive and may lead to unwanted changes in the model’s behavior over time (also known as model drift).

Instead of fine-tuning, RAG retrieves relevant information from an external knowledge source and provides it as additional context to the LLM. This helps the model generate more accurate and reliable responses without retraining.

### References

* [Simple RAG for GitHub issues using Hugging Face Zephyr and LangChain](https://huggingface.co/learn/cookbook/rag_zephyr_langchain)
  [Simple Evaluation of RAG](https://namratanwani.medium.com/evaluate-rag-with-ragas-e1ad1aa99c2e)
---

##  RAG Pipeline

The Retrieval-Augmented Generation (RAG) pipeline improves LLM responses by grounding them in external data.

### 🔹 Phase 1: Data Preparation
- **Document Loading** → Load raw data (PDFs, text, etc.)
- **Chunking** → Split documents into smaller chunks for better retrieval
- **Embedding** → Convert each chunk into vector representations
- **Vector Storage** → Store embeddings in a vector database for fast similarity search

### 🔹 Phase 2: Retrieval & Generation
- **Query Embedding** → Convert the user query into a vector
- **Retrieval** → Retrieve top-k most similar document chunks
- **Context Building** → Combine retrieved chunks into a context
- **LLM Generation** → Pass the query + context to the LLM to generate the final answer

---

##  RAG Pipeline Diagram (Figure 1)

The figure below illustrates the full RAG workflow, including both data preparation and the query-answering process. It shows how documents are processed into embeddings, stored in a vector database, and later retrieved to provide context for the LLM. The retriever finds relevant chunks, and the reader (LLM) uses them to generate accurate and context-aware responses.

![RAG Pipeline](./figures/rag-pipeline.png)

---

##  RAG Evaluation Pipeline

The evaluation pipeline measures the quality of generated answers by comparing them with the ground truth.

- Generate answers using the RAG system
- Evaluate using metrics:
  - **Faithfulness** → How well the answer is supported by the context  
  - **Answer Relevancy** → How relevant the answer is to the question  
  - **Context Precision** → How relevant the retrieved context is  
  - **Context Recall** → How much important information is retrieved  
  - **Answer Correctness** → How close the answer is to the ground truth



For the complete Python framework and step-by-step implementation, please refer to the Jupyter Notebook:

👉 `RAG_RAGAS_Evaluation.ipynb`
