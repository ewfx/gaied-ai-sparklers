# 🚀 AI Powered Email & Document Classification for Triage

## 📌 Table of Contents
- [Introduction](#introduction)
- [Demo](#demo)
- [Inspiration](#inspiration)
- [What It Does](#what-it-does)
- [How We Built It](#how-we-built-it)
- [Challenges We Faced](#challenges-we-faced)
- [How to Run](#how-to-run)
- [Tech Stack](#tech-stack)
- [Team](#team)

---

## 🎯 Introduction
In commercial banking, loan servicing teams receive thousands of email requests daily. These emails often contain attachments and require manual triage by a gatekeeping team that classifies them, extracts key data, and assigns them to the right teams. This process is:
❌ Time-consuming
❌ Error-prone
❌ Operationally expensive
To automate this, we built an AI-powered solution that classifies emails, extracts metadata from both email body and attachments, and detects duplicate emails using similarity search with embeddings.

## 🎥 Demo
🔗 [Live Demo](#) (if applicable)  
📹 [Video Demo](#) (if applicable)  
🖼️ Screenshots:

![Screenshot 1](link-to-image)

## 💡 Inspiration
- Manual email processing in banking is inefficient, with high operational costs and risks of errors.
- Generative AI models (LLMs) can understand unstructured text, making it ideal for automated classification.
- OCR & Embeddings enable us to process PDFs, images, and detect duplicate emails effectively.
- We were inspired by AI-driven automation in financial services and wanted to build a scalable, explainable, and efficient solution.

## ⚙️ What It Does
- Ingests emails (.eml files) with nested attachments (PDFs, DOCX, images, and other .eml files).
- Classifies emails into predefined request types and sub-request types.
- Extracts key metadata fields (e.g., deal name, amount, effective date) from email body & attachments.
- Handles nested emails inside attachments recursively.
- Detects duplicate emails using vector embeddings and similarity search (ChromaDB).
- Displays results in an interactive UI with progress tracking and metadata visualization.

## 🛠️ How We Built It
📅 Email Ingestion & Preprocessing
- Parse .eml files with Python’s email module.
- Extract text from attachments (pdfplumber for PDFs, python-docx for DOCX, easyocr for images).
- Handle nested emails recursively.

🤖 AI-Powered Email Classification
- Uses GPT-4-turbo for request type classification based on the email body.
- Uses function calling API to extract structured metadata.

🔍 Context-Based Metadata Extraction
- Extracts key fields dynamically based on request type & sub-request type.
- Prioritizes email body over attachments for classification.

🧠 Duplicate Email Detection
- Converts email content to vector embeddings using sentence-transformers.
- Stores embeddings in ChromaDB and checks for similar emails.

📊 Interactive Gradio UI
- Accepts email directory path and processes emails with real-time progress tracking.
- Shows classification results in a structured table with expandable metadata fields.

## 🚧 Challenges We Faced
Describe the major technical or non-technical challenges your team encountered.

## 🏃 How to Run
1. Clone the repository  
   ```sh
   git clone https://github.com/your-repo.git
   ```
2. Install dependencies  
   ```sh
   npm install  # or pip install -r requirements.txt (for Python)
   ```
3. Run the project  
   ```sh
   npm start  # or python app.py
   ```

## 🏗️ Tech Stack
- 🔹 Frontend: React / Vue / Angular
- 🔹 Backend: Node.js / FastAPI / Django
- 🔹 Database: PostgreSQL / Firebase
- 🔹 Other: OpenAI API / Twilio / Stripe

## 👥 Team
- **Prasune John** - [GitHub](#) | [LinkedIn](#)
- **Anusree A R** - [GitHub](#) | [LinkedIn](#)
- **Sangeetha Naik** - [GitHub](#) | [LinkedIn](#)
- **Partha Ojah** - [GitHub](#) | [LinkedIn](#)
- **Sai Nikhil Palukuri** - [GitHub](#) | [LinkedIn](#)
