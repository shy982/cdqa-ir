Source Folder Structure:

```
src/
├── README.md
├── arguana...
├── cisi
│   ├── dataset
│   │   ├── documents.pkl
│   │   ├── original
│   │   │   ├── CISI.ALL
│   │   │   ├── CISI.QRY
│   │   │   └── CISI.REL
│   │   ├── queries.pkl
│   │   └── rel_set.pkl
│   ├── embeddings
│   │   ├── lsi
│   │   │   ├── documents.pkl
│   │   │   └── queries.pkl
│   │   └── text-embedding-ada-002-v2
│   │       ├── documents.pkl
│   │       └── queries.pkl
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
│   │   ├── llm_w_rag_exact_search.ipynb
│   │   ├── llm_w_rag_faiss.ipynb
│   │   ├── llm_wo_rag.ipynb
│   │   └── preprocess_data.ipynb
│   └── responses
│       ├── da-vinci-0.0.3
│       │   ├── llm_w_rag_faiss.pkl
│       │   └── llm_wo_rag.pkl
│       ├── gpt-3.5-turbo-instruct
│       │   ├── llm_w_rag_exact_search.pkl
│       │   ├── llm_w_rag_faiss.pkl
│       │   └── llm_wo_rag.pkl
│       └── llama-7b
│           ├── llm_w_rag_faiss.pkl
│           └── llm_wo_rag.pkl
├── get_results.ipynb
└── nfcorpus...
```
