# 🎬 AI Video Subtitle Generator – n8n Workflow

## Overview
This project is an **n8n automation workflow** that automatically generates subtitles from videos and translates them into multiple languages using AI.

The workflow combines **Google Drive**, **OpenAI Whisper**, and **GPT models** to create a fully automated subtitle pipeline.

**Goal:**  
From a single video file → **Transcription → Translation → `.srt` Subtitle File**

---

## Core Features
- Automatic audio transcription (Whisper)
- AI-powered translation (GPT)
- Multi-language subtitle generation
- `.srt` file creation with accurate timestamps
- Google Drive integration
- Fully automated n8n workflow
- Scalable and modular structure

---

## Workflow Structure

### 1. Trigger
Manual or Webhook trigger to start the workflow.

### 2. Google Drive – Download Video
Downloads the video file and stores it as binary data.

### 3. Set Language Parameters
Defines:
- `targetLang` → Subtitle output language
- `sourceLang` → Auto-detect or manual
- `targetName` → Language name (English, Spanish, German…)

### 4. Whisper – Audio Transcription
- Converts speech to text
- Auto-detects spoken language
- Outputs **segments + timestamps**

### 5. Merge Node
Combines:
- Language parameters
- Whisper transcript segments

### 6. GPT – Translate & Refine
- Translates each segment into the target language
- Preserves timestamps
- Ensures natural phrasing

### 7. Code – Generate SRT File
- Formats subtitles into `.srt`
- Keeps timing precision
- Outputs downloadable file

---

## Supported Languages (Example)
- English (EN)
- Spanish (ES)
- German (DE)
- Italian (IT)

Additional languages can be added easily.

---

## Requirements
- n8n (Cloud or Self-Hosted)
- OpenAI API Key
- Google Drive Access
- Code Node enabled

---

## Possible Extensions
- Direct YouTube upload
- Batch video processing
- Webhook API interface
- Cloud storage export (S3 / Drive)
- User-selected target language
- Automatic language detection logic

---

## Use Cases
- YouTube content
- Online courses
- Product demos
- Marketing videos
- Training materials
- Multilingual documentation

---

## Project Goal
A **scalable AI-powered subtitle generator** that eliminates manual editing and integrates easily into larger automation systems.

---

## Author
**Fabio Roggero**  
Languages: Italian • English • Spanish • German  
Focus: Workflow Automation • AI Integration • n8n
