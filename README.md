**Lightweight Retreival Augmented Generation**

This repository implements a Response Augmentation Generation (RAG) model for contextualizing information retrieval from PDFs. Built using Gradio, the model takes a PDF document as input and leverages the Gemini API to generate a response.

The model first processes the PDF through an embedding layer, converting textual information into a numerical representation. Cosine similarity is then employed to identify sections within the PDF that hold the most relevant context to the user's query. This contextualization process even incorporates chat history, ensuring the response considers the entire conversation thread.

Added Hierarchical Navigable Small World (HNSW) support for retrieval boosting retrieval speed. In my test I have uploaded a research paper having 1800 words, with normal consine similarity it took 0.5 seconds for fetching relevant context. With HNSW it took 0.0012 seconds. 

Flow: 
![flow chart](https://github.com/harinaralasetty/Retrieval_Augmented_Generation/blob/main/RAG%20+%20HNSW.png)

To run: 
1. Install requirements on your python env.
2. Get Google Vertex API key from https://aistudio.google.com/app/apikey and insert in config.json
3. Set retrieval mode to 'cosine' or 'hnsw' in config.json (hnsw is the default and faster)
4. Run server.py

![alt text](https://github.com/harinaralasetty/Retrieval_Augmented_Generation/blob/main/screenshot.png)
