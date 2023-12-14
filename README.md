# cdqa-ir
Experimental comparison of Numerical &amp; Generative Techniques for CDQA and IR, conducted as part of DSC 210 Fall '23 UCSD


# Overview:

This project focused on evaluating Closed Domain Question Answering (CDQA) through a comprehensive exploration of Numerical Linear Algebra (NLA) and state-of-the-art (SOTA) techniques. Leveraging NLA, methods like Latent Semantic Indexing (LSI) were employed to process textual data, reducing dimensionality through Singular Value Decomposition (SVD). The study extensively compared the NLA approach with SOTA methods, including Retrieval Augmented Generation (RAG) and Large Language Models (LLMs) such as GPT-3.5-turbo. Experiments involved a variety of datasets of questions, documents and ground truth, assessing accuracy and response times. Multiple sub-experiments were also performed to evaluate the technical soundness of main experimental strategy. Results indicated that while NLA offered a foundational methodology, modern techniques significantly outperformed it, reaffirming the importance of staying abreast of evolving methodologies in CDQA. The project also validated the choice of using RAG with LLMs and established VectorDB as a superior Information Retrieval system. The findings contribute to ongoing efforts in refining and tailoring models for CDQA, aligning them with the dynamic challenges posed by diverse knowledge domains.

# How to Run: 

1. **Python Requirements**: 
    - A Python 3.9.6+ kernel is recommended to run this project. Since the project mainly consists of .ipynb notebooks, we recommend the installation of [Jupyter Notebook](https://jupyter.org/install).
    - Clone the repository and navigate to the root folder of the project. 
    - Optional: Create a virtual environment for this project (use ``venv`` or ``conda``)
    - Install all dependencies from the [requirements.txt](https://github.com/shy982/cdqa-ir/blob/main/requirements.txt) file with the command ``pip install -r requirements.txt``

2. **OpenAI Token Requirements**: 

    - A valid OpenAI token would be necessary (to generate OpenAI embeddings and GPT/Davinci LLM responses) to run majority of the project. 
    - You'll need to add the `OPENAI_API_KEY` to a .env file. An `env.example` is given in the root directory of the repo (open to see instructions). 
    - To get the API token, please follow instructions in [OpenAI API](https://openai.com/blog/openai-api). 
    - **To run just the [Results Notebook](https://github.com/shy982/cdqa-ir/blob/main/src/get_results.ipynb), you do not need the key.**

3. Once these steps are complete, please refer to the next section to understand the project layout. 

# Project Flow:

1. Our project is primarily composed of Jupyter notebooks each performing a specific subpart of the project. We have all the experiments in the ``src`` folder. Experiments are organized based on the datasets used. i.e. ``src/cisi`` will have all experiments performed on the CISI dataset.

2. Refer to the [Project Structure](https://github.com/shy982/cdqa-ir/blob/main/src/README.md) to understand the file organization and hierarchy. 

3. The [Results Notebook](https://github.com/shy982/cdqa-ir/blob/main/src/get_results.ipynb) has the compiled results of all our experiments and sub-experiments. Running this notebook will read, process, and compute all results from the responses and data pickle files for each dataset using the corresponding models. These results have been added in our [Notion]() report as well.

4. If you wish to separately run individual experimental sections for a specific dataset: 

    - Navigate to the corresponding dataset subdirectory, i.e. ``src/{dataset}`` For ex. ``src/nfcorpus``. 
    - ``src/{dataset}/notebooks`` contains the notebooks explaining every step of processing towards CDQA.
    - The notebook names are self-explanatory, For ex. ``src/{dataset}/notebooks/preprocess_data.ipynb`` has the code to pre-process, clean and pickle the documents, queries, and ground truth's for the corresponding dataset.
    - Similarily ``src/{dataset}/notebooks/generate_embeddings.ipynb`` generates all LSI (reduced vectors), and OpenAI embeddings. 
    - To run the experiments without RAG, refer to notebooks named ``src/{dataset}/notebooks/llm_wo_rag.ipynb``. 
    - Similarily, if you would like to run experiments with RAG, the NLA (LSI) approach for RAG is given ``src/{dataset}/notebooks/llm_w_rag_exact_search.ipynb`` and the SOTA VectorDB approach (with FAISS) is given in ``src/{dataset}/notebooks/llm_w_rag_faiss.ipynb``. 

5. **Datastores & Pickle Files**: If you wish to view the intermediate outputs after each stage of the RAG pipeline, You can do so by manually loading and viewing pickle files corresponding to the steps. 

    - ``src/{dataset}/dataset/``: Pickled, pre-processed, cleaned documents, queries, and ground truth files for the dataset. i.e. output of the ``preprocess_data.ipynb`` notebook.
    - ``src/{dataset}/embeddings/``: Pickled OpenAI & LSI embeddings in corresponding folders. i.e. the output of ``generate_embeddings.ipynb`` notebook.
    - ``src/{dataset}/ir_techniques/``: Index files necessary for IR in the RAG pipeline for each mode of IR, i.e. NLA technique (output of LSI + Truncated SVD) and SOTA techniques (``FAISS``/``ANNOY`` VectorDB index files). 
    - ``src/{dataset}/responses/``: LLM-specific responses for the queries in the dataset. This includes pickled responses from all LLMs we ran for that dataset. For ex - ``src/nfcorpus/responses/gpt-3.5-turbo-instruct/llm_w_rag_exact_search.pkl`` has the responses returned by ``gpt-3.5-turbo`` with LSI + SVD (exact_search) as the IR technique used for RAG. 

# Notes:

1. Raise PR on separate branch for code updates & request code owner review.
2. Mark TODO's as issues.

# Collaboration: 

We appreciate any ideas and contributions from the fellow open-source community. 

We aim to make this project accessible and modularized enough to use as a plug-and-play model for evaluating traditional and modern Closed Domain Question Answering approaches. 

Please feel free to contact the authors if you are interested to contribute or collaborate: 

- [Sanidhya Singal](https://www.github.com/sayhitosandy)
- [Shyam Renjith](https://www.github.com/shy982)
- [Srinivas Thillaisthanam Raman](https://github.com/srinivasraman18)