# Task-1
Here is a detailed **README.md** file for Task 1 to post on GitHub.

---

# **Chat with PDF using RAG Pipeline**

This project implements a **Retrieval-Augmented Generation (RAG) pipeline** that allows users to interact with **semi-structured PDF files**. The system can extract text, chunk it into smaller pieces, generate embeddings, and store them for efficient retrieval. When a user asks a question, the system retrieves relevant chunks and generates a detailed, accurate response using a **Large Language Model (LLM)**.

---

## **Features**
- **Text Extraction**: Extracts text and relevant structured information from PDF files.
- **Text Chunking**: Splits large text into smaller logical chunks for improved retrieval.
- **Embedding Generation**: Converts text chunks into vector embeddings using the OpenAI Embedding API.
- **Vector Database**: Stores embeddings using FAISS for similarity-based search.
- **Query Handling**: Retrieves relevant chunks and generates responses using an OpenAI-powered LLM (e.g., GPT-3.5 Turbo).
- **Accurate Responses**: Ensures factuality by including exact retrieved values in the response.

---

## **Requirements**
Before running the project, ensure you have the following:
1. **Python 3.8+**
2. **OpenAI API Key** (for embeddings and LLM responses)

### **Install Required Libraries**
Run the following command to install all necessary libraries:
```bash
pip install langchain faiss-cpu pypdf2 openai tiktoken
```

---

## **File Structure**
```
chat-with-pdf-rag/
│
├── pdfs/                       # Folder to store your PDF files
├── main.py                     # Main script to run the RAG pipeline
├── README.md                   # Project documentation
```

---

## **How to Run the Project**

### 1. **Prepare the Environment**
- Create a folder named **`pdfs`** in the project directory.
- Place your PDF files inside the `pdfs` folder.

### 2. **Set Up OpenAI API Key**
- Get an API key from [OpenAI](https://platform.openai.com/signup).
- Add your API key in the script where indicated.

### 3. **Run the Script**
Run the following command in your terminal:
```bash
python main.py
```

---

## **Usage**
1. **Load and Process PDFs**: 
   The script loads PDFs from the `pdfs/` folder, extracts text, and creates embeddings for efficient retrieval.

2. **Ask Questions**:
   Enter your question as input. Example questions:
   - "What is the unemployment information based on degree type on page 2?"
   - "What data is available in the table on page 6?"

3. **Get Answers**:
   The system will retrieve relevant chunks and generate a precise response.

---

## **Example Output**
**Input**:  
> "What is the unemployment information based on degree type on page 2?"

**Output**:  
> "The unemployment rate for individuals with a Bachelor's degree is 3.5%. Those with only a high school diploma have an unemployment rate of 6.2%."

---

## **Code Overview**

### **Key Components**
- **PDF Text Extraction**: Uses `PyPDF2` to read and extract text from PDFs.
- **Chunking**: Text is divided into chunks of 500 characters with a 50-character overlap using `LangChain`'s `RecursiveCharacterTextSplitter`.
- **Embeddings**: Chunks are embedded using the OpenAI API (`text-embedding-ada-002`).
- **Vector Store**: Stores embeddings in **FAISS** for fast similarity-based retrieval.
- **LLM Query**: Retrieves relevant chunks and generates responses using the `gpt-3.5-turbo` model.

### **Core Functions**
- **`pdf_rag_pipeline`**: The main pipeline to load PDFs, split text, and generate embeddings.
- **`query_pdf(question)`**: Allows users to input questions and get detailed answers.

---

## **Dependencies**
- [LangChain](https://python.langchain.com/)
- [FAISS](https://github.com/facebookresearch/faiss)
- [PyPDF2](https://pypi.org/project/PyPDF2/)
- [OpenAI API](https://platform.openai.com/docs/)
- [Tiktoken](https://pypi.org/project/tiktoken/)

---

## **Limitations**
- Requires an **OpenAI API key**, which may incur costs.
- The performance of the LLM and embedding model depends on the input size and token limits.

---

## **Future Improvements**
- Add support for multiple embedding models (e.g., HuggingFace Transformers).
- Enhance the chunking process for better semantic understanding.
- Integrate a web interface to allow users to upload PDFs and ask questions interactively.

---

## **Contributing**
Contributions are welcome! If you have suggestions or improvements, please create a pull request.

---

## **License**
This project is licensed under the **MIT License**. See the `LICENSE` file for details.

---

## **Contact**
For any questions or feedback, please contact:
- **Name**: Viswanath Reddy Gangula  
- **Email**: viswanath@example.com  

---

### **Enjoy using the Chat with PDF RAG Pipeline!** 🚀
