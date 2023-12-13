# cdqa-ir
Experimental comparison of Numerical &amp; Generative Techniques for CDQA and IR, conducted as part of DSC 210 Fall '23 UCSD


# Overview:

The project focused on enhancing Closed Domain Question Answering (CDQA) through a comprehensive exploration of Numerical Linear Algebra (NLA) and state-of-the-art (SOTA) techniques. Leveraging NLA, methods like Latent Semantic Indexing (LSI) were employed to process textual data, reducing dimensionality through Singular Value Decomposition (SVD). The study extensively compared the NLA approach with SOTA methods, including Retrieval Augmented Generation (RAG) and Large Language Models (LLMs) such as GPT-3.5-turbo. Experiments involved datasets of medical questions, assessing accuracy and response time. Results indicated that while NLA offered a foundational methodology, modern techniques significantly outperformed it, reaffirming the importance of staying abreast of evolving methodologies in CDQA. The project also validated the choice of using RAG with LLMs and established VectorDB as a superior Information Retrieval system. The findings contribute to ongoing efforts in refining and tailoring models for CDQA, aligning them with the dynamic challenges posed by diverse knowledge domains.

# How to Run:

1. Our project is primarily composed of Jupyter notebooks each performing a specific subpart of the project. We have all the experiments in the ``src`` folder. All the experiments are organized based on the datasets used. 

2. Refer to this [Project Structure](https://github.com/shy982/cdqa-ir/blob/main/src/README.md) to understand the file organization and hierarchy. 

3. The [Results Notebook](https://github.com/shy982/cdqa-ir/blob/main/src/get_results.ipynb) has the compiled results of all our experiments and sub-experiments (These results have been added in our [Notion]() report as well). Running this notebook will read, process, and compute all results from the responses and dataset pickle files for each dataset using the corresponding models. 

4. **OpenAI Token**: To run the project a valid OpenAI token would be necessary (to generate OpenAI embeddings and GPT/Davinci LLM responses). You'll need to add the `OPENAI_API_KEY` to a .env file. An `env.example` is given in the root directory of the repo (open to see instructions). To get the API token follow instructions in [OpenAI API](https://openai.com/blog/openai-api)

5. If you wish to separately run the experiments for a specific dataset: 
    - Navigate to the corresponding dataset subdirectory, i.e. ``src/{dataset}`` 
    - Navigate to ``src/{dataset}/notebooks`` to find the notebooks explaining each and every step of processing towards CDQA.
    - The notebook names are self-explanatory, For ex. ``src/{dataset}/notebooks/preprocess_data.ipynb`` has the code to pre-process, clean and pickle the documents, queries, and ground truth's for the corresponding dataset.
    - Similarily ``src/{dataset}/notebooks/generate_embeddings.ipynb`` Generate all LSI (reduced vectors), and OpenAI embeddings. 
    - To run the experiments without RAG, refer to notebooks labeled ``src/{dataset}/notebooks/llm_wo_rag.ipynb``. 
    - Similarily, if you would like to run experiments with RAG, the NLA (LSI) approach for RAG is given ``src/{dataset}/notebooks/llm_w_rag_exact_search.ipynb`` and the SOTA VectorDB approach (with FAISS) is given in ``src/{dataset}/notebooks/llm_w_rag_faiss.ipynb``. 

6. **Data stores & Pickle Files**: If you wish to view the processed data across each stage of the RAG pipeline. You can manually load and view pickle files that are neatly organized corresponding to the steps. 
    - ``src/{dataset}/dataset/`` will have the pickled, pre-processed, cleaned documents, queries, and ground truth files for the dataset. i.e. output of the ``preprocess_data.ipynb`` notebook.
    - ``src/{dataset}/embeddings/`` will have the pickled OpenAI & LSI embeddings in corresponding folders. i.e. the output of ``generate_embeddings.ipynb`` notebook.
    - ``src/{dataset}/ir_techniques/`` will have the index files necessary for IR in the RAG pipeline for each mode of IR, i.e. NLA technique (output of LSI + Truncated SVD) and SOTA techniques FAISS, ANNOY VectorDB index files. 
    - ``src/{dataset}/responses/`` will have the corresponding LLM responses for the queries in the dataset. This includes pickled responses from all LLMs we ran for that dataset. For ex - ``src/nfcorpus/responses/gpt-3.5-turbo-instruct/llm_w_rag_exact_search.pkl`` has the responses given by ``gpt-3.5-turbo`` LLM with LSI + SVD (exact_search) as the IR technique used for RAG. 

# Notes:

1. Raise PR for Code updates (Anything to src directory)
2. Read env.example to create .env for storing API tokens
3. Mark TODO's as issues

# Collaboration: 

We appreciate any ideas and contributions from the fellow open-source community. 

We aim to make this application accessible and modularized enough to use as a plug-and-play model for Closed Domain Question Answering. 

Please feel free to contact the authors if you are interested to contribute or collaborate: 

- [Sanidhya Singal](https://www.github.com/sayhitosandy)
- [Shyam Renjith](https://www.github.com/shy982)
- [Srinivas Thillaisthanam Raman](https://github.com/srinivasraman18)