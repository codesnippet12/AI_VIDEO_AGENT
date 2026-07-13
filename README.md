# 🎥 AI Video Assistant

An AI-powered video analysis platform that converts YouTube videos or local audio/video files into structured insights using Whisper, LangChain, Mistral AI, ChromaDB, and Streamlit.

---

## 🚀 Features

### 🎙️ Audio Processing
- Extract audio from YouTube videos
- Process local audio/video files
- Automatic audio chunking for long recordings

### 📝 Transcription
- Whisper-based local transcription
- English transcription support
- Hinglish → English transcription using Sarvam AI

### 🤖 AI Analysis
- Generate meeting/video titles
- Create concise summaries
- Extract action items
- Identify key decisions
- Detect open questions

### 🔍 RAG-Powered Q&A
- Vector embeddings using Sentence Transformers
- ChromaDB vector store
- LangChain Retrieval-Augmented Generation (RAG)
- Ask questions about the video transcript

### 🌐 Streamlit Dashboard
- Modern dark-themed UI
- Transcript viewer
- Summary dashboard
- Interactive chat with video content

---

# 🏗️ Architecture

```text
                    ┌─────────────────┐
                    │ YouTube URL /   │
                    │ Local File      │
                    └────────┬────────┘
                             │
                             ▼
                 ┌─────────────────────┐
                 │ Audio Processor     │
                 │ yt-dlp + ffmpeg     │
                 └────────┬────────────┘
                          │
                          ▼
                 ┌─────────────────────┐
                 │ Audio Chunking      │
                 └────────┬────────────┘
                          │
         ┌────────────────┴──────────────┐
         ▼                               ▼
 ┌─────────────────┐         ┌─────────────────────┐
 │ Whisper         │         │ Sarvam AI           │
 │ English STT     │         │ Hinglish → English  │
 └────────┬────────┘         └──────────┬──────────┘
          │                             │
          └──────────────┬──────────────┘
                         ▼
              ┌────────────────────┐
              │ Transcript         │
              └─────────┬──────────┘
                        │
                        ▼
          ┌─────────────────────────────┐
          │ Mistral AI + LangChain      │
          └─────────┬───────────────────┘
                    │
                    ├── Summary
                    ├── Title
                    ├── Action Items
                    ├── Decisions
                    └── Questions
                    │
                    ▼
          ┌─────────────────────────────┐
          │ Vector Store (ChromaDB)     │
          └─────────┬───────────────────┘
                    │
                    ▼
          ┌─────────────────────────────┐
          │ RAG Question Answering      │
          └─────────────────────────────┘
```

---

# 🛠️ Tech Stack

| Category | Technology |
|-----------|------------|
| Frontend | Streamlit |
| Speech-to-Text | OpenAI Whisper |
| Hinglish Translation | Sarvam AI |
| LLM | Mistral AI |
| RAG Framework | LangChain |
| Vector Database | ChromaDB |
| Embeddings | Sentence Transformers |
| Audio Processing | FFmpeg |
| YouTube Downloader | yt-dlp |
| Language | Python 3.12 |

---

# 📂 Project Structure

```text
AI_VIDEO_AGENT/
│
├── app.py
├── main.py
├── Requirements.txt
│
├── core/
│   ├── transcriber.py
│   ├── summarizer.py
│   ├── extractor.py
│   ├── rag_engine.py
│   └── vector_store.py
│
├── utils/
│   └── audio_processor.py
│
├── downloads/
│
├── vector_db/
│
└── .env
```

---

# ⚙️ Installation

## Clone Repository

```bash
git clone https://github.com/codesnippet12/AI_VIDEO_AGENT.git
cd AI_VIDEO_AGENT
```

## Create Virtual Environment

```bash
uv venv
```

### Windows

```bash
.venv\Scripts\Activate.ps1
```

### Git Bash

```bash
source .venv/Scripts/activate
```

## Install Dependencies

```bash
uv pip install -r Requirements.txt
```

---

# 🔑 Environment Variables

Create a `.env` file:

```env
MISTRAL_API_KEY=your_mistral_api_key
SARVAM_API_KEY=your_sarvam_api_key
```

---

# ▶️ Running the Application

## Streamlit UI

```bash
streamlit run app.py
```

Open:

```text
http://localhost:8501
```

---

# 💬 Example Workflow

1. Enter YouTube URL
2. Choose Language
3. Generate Transcript
4. View:
   - Title
   - Summary
   - Action Items
   - Key Decisions
   - Open Questions
5. Chat with the Video using RAG

---

# 📸 Screenshots

## Dashboard

Add screenshot here:

```text
screenshots/dashboard.png
```

## Summary View

Add screenshot here:

```text
screenshots/summary.png
```

## RAG Chat

Add screenshot here:

```text
screenshots/chat.png
```

---

# 🔮 Future Improvements

- Speaker diarization
- PDF export
- Multi-language support
- Video upload support
- Meeting analytics dashboard
- Cloud deployment
- GPU inference support

---

# 👨‍💻 Author

**Subhranil Das**

- GitHub: https://github.com/codesnippet12
- LinkedIn: https://www.linkedin.com/in/subhranil-das-software-engineer/

---

# ⭐ Support

If you found this project useful, consider giving it a star ⭐ on GitHub.
