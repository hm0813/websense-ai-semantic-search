
# 🌐 **WebSense – AI Semantic Search Engine**

WebSense is a full-stack **AI-powered semantic search engine** that crawls any website, extracts HTML content, breaks it into chunks, generates embeddings, stores them in a vector database, and returns the most relevant search results using intelligent ranking.

This repository contains **both the frontend (Next.js)** and **backend (FastAPI)** inside one unified repo.

---

## 🚀 **Features**

* 🌐 Crawl any website URL
* 🔍 Search using **semantic meaning**, not just keywords
* 📄 HTML tokenization into chunks
* 🧠 Embeddings generated using Sentence Transformers
* 🗄 Vector similarity search with **ChromaDB**
* ⚡ FastAPI backend for embedding + querying
* 🖥 Beautiful Next.js UI
* 🎯 Displays top 10 most relevant HTML chunks with score
* 📦 Fully containerizable (Railway + Vercel ready)

---

## 🏗 **Repository Structure**

```
websense-ai-semantic-search/
│
├── backend/
│   ├── main.py
│   ├── requirements.txt
│   ├── chroma_db/               # Vector DB storage
│   └── (FastAPI, embedding + chunking logic)
│
├── frontend/
│   ├── app/
│   ├── components/
│   ├── next.config.js
│   ├── package.json
│   └── (Next.js UI)
│
└── README.md
```

---

# ⚙️ **Backend Setup (FastAPI)**

### 📍 Navigate to the backend folder

```bash
cd backend
```

### 📦 Install dependencies

```bash
pip install -r requirements.txt
```

### ▶️ Run the server

```bash
uvicorn main:app --reload
```

Backend runs at:

```
http://localhost:8000
```

---

# 🖼 **Frontend Setup (Next.js)**

### 📍 Navigate to the frontend

```bash
cd frontend
```

### 📦 Install npm packages

```bash
npm install
```

### ▶️ Start development server

```bash
npm run dev
```

Frontend runs at:

```
http://localhost:3000
```

---

# 🔗 **Connecting Frontend → Backend**

In your `.env` file (inside `frontend/`), make sure:

```
NEXT_PUBLIC_API_URL=http://localhost:8000
```

This allows the UI to talk to your FastAPI backend.

---

# 🧠 **How It Works (Architecture)**

### 1️⃣ User submits:

* Website URL
* Search query

### 2️⃣ Backend workflow:

* Fetch raw HTML from URL
* Clean + tokenize HTML
* Split into **500-token chunks**
* Generate embeddings using `sentence-transformers`
* Store vectors in **ChromaDB**
* Query vectors using similarity search
* Return top 10 chunks + scores

### 3️⃣ Frontend:

* Calls the backend API
* Displays results in clean card layout
* Highlights best-matching HTML segments

---

# 🗄 **Tech Stack**

### 🖥 Frontend

* Next.js 14
* React
* TailwindCSS
* TypeScript

### ⚙️ Backend

* FastAPI
* Python
* BeautifulSoup4
* Requests
* Uvicorn

### 🧠 AI / Vector Search

* Sentence Transformers
* ChromaDB

### 🚀 Deployment Ready For:

* **Vercel** (frontend)
* **Railway** (backend)

---

# 🧪 API Routes

### 🔹 Generate chunks + embeddings

```
POST /process
{
  "url": "https://example.com"
}
```

### 🔹 Search query

```
POST /search
{
  "query": "your keyword or semantic text"
}
```

---

# 📸 Screenshots (optional)

<img width="1915" height="920" alt="image" src="https://github.com/user-attachments/assets/c927f1eb-c845-4725-96d1-559b57ca98bd" />
<img width="1913" height="916" alt="image" src="https://github.com/user-attachments/assets/19e6a228-c5c0-49a2-a2e7-1ac400f50536" />
<img width="1919" height="921" alt="image" src="https://github.com/user-attachments/assets/65193dac-e9c9-4ba1-b025-b0dd7c30b55e" />
<img width="1919" height="877" alt="image" src="https://github.com/user-attachments/assets/9bf97d19-d6fe-4e36-8013-f9959a3c2c29" />
<img width="1915" height="867" alt="image" src="https://github.com/user-attachments/assets/3a3f18eb-fb1b-48f3-8919-0ee353d6f1a6" />

