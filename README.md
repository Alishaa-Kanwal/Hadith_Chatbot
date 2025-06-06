# 📖 Hadith Chatbot (Semantic Search using FAISS + NLP)

A ChatGPT-style Islamic Chatbot designed to retrieve the **most relevant Hadiths** based on user input using **semantic similarity**, not just keyword search. Built using **FAISS**, **MiniLM embeddings**, and a custom frontend with **chat history sidebar** like ChatGPT.

---

## 🚀 Demo

▶️ [Watch Demo + Concept Explanation on YouTube](https://youtu.be/2fjdc9IIkwc?si=N2E-B6vLJCSbKIlO)

---

## 🧠 Core Features

- 🔍 **Semantic Hadith Retrieval** using sentence-transformer embeddings
- 🧠 **FAISS Vector Search** for fast similarity comparison
- 💬 **Chat-style UI with history sidebar** (inspired by ChatGPT)
- 🌐 **Handles Arabic and English** Hadith texts
- ✨ Clean frontend using HTML, CSS, JS

---

## 📊 Dataset Used

**Name:** LK-Hadith-Corpus  
**Source:** GitHub  
**Contains:** Hadiths in English and Arabic, with metadata like chapter, grading, isnad, etc.

### 🧹 Preprocessing Steps:
- Cleaned English Hadiths with regex
- Saved as `cleaned_hadith_csv.csv` in `data/` folder

---

## 🛠 Technologies & Libraries

| Purpose              | Tools / Libraries                         |
|----------------------|-------------------------------------------|
| Embeddings           | `sentence-transformers` (MiniLM-L6-v2)    |
| Vector Search        | `FAISS` (Facebook AI Similarity Search)   |
| Data Handling        | `pandas`, `numpy`, `regex`                |
| Frontend             | `HTML`, `CSS`, `JavaScript`, `Flask`      |
| Search Optimization  | Vectorized search with cosine similarity  |

---

## 📁 Folder Structure

hadith_chatbot/
├── app.py                                        # Main Flask app
├── model_training_code.ipynb                     # Embedding generation & FAISS indexing
├── requirements.txt
├── data/
│ └── cleaned_hadith_csv.csv                      # Preprocessed Hadith dataset
├── model/
│ ├── faiss_index.faiss                           # FAISS index
│ ├── hadith_embedding.npy                        # Embedding vectors
│ └── model_load.py                               # Embedding + FAISS loader
├── static/
│ ├── css/styles.css                              # Frontend styling
│ └── js/scripts.js                               # JS interactivity
├── templates/
│ └── index.html                                  # Chat UI
└── README.md                                     # Project overview (this file)



---

## 💡 How It Works

1. User inputs a natural language query (e.g., *"Tell me about prayer."*).
2. The query is embedded using `MiniLM-L6-v2`.
3. FAISS retrieves the **top-k most semantically similar Hadiths**.
4. The result is shown in a **chat interface**, stored in a **sidebar** history log.

---

## 🧪 How to Run Locally

```bash
# Clone the repo
git clone https://github.com/Alishaa-Kanwal/Hadith_Chatbot
cd hadith_chatbot

# Activate virtual environment (optional)
source venv/bin/activate    # Mac/Linux
venv\Scripts\activate       # Windows

# Install dependencies
pip install -r requirements.txt

# Run the app
python app.py
