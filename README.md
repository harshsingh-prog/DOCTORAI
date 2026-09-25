# 🩺 DoctorAI — AI-Powered Medical Imaging & Clinical Report Assistant

> **An AI-powered medical imaging assistant for image analysis, clinical report understanding, contextual Q&A, and collaborative case discussion.**

DoctorAI is a Generative AI-powered healthcare application designed to assist users and medical professionals in understanding medical images and clinical reports.

The system combines **multimodal AI, LLM-based reasoning, semantic retrieval, contextual question answering, and collaborative case discussions** into a unified workflow.

It is designed as an **AI-assisted decision-support system**, not as a replacement for qualified medical professionals.

---

## ✨ Key Features

### 🖼️ AI Medical Image Analysis

Upload a medical image and use an AI-powered analysis workflow to extract structured clinical information.

The analysis pipeline is designed to cover:

* Imaging modality identification
* Anatomical region identification
* Image quality and technical adequacy
* Key imaging findings
* Abnormality descriptions
* Location, size, shape, and characteristics
* Severity assessment
* Diagnostic assessment
* Differential diagnoses
* Critical or urgent findings
* Patient-friendly explanations
* Relevant medical research context

The system uses structured prompting to produce consistent and readable medical-image analysis.

---

### 🧠 Generative AI Medical Assistant

DoctorAI uses OpenAI-powered language models to generate contextual responses based on:

* Medical image findings
* Case descriptions
* User questions
* Previously generated analyses
* Clinical context

The system is designed to communicate in a collaborative format, allowing users to ask follow-up questions about a case rather than receiving only a single static prediction.

---

### 🔎 Medical Report Q&A with Semantic Retrieval

DoctorAI includes a report question-answering system that allows users to ask questions about previously analyzed medical reports.

The workflow includes:

```text
User Question
      ↓
Query Embedding
      ↓
Semantic Similarity Search
      ↓
Relevant Medical Analyses
      ↓
Context Construction
      ↓
LLM
      ↓
Contextual Answer
```

The system generates embeddings for stored analyses and uses **cosine similarity** to identify the most relevant previous medical contexts before generating an answer.

This allows the application to move beyond simple chatbot interactions toward a **context-aware medical knowledge assistant**.

---

### 💬 Collaborative Clinical Case Discussion

DoctorAI provides a case-based discussion workflow where users can create and join discussion rooms.

Each case can contain:

* Case ID
* Case description
* Creator
* Participants
* AI assistant
* Messages
* Timestamps

The application can maintain multiple participants within a case discussion and store the conversation history for that case.

Example workflow:

```text
Medical Case
     ↓
AI Image Analysis
     ↓
Generated Findings
     ↓
Case Discussion Room
     ↓
Doctor / User Questions
     ↓
AI-Assisted Discussion
```

---

### 📚 Medical Research Context

The analysis workflow is also designed to provide research context around identified findings, including:

* Relevant medical literature
* Standard treatment protocols
* Recent technological developments
* Supporting references

The project includes dedicated prompting for literature-oriented medical research.

---

### 🗂️ Persistent Analysis Context

Previously generated analyses can be stored and reused by the report-QA system.

Stored information can include:

* Analysis
* Findings
* Image filename
* Date
* Analysis ID
* Related contextual information

This enables users to ask questions about previous analyses rather than starting from zero every time.

---

## 🏗️ System Architecture

```text
                         ┌──────────────────────┐
                         │      User / Doctor   │
                         └──────────┬───────────┘
                                    │
                                    ▼
                         ┌──────────────────────┐
                         │  Streamlit Interface │
                         └──────────┬───────────┘
                                    │
                     ┌──────────────┼──────────────┐
                     │              │              │
                     ▼              ▼              ▼
              Medical Image    Report Q&A     Case Discussion
                     │              │              │
                     ▼              ▼              ▼
              Image Analysis   Embeddings      Chat Store
                     │              │              │
                     ▼              ▼              │
               AI Findings    Similarity Search   │
                     │              │              │
                     └──────────────┼──────────────┘
                                    ▼
                           ┌──────────────────┐
                           │  OpenAI LLM APIs │
                           └────────┬─────────┘
                                    │
                                    ▼
                         ┌────────────────────┐
                         │ Contextual Medical │
                         │      Response      │
                         └────────────────────┘
```

---

## 🔄 End-to-End Workflow

### 1. Medical Image Upload

The user provides a medical image such as an X-ray, MRI, CT, or ultrasound image.

### 2. Image Analysis

The AI analyzes the image according to a structured medical-imaging prompt.

The analysis is organized into:

1. Image Type & Region
2. Key Findings
3. Diagnostic Assessment
4. Patient-Friendly Explanation
5. Research Context

This structured approach is defined in the project's prompt architecture.

### 3. Analysis Storage

The generated analysis and associated findings can be stored for future retrieval.

### 4. Report Question Answering

A user can ask a question about previous analyses.

DoctorAI:

```text
Question
   ↓
Generate Query Embedding
   ↓
Compare Against Stored Analyses
   ↓
Select Top Relevant Contexts
   ↓
Construct Medical Context
   ↓
LLM Response
```

The implementation currently retrieves the top relevant contexts using cosine similarity.

### 5. Collaborative Case Discussion

Users can create a case discussion room and communicate around the case with the AI assistant and other participants.

---

## 🧩 Project Structure

```text
DOCTORAI/
│
├── app.py
│   └── Main Streamlit application
│
├── chat_system.py
│   └── Case discussion and collaborative chat functionality
│
├── prompts.py
│   └── Medical image analysis and research prompts
│
├── qa_interface.py
│   └── Question-answering interface
│
├── report_qa_chat.py
│   └── Report Q&A, embeddings, semantic retrieval,
│       conversation history and QA chat rooms
│
├── utils_simple.py
│   └── Utility and supporting functionality
│
├── requirements.txt
│   └── Python dependencies
│
└── README.md
    └── Project documentation
```

The repository currently contains these core Python modules and the dependency specification shown above.

---

## 🛠️ Technology Stack

### Programming Language

* Python

### AI / Generative AI

* OpenAI API
* Large Language Models
* Prompt Engineering
* Multimodal AI workflows
* Embeddings
* Retrieval-Augmented Question Answering

### Machine Learning / NLP

* NumPy
* Scikit-learn
* Cosine Similarity
* Text Embeddings

### Medical Data & Imaging

* Pillow
* PyDICOM
* BioPython

### Application Layer

* Streamlit
* FastAPI
* Uvicorn
* Pydantic
* Python Multipart

The repository's current `requirements.txt` includes FastAPI, Uvicorn, Pydantic, Pillow, OpenAI, Streamlit, BioPython, PyDICOM, and related dependencies.

---

## 🔐 API Configuration

DoctorAI requires an OpenAI API key for its AI-powered functionality.

Create an environment variable:

```bash
OPENAI_API_KEY=your_api_key_here
```

Or configure the API key through the application's interface where supported.

### ⚠️ Security

Never commit API keys directly into GitHub.

Use:

```text
.env
```

and add it to `.gitignore`.

---

## 🚀 Installation

### 1. Clone the Repository

```bash
git clone https://github.com/harshsingh-prog/DOCTORAI.git
cd DOCTORAI
```

### 2. Create a Virtual Environment

Windows:

```bash
python -m venv venv
venv\Scripts\activate
```

Linux / macOS:

```bash
python3 -m venv venv
source venv/bin/activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

---

## ▶️ Running the Application

Run the Streamlit application:

```bash
streamlit run app.py
```

The application will start locally and provide a browser-based interface.

---

## 🧠 Retrieval-Augmented Report Q&A

One of the important components of DoctorAI is its semantic retrieval pipeline.

Instead of sending every historical analysis to the language model, the system attempts to identify the most relevant stored analyses.

For each stored analysis:

```text
Medical Analysis
      ↓
Embedding Generation
      ↓
Vector Representation
```

For a new question:

```text
User Question
      ↓
Query Embedding
      ↓
Cosine Similarity
      ↓
Top-K Relevant Analyses
      ↓
LLM Context
      ↓
Answer
```

The current implementation retrieves the top three relevant contexts by default.

---

## 💬 Conversation Memory

DoctorAI maintains conversation history for report-based Q&A.

The system keeps a bounded recent conversation history so that follow-up questions can remain contextual while preventing the conversation context from growing indefinitely.

---

## 🩻 Supported Medical Imaging Concepts

The analysis prompt is designed to work with common medical imaging modalities, including:

* X-Ray
* MRI
* CT
* Ultrasound
* Other medical imaging formats

The system also includes fallback handling when an uploaded image is unclear, unsupported, or insufficient for reliable analysis.

---

## 🛡️ Responsible AI & Medical Safety

DoctorAI is intended as an **AI-assisted medical information and decision-support prototype**.

It should **not** be used as a substitute for:

* A qualified physician
* A radiologist
* A clinical diagnosis
* Professional medical advice
* Emergency medical care

AI-generated findings can be incorrect or incomplete.

All medical-image interpretations and AI-generated recommendations should be independently reviewed by qualified healthcare professionals before being used for clinical decisions.

---

## 🎯 Project Goals

DoctorAI aims to explore how Generative AI can support healthcare workflows by combining:

* Medical image understanding
* LLM-based reasoning
* Semantic retrieval
* Clinical report Q&A
* Persistent medical context
* Collaborative case discussion
* Medical research assistance

The broader goal is to create an AI-assisted workflow where users can **analyze → understand → retrieve → question → discuss** medical information within one system.

---

## 🔮 Future Improvements

Potential extensions include:

* Dedicated multimodal medical vision models
* DICOM metadata extraction
* Medical knowledge graphs
* Vector database integration
* Structured clinical data integration
* Fine-tuned medical LLMs
* Explainable AI outputs
* Confidence calibration
* Physician-in-the-loop validation
* Clinical evaluation on benchmark datasets
* Role-based authentication
* Secure cloud deployment
* HIPAA/GDPR-oriented privacy architecture
* Audit logging
* Model evaluation and monitoring
* Production-grade API architecture

---

## 📊 Current Architecture vs. Production Architecture

The current project uses local JSON-based storage for components such as chat and analysis stores.

For production deployment, the architecture can be extended to:

```text
                ┌────────────────────┐
                │    Web / Mobile UI │
                └─────────┬──────────┘
                          │
                          ▼
                ┌────────────────────┐
                │     API Gateway    │
                └─────────┬──────────┘
                          │
             ┌────────────┼────────────┐
             ▼            ▼            ▼
        Image Service  RAG Service  Chat Service
             │            │            │
             ▼            ▼            ▼
        Vision Model   Vector DB    PostgreSQL
             │            │            │
             └────────────┼────────────┘
                          ▼
                  ┌───────────────┐
                  │   LLM Layer   │
                  └───────┬───────┘
                          ▼
                 ┌─────────────────┐
                 │ AI Response/API │
                 └─────────────────┘
```

---

## 🌟 Why DoctorAI?

DoctorAI goes beyond a basic medical chatbot.

It combines multiple AI capabilities into a single workflow:

```text
             DoctorAI
                │
     ┌──────────┼──────────┐
     │          │          │
     ▼          ▼          ▼
 Multimodal   RAG /      Clinical
   AI         Retrieval   Chat
     │          │          │
     └──────────┼──────────┘
                ▼
        Contextual Medical
             Assistant
```

This makes the project a practical exploration of **multimodal Generative AI + RAG + healthcare workflow automation**.

---

## 📌 Project Highlights

* 🧠 Generative AI-powered medical assistant
* 🩻 Medical image analysis workflow
* 🔎 Semantic retrieval for medical reports
* 📚 Research-context generation
* 💬 Collaborative case discussion
* 🗂️ Persistent analysis storage
* 🔗 Context-aware report Q&A
* 🖥️ Streamlit-based interface
* ⚡ FastAPI/Uvicorn backend dependencies
* 🔐 API-key-based LLM integration
* 🧩 Modular Python architecture

---

## 👨‍💻 Author

**Harsh Singh**

AI/ML • Generative AI • Agentic AI • RAG • Deep Learning

GitHub:
https://github.com/harshsingh-prog

---

## ⚠️ Disclaimer

This project is intended for **research, educational, and AI-assistance purposes**.

It does not provide a certified medical diagnosis and should not be used as a replacement for professional medical evaluation.

For any medical concern, consult an appropriately qualified healthcare professional.

---

## ⭐ If You Find This Project Useful

If this project is useful for your research or experimentation:

⭐ Star the repository
🍴 Fork the project
🐛 Open an issue
💡 Suggest improvements
🤝 Contribute to the project

---

## 📄 License

See the repository for the applicable license and project terms.



