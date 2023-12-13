Example Folder Structure (CISI Dataset):
```
cisi
├── dataset
│   ├── documents.pkl
│   ├── queries.pkl
│   └── rel_set.pkl
├── embeddings
│   ├── lsi-svd.pkl
│   └── text-embedding-ada-002-v2.pkl
├── responses
│   ├── da-vinci-0.0.3
│   │   ├── llm_w_rag.pkl
│   │   └── llm_wo_rag.pkl
│   ├── gpt-3.5-turbo-instruct
│   │   ├── llm_w_rag.pkl
│   │   └── llm_wo_rag.pkl
│   └── llama-7b
│       ├── llm_w_rag.pkl
│       └── llm_wo_rag.pkl
└── vectordbs
    ├── annoy
    │   ├── index.annoy
    │   └── index.pkl
    └── faiss
        ├── index.faiss
        └── index.pkl
```
