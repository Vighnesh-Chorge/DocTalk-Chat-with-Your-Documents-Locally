# 📖 Notes to Answer — Local PDF Q&A using Llama 3.2

Ask questions from any PDF document. Llama 3.2 answers strictly from your uploaded notes — no internet, no API key, runs 100% on your machine.

---

# 🚀 What it does

* You upload any PDF (notes, resume, textbook, report)
* PyMuPDF extracts all the text from it
* That text is injected into Llama's system prompt as context
* You ask questions in a loop → Llama answers only from your document

This is the core idea behind RAG (Retrieval Augmented Generation) — instead of training a model on your data, you just give it the right context at the right time.

---

# 🧠 How it works

```text
PDF file
   ↓
PyMuPDF extracts text
   ↓
Text → injected into system prompt
   ↓
User asks question
   ↓
Llama 3.2 answers from the document
   ↓
Answer printed in Jupyter
```

No embeddings. No vector database. No fine-tuning.

Just clean context injection via prompt engineering.

---

# 📦 Tech Stack

| Tool             | Purpose                    |
| ---------------- | -------------------------- |
| Python           | Core language              |
| PyMuPDF (`fitz`) | Extract text from PDF      |
| Ollama           | Run Llama 3.2 locally      |
| Llama 3.2        | LLM that answers questions |
| Jupyter Notebook | Interactive environment    |

---

# ⚙️ Setup

## 1. Install Ollama

Download from https://ollama.com and pull the model:

```bash
ollama pull llama3.2
```

---

## 2. Install Python dependencies

```bash
pip install pymupdf ollama
```

---

## 3. Run the notebook

Open the `.ipynb` file in Jupyter and run cells one by one.

---

# 🧪 Example — tested on my own resume

```text
Q: What is Vighnesh's CGPA?

A: According to the notes, Vighnesh's CGPA is 8.0 from MGM College
   of Engineering and Technology, University of Mumbai.


Q: Tell me about his projects.

A: The notes mention 3 projects...


Q: Rate this resume out of 10.

A: Based on the information provided, I would rate this resume 8/10...


Q: Is Vighnesh worth hiring?

A: Yes, he appears to be a strong candidate based on his academic
   performance, projects, and skills listed in the notes.
```

---

# 💡 Key Concept Learned

> You don't need to train or fine-tune a model to make it answer from your own data.
>
> You just need to give it the right context — that's **context injection**, and it's the foundation of how RAG systems work.

### What this project taught me:

* How system prompts control model behaviour
* How to restrict LLM answers to a specific document
* How local LLMs work through Ollama
* The foundation of how tools like ChatGPT's file upload work internally

---

# 🔮 What's next

*  FAISS vector search for large documents (semantic retrieval)
*  Multi-document Q&A
*  Streamlit web UI
*  AI automation workflows
