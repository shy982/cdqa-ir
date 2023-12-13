Source Folder Structure:
```
src
├── README.md
├── arguana
│   ├── dataset
│   │   ├── documents.pkl
│   │   ├── queries.pkl
│   │   └── rel_set.pkl
│   ├── embeddings
│   │   ├── lsi-svd.pkl
│   │   └── text-embedding-ada-002-v2.pkl
│   ├── ir_techniques
│   │   ├── annoy
│   │   │   ├── index.annoy
│   │   │   └── index.pkl
│   │   ├── exact_search
│   │   │   └── index.pkl
│   │   └── faiss
│   │       ├── index.faiss
│   │       └── index.pkl
│   ├── notebooks
│   │   ├── generate_embeddings.ipynb
│   │   ├── ir_techniques.ipynb
│   │   ├── llm_w_rag.ipynb
│   │   ├── llm_wo_rag.ipynb
│   │   └── preprocess_data.ipynb
│   └── responses
│       ├── da-vinci-0.0.3
│       │   ├── llm_w_rag.pkl
│       │   └── llm_wo_rag.pkl
│       ├── gpt-3.5-turbo-instruct
│       │   ├── llm_w_rag.pkl
│       │   └── llm_wo_rag.pkl
│       └── llama-7b
│           ├── llm_w_rag.pkl
│           └── llm_wo_rag.pkl
├── cisi
│   ├── dataset
│   │   ├── documents.pkl
│   │   ├── queries.pkl
│   │   └── rel_set.pkl
│   ├── embeddings
│   │   ├── lsi-svd.pkl
│   │   └── text-embedding-ada-002-v2.pkl
│   ├── ir_techniques
│   │   ├── annoy
│   │   │   ├── index.annoy
│   │   │   └── index.pkl
│   │   ├── exact_search
│   │   │   └── index.pkl
│   │   └── faiss
│   │       ├── index.faiss
│   │       └── index.pkl
│   ├── notebooks
│   │   ├── generate_embeddings.ipynb
│   │   ├── ir_techniques.ipynb
│   │   ├── llm_w_rag.ipynb
│   │   ├── llm_wo_rag.ipynb
│   │   └── preprocess_data.ipynb
│   └── responses
│       ├── da-vinci-0.0.3
│       │   ├── llm_w_rag.pkl
│       │   └── llm_wo_rag.pkl
│       ├── gpt-3.5-turbo-instruct
│       │   ├── llm_w_rag.pkl
│       │   └── llm_wo_rag.pkl
│       └── llama-7b
│           ├── llm_w_rag.pkl
│           └── llm_wo_rag.pkl
├── get_results.ipynb
└── nfcorpus
    ├── dataset
    │   ├── documents.pkl
    │   ├── queries.pkl
    │   └── rel_set.pkl
    ├── embeddings
    │   ├── lsi-svd.pkl
    │   └── text-embedding-ada-002-v2.pkl
    ├── ir_techniques
    │   ├── annoy
    │   │   ├── index.annoy
    │   │   └── index.pkl
    │   ├── exact_search
    │   │   └── index.pkl
    │   └── faiss
    │       ├── index.faiss
    │       └── index.pkl
    ├── notebooks
    │   ├── generate_embeddings.ipynb
    │   ├── ir_techniques.ipynb
    │   ├── llm_w_rag.ipynb
    │   ├── llm_wo_rag.ipynb
    │   └── preprocess_data.ipynb
    └── responses
        ├── da-vinci-0.0.3
        │   ├── llm_w_rag.pkl
        │   └── llm_wo_rag.pkl
        ├── gpt-3.5-turbo-instruct
        │   ├── llm_w_rag.pkl
        │   └── llm_wo_rag.pkl
        └── llama-7b
            ├── llm_w_rag.pkl
            └── llm_wo_rag.pkl
```
