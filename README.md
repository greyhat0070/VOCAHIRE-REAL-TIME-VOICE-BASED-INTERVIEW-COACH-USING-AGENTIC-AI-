# 🧠 VocaHire – Terminal-Based Voice Interview Simulator

**VocaHire** is a terminal-based voice-interactive interview agent that simulates a professional interview experience using real-time audio input, AI-powered agents, and feedback mechanisms.

---

## 🚀 Features

- 🎙️ Voice Activity Detection (VAD) for real-time recording
- 🧾 Resume-based question generation
- 🤖 Modular agent architecture (general, resume, fallback, feedback)
- 🧠 Tone analysis and STT via local Whisper
- 🗣️ Text-to-speech feedback
- 📦 Audio recording storage and logging

---

## 🧱 Tech Stack

| Layer           | Tools Used                         |
|------------------|-------------------------------------|
| Language         | Python 3.11+                        |
| Audio Processing | `webrtcvad`, `pyaudio`, `pydub`     |
| STT              | OpenAI's `whisper` (local)          |
| TTS              | `pyttsx3`, `gtts`                   |
| PDF Parsing      | `PyMuPDF (fitz)`                    |
| AI Logic         | Modular agents (`interview_agent.py`, `resume_qa_generator.py`, etc.) |
| Logging & Data   | JSON, `.wav` recordings             |
| LLM Integration  | Claude 3 Haiku via OpenRouter API, Flan-T5 |
---



## 📁 Project Structure

vocahire/
├── agents/ # Core agent modules
│ ├── interview_agent.py
│ ├── resume_qa_generator.py
│ ├── feedback_engine.py
│ └── ...
│
├── audio/ # Audio processing pipeline
│ ├── step2_vad_listener.py
│ ├── stt_whisper_local.py
│ ├── tone_analysis.py
│ ├── tts_speaker.py
│ └── step4_voice_to_langgraph.py
│
├── data/ # Logs, parsed resumes, audio recordings
│ ├── parsed_resume.json
│ └── recordings/
│
├── main.py # Entry-point for running the system
├── requirements.txt
└── .env



---

## ⚙️ Setup Instructions

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/vocahire.git
cd vocahire


2. Create a Virtual Environment (Recommended)
python -m venv .venv
.venv\Scripts\activate    # Windows

3. Install Required Packages
pip install -r requirements.txt

You may also need to install ffmpeg for audio processing and Whisper dependencies.

4. Run the Interview Script

python audio/step4_voice_to_langgraph.py





##🔊Audio Notes 
Audio recordings are saved in data/recordings/.

Logs and parsed resume data are stored in the data/ directory.

Whisper (for speech-to-text) is run locally — no OpenAI API needed.





##🧠 Agent Details
resume_qa_generator.py – Questions based on uploaded resume.

general_qa_generator.py – Common behavioral questions.

feedback_engine.py – Evaluates tone, fluency, and relevance.

fallback_qa_generator.py – Used when others don’t respond.

interview_agent.py – Main orchestration agent.





##✅ Future Enhancements
Integrate Streamlit or CLI-based menu

PDF export of feedback

Role-based interview templates

Real-time emotion/tone classification





👨‍💻 Developed by
  KOMMANA GOWTHAM 
  DAGGUMELLI SRISANTH 
  GOMPA VASAVI
