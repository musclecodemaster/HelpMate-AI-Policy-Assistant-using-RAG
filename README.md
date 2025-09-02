   # HelpMate-AI-Policy-Assistant-using-RAG

   ## 📌 Overview
HelpMate AI is an AI-powered assistant designed to read insurance policy documents (PDFs) and provide direct, citation-backed answers to user queries.  
The project leverages **Retrieval-Augmented Generation (RAG)**, combining information retrieval with generative AI.

---

## ⚙️ Features
- Extracts and preprocesses text from insurance policy PDFs.
- Creates vector embeddings of text chunks using **SentenceTransformers**.
- Retrieves top relevant passages for a given query using **cosine similarity**.
- Re-ranks passages with a **CrossEncoder** to ensure accuracy.
- Generates precise answers using **Flan-T5**, including page citations.
- Implements caching for faster performance.

---

## 🏗️ System Architecture
1. **PDF Processing** – Extract text, clean, and chunk into segments (~180 words).  
2. **Embeddings** – Convert chunks into dense vectors.  
3. **Vector Indexing** – Store vectors for similarity search.  
4. **Retrieval** – Get top candidate chunks for a query.  
5. **Reranking** – Select the most relevant chunks using CrossEncoder.  
6. **Prompt Building** – Build structured context with citations.  
7. **Answer Generation** – Generate concise answers with references.

---

## 📦 Requirements
Install dependencies:
```bash
pip install -r requirements.txt
```

Key libraries used:
- `pypdf`
- `sentence-transformers`
- `transformers`
- `scikit-learn`
- `diskcache`
- `numpy`

---

## ▶️ Usage
1. Place your **policy PDF** in the project folder.  
2. Update the `PDF_PATH` variable in the script with your file path.  
3. Run the pipeline:
```bash
python HelpMate AI Project_V4.pynb
```
4. Enter your query when prompted, e.g.:
```
What is the grace period for premium payment?
```

---

## 📊 Example Queries & Outputs
**Query:** What is the grace period for premium payment?  
**Answer:** Grace Period of 31 days is allowed after premium due date. [p.20]  

**Query:** Who is eligible under this policy?  
**Answer:** A person is eligible after 30 consecutive days of active work with the policyholder. [p.27]  

---

## 🛠️ Challenges & Fixes
- **Keras 3 compatibility issue** → Installed `tf-keras` for Hugging Face compatibility.  
- **Faiss installation issue** → Replaced with `scikit-learn` cosine similarity.  
- **Sequence length errors** → Reduced chunk size and rerank input.  

---

## 🚀 Future Enhancements
- Use **FAISS** or **ChromaDB** for scalable vector indexing.  
- Replace Flan-T5 with larger LLMs (e.g., GPT/Claude) for better reasoning.  
- Build a **Streamlit/Gradio UI** for real-time interaction.  

---

## 👨‍💻 Author
Simhadri Sai Krishna – Lead AI/ML Engineer.
