🧠 YouTube RAG — AI-Powered YouTube Video Analyzer

This project is an AI-powered YouTube content assistant that allows you to extract, analyze, and interact with YouTube video transcripts using Retrieval-Augmented Generation (RAG).

It integrates:

🎥 YouTube Transcript Extraction

🧩 Text Chunking & Vector Embeddings

💬 Google Gemini (ChatGoogleGenerativeAI) for LLM Responses

📚 Chroma Vector Store for Context Retrieval

🤗 Hugging Face Embeddings for Semantic Search

🚀 Features

✅ 1. Transcript Extraction
Automatically extracts subtitles from any YouTube video using the YouTubeTranscriptApi.

✅ 2. Translation to English
Translates non-English transcripts to English with cultural and contextual accuracy using Google Gemini.

✅ 3. Chunking & Embeddings
Splits long transcripts into semantic chunks using RecursiveCharacterTextSplitter,
and generates embeddings via Hugging Face (sentence-transformers/all-MiniLM-L6-v2).

✅ 4. Vector Store Creation
Stores embeddings in a Chroma vector database for fast semantic retrieval.

✅ 5. RAG-based Q&A
Uses Retrieval-Augmented Generation — fetches the most relevant transcript chunks and generates intelligent, context-aware answers.

✅ 6. Notes & Topic Extraction
Automatically generates structured, easy-to-read notes and highlights the 5 most important topics from the video.

🧠 Tech Stack
| Component              | Technology                        |
| ---------------------- | --------------------------------- |
| LLM                    | Google Gemini 2.5 Flash Lite      |
| Framework              | LangChain                         |
| Embeddings             | Hugging Face (`all-MiniLM-L6-v2`) |
| Vector DB              | Chroma                            |
| Transcript API         | YouTubeTranscriptApi              |
| UI Framework           | Streamlit                         |
| Environment Management | dotenv                            |

🧩 Folder Structure
YouTube-RAG/
│
├── app.py                   # Streamlit UI
├── main.py                  # Core RAG logic
├── .env                     # API keys (Google + Hugging Face)
├── requirements.txt          # Dependencies
├── README.md                 # Project documentation
└── vectorstore/              # (Optional) Saved Chroma DB

⚙️ Installation & Setup
1️⃣ Clone the Repository
git clone https://github.com/<your-username>/YouTube-RAG.git
cd YouTube-RAG

2️⃣ Create and Activate Virtual Environment
python -m venv .venv
source .venv/bin/activate       # for Linux/Mac
.venv\Scripts\activate          # for Windows

3️⃣ Install Dependencies
pip install -r requirements.txt

4️⃣ Create .env file

Create a file named .env in the root directory and add:

GOOGLE_API_KEY=your_gemini_api_key_here
HUGGINGFACEHUB_API_TOKEN=your_huggingface_token_here

5️⃣ Run the App
streamlit run app.py

🧠 How It Works

Enter a YouTube video URL

The app fetches the transcript (and translates if needed).

The transcript is split into chunks for embedding.

Each chunk is embedded using Hugging Face embeddings.

Embeddings are stored in a Chroma vector store.

You can now chat with the video, ask questions, get notes, or see key topics.
