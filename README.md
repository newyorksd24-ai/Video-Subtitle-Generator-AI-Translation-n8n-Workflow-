# 🎬 Video Subtitle Generator – AI Translation (n8n Workflow)

A simple but powerful **n8n workflow** that automatically generates **English SRT subtitles** starting from an Italian video, using **Whisper for transcription** and **GPT for translation and technical refinement**.

Designed for technical demos, software tutorials, and automation showcases.

---

## 🚀 What It Does

1. Downloads a video from **Google Drive**
2. Extracts audio and sends it to **Whisper API**
3. Receives a detailed transcription with timestamps
4. Sends transcript segments to **GPT** for:
   - Italian → English translation  
   - Grammar and clarity correction  
   - Technical terminology refinement  
5. Converts segments into an **.SRT subtitle file**
6. Outputs a ready-to-use subtitle file

---

## 🧩 Workflow Structure


---

## 🔧 Nodes Overview

### 1. Manual Trigger
Starts the workflow manually.

### 2. Google Drive – Download File
- Resource: File  
- Operation: Download  
- Binary Field: `data`

### 3. HTTP Request – Whisper API
- Method: POST  
- Endpoint: `/v1/audio/transcriptions`  
- Model: `whisper-1`  
- Language: `it`  
- Response Format: `verbose_json`  
- File: Binary data from previous node  

### 4. OpenAI – GPT Translate & Refine
- Model: `gpt-4o-mini`  
- Input: Whisper JSON segments  
- Responsibilities:
  - Natural translation
  - Technical term correction
  - Preserve timestamps
  - Keep exact JSON structure

### 5. Code Node – Generate SRT
- Language: JavaScript  
- Converts seconds → SRT time format  
- Generates `subtitles.srt`  
- Outputs a binary file ready for download or reuse

---

## 📁 Output

- **Format:** `.srt`  
- **Content:** Time-synchronized English subtitles  
- **Usage:** YouTube, Vimeo, video players, technical demos

---

## 🛠 Requirements

- n8n (Cloud or Self-Hosted)
- Google Drive account
- OpenAI API Key
- HTTP Bearer credentials

---

## 🔐 Required Credentials

| Service | Type |
|--------|------|
| Google Drive | OAuth2 |
| OpenAI | API Key |
| HTTP Request | Bearer Auth |

---

## 🎯 Use Cases

- Automation demos  
- Technical tutorials  
- Educational videos  
- Product presentations  
- Developer / Automation Engineer portfolios  

---

## 💡 Strengths

- Fully automated pipeline  
- Professional-quality subtitles  
- Correct technical terminology  
- Ready-to-use output  
- Modular and reusable design  

---

## 🔄 Possible Extensions

- Automatic multi-language support  
- Direct YouTube upload  
- Google Drive / S3 storage  
- Webhook interface  
- Batch video processing  

---

## 📦 Workflow File

Import directly into n8n:

`Video Subtitle Generator - AI Translation.json`

---

## 🧠 Technical Notes

- Whisper returns timestamped segments (`start`, `end`)
- GPT keeps the JSON structure unchanged
- The Code Node handles:
  - JSON parsing
  - Markdown cleanup
  - Time formatting
  - Binary SRT file creation

---

## 👤 Author Purpose

This workflow demonstrates skills in:

- Automation Engineering  
- API Integration  
- AI Workflow Design  
- Data Transformation  

---

## License

Free to use for educational and demonstration purposes.
