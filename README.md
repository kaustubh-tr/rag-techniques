# **RAG Techniques Implementation**

This repository contains several implementations of Retrieval-Augmented Generation (RAG) techniques using various tools and APIs. The notebooks in this repository explore different RAG strategies, including Adaptive RAG, Agentic RAG, Corrective RAG, Self RAG, Hyde RAG (Hypothetical Document Retrieval), Reranking RAG, and Naive RAG.

## **Table of Contents**
- [Introduction](#introduction)
- [RAG Techniques](#rag-techniques)
  - [Adaptive RAG](#adaptive-rag)
  - [Agentic RAG](#agentic-rag)
  - [Corrective RAG](#corrective-rag)
  - [Self RAG](#self-rag)
  - [Hyde RAG](#hyde-rag-hypothetical-document-retrieval)
  - [Reranking RAG](#reranking-rag)
  - [Naive RAG](#naive-rag)
- [Setup Instructions](#setup-instructions)
  - [Environment Setup](#environment-setup)
  - [API Keys](#api-keys)
- [Usage](#usage)
- [License](#license)

## **Introduction**
Retrieval-Augmented Generation (RAG) is a technique that combines traditional language models with external retrieval mechanisms to improve the quality of generated text. This repository demonstrates several RAG strategies to enhance the capabilities of large language models in tasks like question answering, summarization, and more.

Each notebook in this repository demonstrates a different RAG approach using different configurations and APIs.

## **RAG Techniques**

### **Adaptive RAG**
Adaptive RAG dynamically adjusts the retrieval process based on the context of the query. This method utilizes multiple retrieval sources or models and adapts to the nature of the query to improve the overall performance of text generation.

- **Notebook**: [adaptive_rag/test.ipynb](adaptive_rag/test.ipynb)

### **Agentic RAG**
In Agentic RAG, an external agent (or system) interacts with the model to perform the retrieval process. This agent could be a search engine, a domain-specific retrieval system, or another external tool that helps improve the model's output.

- **Notebook**: [agentic_rag/test.ipynb](agentic_rag/test.ipynb)

### **Corrective RAG**
Corrective RAG uses external sources or retrieval systems to correct or refine the initial generation of a language model. This often improves factual accuracy or handles ambiguous queries by introducing additional context from relevant documents.

- **Notebook**: [corrective_rag/test.ipynb](corrective_rag/test.ipynb)

### **Self RAG**
Self RAG involves using the language model itself to generate and retrieve relevant information. The model queries its own outputs to refine and improve the answer generation process, making it more self-reliant.

- **Notebook**: [self_rag/test.ipynb](self_rag/test.ipynb)

### **Hyde RAG (Hypothetical Document Retrieval)**
Hyde RAG refers to a strategy where the model "hypothetically" retrieves documents that may not actually exist but are generated based on the query. This method is useful for scenarios where the information is not readily available in the corpus, but plausible and contextually relevant documents can be synthetically created for the retrieval process.

- **Notebook**: [hyde_rag/test.ipynb](hyde_rag/test.ipynb)

### **Reranking RAG**
Reranking RAG utilizes external models, such as Cohere, to rank and select the most relevant results from a set of retrieved documents. This approach improves the quality of generated text by selecting the best context to condition the model's generation.

- **Notebook**: [reranking_rag/test.ipynb](reranking_rag/test.ipynb)

### **Naive RAG**
Naive RAG is a straightforward implementation where retrieval and generation are performed without additional strategies for ranking, correction, or adaptation. It uses basic retrieval to guide the generation process without further refinements.

- **Notebook**: [naive_rag/test.ipynb](naive_rag/test.ipynb)

## **Setup Instructions**

### **Environment Setup**
1. Clone this repository:
    ```bash
    git clone https://github.com/kaustubh-tr/rag-techniques.git
    cd rag-techniques
    ```

2. Create a virtual environment (recommended):
    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
    ```

3. Install required dependencies:
    ```bash
    pip install -r requirements.txt
    ```

4. Rename the `.env.example` file to `.env` and provide the necessary values for your environment:
    ```bash
    cp .env.example .env
    ```

### **API Keys**
You will need to set up the following API keys to run some of the RAG techniques:

- **OPENAI_API_KEY**: For interacting with OpenAI models.
- **PGVECTOR_CONNECTION_STRING**: For connecting to your vector database (for retrieval).
- **TAVILY_API_KEY**: Used in Adaptive and Corrective RAG techniques for retrieval and correction.
- **COHERE_API_KEY**: Used in the Reranking RAG technique for reranking retrieved documents.

Add these keys to your `.env` file as shown below:

```
OPENAI_API_KEY=your-openai-api-key
PGVECTOR_CONNECTION_STRING=your-pgvector-connection-string
TAVILY_API_KEY=your-tavily-api-key  # for adaptive and corrective rag
COHERE_API_KEY=your-cohere-api-key  # for reranking rag
```

---

## **Usage**

### Running the Notebooks
Each technique is stored in a separate folder, and each folder contains a Jupyter Notebook (`test.ipynb`) demonstrating a specific RAG technique. To run the notebooks:

1. Navigate to the relevant technique folder. For example:
    - To run **Adaptive RAG**, navigate to the `adaptive_rag/` folder:
      ```bash
      cd adaptive_rag
      ```
    - Similarly, for other techniques:
      - `cd agentic_rag`
      - `cd corrective_rag`
      - `cd self_rag`
      - `cd hyde_rag`
      - `cd reranking_rag`
      - `cd naive_rag`

2. Once in the appropriate folder, open the Jupyter Notebook:
    ```bash
    jupyter notebook test.ipynb
    ```

3. Follow the instructions in the notebook to execute the RAG technique.

### Example
- To run **Adaptive RAG**, go to the `adaptive_rag` directory and open `test.ipynb`:
    ```bash
    cd adaptive_rag
    jupyter notebook test.ipynb
    ```

    Then, follow the step-by-step instructions inside the notebook to implement and test the Adaptive RAG technique.

---