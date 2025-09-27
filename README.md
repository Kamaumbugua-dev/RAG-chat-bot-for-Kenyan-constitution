RAG chatbot Constitution of Kenya 2010 Q&A System

A Retrieval-Augmented Generation (RAG) system that provides accurate, context-based answers strictly from the Constitution of Kenya 2010 document.
 Overview

This project implements a sophisticated Q&A interface that allows users to ask questions about the Constitution of Kenya 2010 and receive precise answers grounded entirely in the constitutional text. The system uses advanced natural language processing to retrieve relevant sections and generate accurate responses.
 Features

     Document-Based Accuracy: 100% of answers come directly from the Constitution text

     RAG Architecture: Combines vector search with LLM for precise responses

     User-Friendly GUI: Clean, intuitive interface built with ipywidgets

     Scrollable Answers: Handles lengthy responses with automatic scrolling

     Secure API Handling: Environment variable-based API key management

     Fast Retrieval: ChromaDB vector database for efficient searching

 Technical Stack

    Backend: Python, LangChain, ChromaDB

    Embeddings: SentenceTransformer (all-MiniLM-L6-v2)

    LLM: Groq API (Llama-3.3-70b-versatile)

    Frontend: ipywidgets, Jupyter Notebook

    PDF Processing: pdfminer.six

    Environment Management: python-dotenv

 Installation
Prerequisites

    Python 3.8+

    Jupyter Notebook/JupyterLab

    Groq API account (Get API key here)

Step 1: Clone the Repository
bash

git clone https://github.com/yourusername/constitution-kenya-qa.git
cd constitution-kenya-qa

Step 2: Install Dependencies
bash

pip install -r requirements.txt

If requirements.txt is not available, install manually:
bash

pip install ipywidgets langchain chromadb sentence-transformers pdfminer.six python-dotenv requests

Step 3: Set Up Environment Variables

Create a .env file in the project root:
bash

# .env
GROQ_API_KEY=your_groq_api_key_here

Step 4: Add Constitution PDF

Place The_Constitution_of_Kenya_2010.pdf in the project root directory.
 Usage
Running the Application

    Start Jupyter Notebook:

bash

jupyter notebook

    Open constitution_qa_gui.ipynb

    Run all cells in sequence

    The GUI will appear with:

        Welcome message and instructions

        Question input text area

        "Get Answer" and "Clear" buttons

        Scrollable answer display area

Asking Questions

Enter questions in natural language, such as:

    "What are the fundamental rights guaranteed by the Constitution?"

    "How is devolution implemented under the Constitution?"

    "What does Article 43 say about healthcare?"

    "Explain the Bill of Rights and its enforcement mechanisms"

 System Architecture
text

User Question → Vector Search → Context Retrieval → LLM Processing → Formatted Answer
                     ↓
              Constitution Text (PDF)
                     ↓
             ChromaDB Vector Store
                     ↓
           SentenceTransformer Embeddings

Key Components

    Document Processing: PDF text extraction and chunking

    Vector Database: ChromaDB with semantic search capabilities

    Retrieval System: LangChain retriever with similarity search

    Generation System: Groq LLM with strict RAG prompting

    User Interface: Interactive ipywidgets-based GUI

 Configuration
Environment Variables

    GROQ_API_KEY: Your Groq API key (required)

Model Settings

    Embedding Model: all-MiniLM-L6-v2

    LLM Model: llama-3.3-70b-versatile

    Temperature: 0.1 (for factual accuracy)

    Max Tokens: 600

Retrieval Parameters

    Chunk Size: 500 characters

    Chunk Overlap: 50 characters

    Retrieval Count: 5 most relevant chunks
    
    
 Project Structure


     constitution-kenya-qa/
     ├── constitution_qa_gui.ipynb      # Main application notebook
     ├── The_Constitution_of_Kenya_2010.pdf  # Constitution document
     ├── constitution_of_kenya.txt      # Processed text file
     ├── .env                           # Environment variables (create)
     ├── chroma/                        # Vector database (auto-generated)
     ├── requirements.txt               # Python dependencies
     └── README.md                      # This file

 Features in Detail
Accurate RAG System

    Strict context-only responses

    No hallucinations or external knowledge

    Transparent about information limitations

    Cites specific constitutional articles

User Interface

    Clean, professional design

    Real-time processing feedback

    Scrollable answer display

    Responsive layout

Security & Privacy

    API keys stored in environment variables

    Local vector database

    No data sent to external services except Groq API

 Example Questions & Responses

Question: "What are the objects of devolution?"

Response: "According to Article 174 of the Constitution, the objects of devolution are: (a) to promote democratic and accountable exercise of power; (b) to foster national unity by recognising diversity; (c) to give powers of self-governance to the people..."

Question: "What rights are guaranteed to children?"

Response: "Based on the available constitutional text, I can provide the following information: Article 53 outlines the rights of children, including the right to a name and nationality from birth, free and compulsory basic education, basic nutrition, shelter, and healthcare..."
 Troubleshooting
Common Issues

    API Key Not Found

        Check .env file exists and contains GROQ_API_KEY=your_key

        Restart Jupyter kernel after creating .env

    PDF File Not Found

        Ensure The_Constitution_of_Kenya_2010.pdf is in the project root

        Check file name spelling

    Module Import Errors

        Install missing packages: pip install package_name

        Restart Jupyter kernel after installation

    Widgets Not Displaying

        Enable ipywidgets: jupyter nbextension enable --py widgetsnbextension

        Restart Jupyter notebook

Performance Tips

    First run may take longer to process the PDF

    Subsequent runs use cached vector database

    Questions with specific article references yield better results

 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.
Areas for Improvement

    Support for multiple document formats

    Enhanced citation tracking

    Batch question processing

    Export functionality for answers

    Multi-language support

 License

This project is for educational and research purposes. The Constitution of Kenya 2010 is a public document.
Acknowledgments

    Constitution of Kenya 2010 (Public Document)

    Groq for LLM API access

    LangChain community for RAG framework

    SentenceTransformers for embeddings

 Support

For issues and questions:

    Check the troubleshooting section above

    Open an issue on GitHub

    Ensure you've included error messages and system information

Note: This system is designed for educational and reference purposes. For legal advice, consult qualified legal professionals.
