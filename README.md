MediMind: RAG-Powered Medical Chatbot
MediMind is a state-of-the-art medical information assistant built using Retrieval-Augmented Generation (RAG). It processes medical PDF documents, stores them in a vector database, and uses a Large Language Model (LLM) to provide context-aware, accurate answers to clinical queries.

🚀 Features
PDF Knowledge Integration: Extracts and chunks data from complex medical textbooks/manuals.

Semantic Search: Uses Hugging Face embeddings to understand the meaning behind medical queries.

Vector Storage: Powered by Pinecone for high-performance similarity searches.

Premium UI: A clean, clinical, and responsive chat interface.

Open-Source LLM Support: Integrated with OpenRouter to access models like Gemini 2.0 or Llama 3.

🛠️ Tech Stack
Framework: Flask

Orchestration: LangChain (LCEL)

Embeddings: sentence-transformers/all-MiniLM-L6-v2

LLM: Google Gemini 2.0 (via OpenRouter)

Vector DB: Pinecone

Frontend: HTML5, CSS3 (Glassmorphism), JavaScript

📋 Installation & Setup
1. Clone the Repository
Bash
git clone https://github.com/yourusername/medical-chatbot.git
cd medical-chatbot
2. Create a Virtual Environment
Bash
python -m venv .venv
source .venv/bin/activate  # On Windows: .venv\Scripts\activate
3. Install Dependencies
Bash
pip install -r requirements.txt
4. Configure Environment Variables
Create a .env file in the root directory and add your credentials:

Code snippet
PINECONE_API_KEY="your_pinecone_key"
OPENROUTER_API_KEY="your_openrouter_key"
🏃 Running the Project
Phase 1: Data Ingestion
Place your medical PDFs in the data/ folder, then run the indexing script to populate the Pinecone database:

Bash
python store_index.py
Phase 2: Launch the Chatbot
Start the Flask application:

Bash
python app.py
Visit http://localhost:8080 in your browser.

🧠 How it Works
Ingestion: PDFs are loaded and split into 500-character chunks with a 20-character overlap to preserve context.

Vectorization: Each chunk is converted into a 384-dimensional vector using Hugging Face.

Retrieval: When a user asks a question, the system finds the top 3 most relevant chunks in Pinecone.

Generation: The LLM receives the chunks + the user question and generates a professional medical response.

⚠️ Disclaimer
This project is for educational purposes only. The AI assistant is designed to provide information based on retrieved documents and is not a substitute for professional medical advice, diagnosis, or treatment.

🤝 Contributing
Feel free to fork this project and submit pull requests. For major changes, please open an issue first to discuss what you would like to change.
