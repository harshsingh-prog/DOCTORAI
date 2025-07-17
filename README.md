🧠 DoctorAI – Intelligent Medical Image Analysis & AI-Powered Consultation
DoctorAI is a smart, AI-powered medical assistant built with Streamlit and FastAPI that allows users to upload medical images (e.g., X-rays, CT scans, MRIs) and receive advanced AI-based diagnostic analysis and consultation support. It combines powerful image processing, LLM-driven chat support, and a responsive interface to assist doctors and patients alike.

🚀 Features
🔬 AI Medical Image Analysis
Upload medical images in formats like JPG, PNG, or even DICOM (via pydicom) for intelligent insights powered by deep learning and bioinformatics tools.

💬 Doctor Chat System
Integrated LLM-based prompt system that allows users to interact with an AI-powered doctor for preliminary consultations and symptom discussions.

🧠 Bioinformatics & DICOM Support
Built-in support for Biopython and pydicom to interpret medical metadata and advanced imaging standards.

🧾 Doctor Prompt Templates
Predefined and dynamic prompts for different medical specialties (e.g., radiology, general medicine, cardiology) via a modular utils and prompts system.

⚡ FastAPI Backend
Efficient and scalable backend to handle image uploads, run diagnostics, and serve results via REST API endpoints.

🎨 Streamlit Frontend
User-friendly interface for patients and healthcare professionals to interact with the AI tools and visualization modules.

🛠️ Tech Stack
🔗 Backend
FastAPI==0.105.0 — high-performance API framework

uvicorn==0.24.0 — ASGI server for FastAPI

pydantic==2.5.2 — data validation

openai==1.3.0 — LLM-based medical chat responses

python-multipart==0.0.6 — file upload handling

Pillow==10.1.0 — image processing

requests==2.31.0 — API requests

🖼️ Image & Bio Data
biopython — for bioinformatics operations

pydicom — handling DICOM medical image formats

💻 Frontend
streamlit==1.29.0 — interactive UI and user input handling

📂 Project Structure
graphql
Copy
Edit
📁 DoctorAI/
├── app.py                 # Main Streamlit frontend
├── main.py                # FastAPI backend entry point
├── utils_simple.py        # Utility functions (image handling, OpenAI API, etc.)
├── prompts/               # LLM prompt templates for various specialties
├── static/                # Assets like sample images or logo
└── requirements.txt       # All dependencies
📸 Sample Use Case
Upload an X-ray or DICOM scan.

Choose analysis type (general, radiology, etc.).

Get instant AI-generated diagnostic feedback.

Chat with the built-in doctor assistant for next steps.

🔒 Disclaimer
This app is for educational and research purposes only. It is not a substitute for professional medical advice, diagnosis, or treatment. Always consult a qualified healthcare provider.

🤝 Contributions
Contributions, ideas, and improvements are welcome! Please feel free to open issues or submit pull requests.

