# 🚀 Gen AI Powered orchestrator for Email & Document Classification for Triage Routing

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
📹 Video demo is uploaded under https://github.com/ewfx/gaied-ai-sparklers/tree/main/artifacts/demo
🖼️ Screenshots:
![image](https://github.com/user-attachments/assets/9c4569c6-1753-4e24-9af5-0a503333d8ac)
![image](https://github.com/user-attachments/assets/df290833-6882-419b-9d56-1d0a28e8a768)
![image](https://github.com/user-attachments/assets/594299b9-301a-45eb-b0fd-c0e919192733)


## 💡 Inspiration
- Manual email processing in banking is inefficient, with high operational costs and risks of errors.
- Generative AI models (LLMs) can understand unstructured text, making it ideal for automated classification.
- OCR & Embeddings enable us to process PDFs, images, and detect duplicate emails effectively.
- We were inspired by AI-driven automation in financial services and wanted to build a scalable, explainable, and efficient solution.

## ⚙️ What It Does
- Ingests emails (.eml files) with nested attachments (PDFs, DOCX, images, and other .eml files).
- Classifies emails into predefined request types and sub-request types.
- Provision to include additional classification rules and user defined request types and sub-request types.
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
🔴 Handling Nested Emails: Gmail .eml files were tricky, requiring a fix for handling message/rfc822 properly.

🔴 Extracting Key Metadata Dynamically: Metadata fields change based on request type, so we split it into two function calls.

🔴 OCR Accuracy on Images: pytesseract had issues, so we switched to easyocr for better results.

🔴 Duplicate Detection False Positives: Fine-tuned similarity threshold to 0.90 for optimal duplicate detection.

## 🏃 How to Run
1. Clone the repository  
   ```sh
   git clone https://github.com/ewfx/gaied-ai-sparklers.git
   ```
2. Upload the python notebook from ./gaied-ai-sparklers/code/src to Google Colab by clicking File -> Upload Notebook
3. Go to google drive https://drive.google.com/drive/my-drive and create folder named EmailClassification
4. Save the open ai key in the file OpenAI_API_Key.txt under EmailClassification directory inside /content/drive/  for accessing GPT model
5. Create a sub folder emails under EmailClassification directory and upload test data from from ./gaied-ai-sparklers/code/text/dataset
6. Click Runtime -> Run all for running the code. A prompt for allowing access to google drive using your gmail id will appear. Provide necessary permissions for the execution to continue.
7. Once the run is finished, there will be gradio url generated similar to https://e74f39bb99810c3b65.gradio.live
8. Click on the same and navigate to the UI screen
9. Enter the email directory path as /content/drive/MyDrive/EmailClassification/emails/ (The path from google colab to MyDrive in gDrive is /content/drive/MyDrive)
10. Click on Classify Emails button and wait for the results
    
## 🏗️ Tech Stack
🌟 Frontend & UI: Gradio🤖 AI & NLP: GPT-4-turbo, Function Calling API

📄 Document Processing: pdfplumber, python-docx, easyocr

🧠 Vector Search & Duplicate Detection: sentence-transformers, ChromaDB

🔧 Backend & Parsing: email, BeautifulSoup

## 👥 Team
- **Prasune John** - [GitHub](https://github.com/prasune) | [LinkedIn](#)
- **Anusree A R** - [GitHub](#) | [LinkedIn](#)
- **Sangeetha Naik** - [GitHub](#) | [LinkedIn](#)
- **Partha Ojah** - [GitHub](#) | [LinkedIn](#)
- **Sai Nikhil Palukuri** - [GitHub](#) | [LinkedIn](#)
