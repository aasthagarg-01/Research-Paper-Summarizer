# AI-Powered Research Paper Summarizer

> An NLP-powered application that automatically summarizes long scientific research papers using a hybrid Extractive–Abstractive pipeline. The system supports PDF uploads and arXiv integration, extracts scientific keywords and entities, generates methodology flowcharts, and provides an interactive interface for efficient literature review.

![Python](https://img.shields.io/badge/Python-3.10+-blue?style=flat-square&logo=python)
![PyTorch](https://img.shields.io/badge/PyTorch-Deep%20Learning-ee4c2c?style=flat-square&logo=pytorch)
![Streamlit](https://img.shields.io/badge/Streamlit-Web%20Application-ff4b4b?style=flat-square&logo=streamlit)
![Transformers](https://img.shields.io/badge/HuggingFace-Transformers-yellow?style=flat-square)
![Docker](https://img.shields.io/badge/Docker-Supported-2496ED?style=flat-square&logo=docker)
![NLP](https://img.shields.io/badge/Domain-Natural%20Language%20Processing-success?style=flat-square)

---

# Overview

Scientific research papers contain valuable knowledge but are often lengthy, highly technical, and time-consuming to understand. Researchers and students spend a significant amount of time reading multiple papers before identifying the most relevant information.

This project presents an AI-powered research paper summarization system that automatically extracts and summarizes important information from scientific publications using modern Natural Language Processing (NLP) techniques.

The system combines semantic extractive summarization with transformer-based abstractive summarization to generate concise, coherent, and context-aware summaries while preserving the technical meaning of the original paper.

In addition to summarization, the application extracts scientific keywords, identifies important entities such as models and datasets, and generates methodology flowcharts to improve comprehension of research workflows.

The application provides a simple Streamlit-based interface where users can upload research papers in PDF format or retrieve papers directly from arXiv.

---

# Key Features

- Automatic research paper summarization
- Upload research papers in PDF format
- Search and retrieve papers directly from arXiv
- Hybrid Extractive + Abstractive summarization pipeline
- Long document processing using LED Transformer
- Scientific keyword extraction using KeyBERT and SciBERT
- Scientific entity extraction
- Section-wise summarization
- Automatic methodology flowchart generation
- Interactive Streamlit web application
- Export generated summaries
- Docker support for deployment

---

# System Architecture

```mermaid
flowchart LR

A[PDF Upload / arXiv Search]

A --> B[PyMuPDF]

B --> C[Text Extraction]

C --> D[Section Detection]

D --> E[Sentence Embeddings]

E --> F[Extractive Ranking]

F --> G[LED Transformer]

G --> H[Abstractive Summary]

C --> I[KeyBERT + SciBERT]

I --> J[Scientific Keywords]

C --> K[Regex Entity Detection]

K --> L[Scientific Entities]

C --> M[Methodology Parser]

M --> N[Mermaid Flowchart]

H --> O[Streamlit Dashboard]

J --> O

L --> O

N --> O

O --> P[Final Output]
```

---

# Processing Pipeline

```
Research Paper
       │
       ▼
PDF Extraction
       │
       ▼
Text Cleaning
       │
       ▼
Section Detection
       │
       ▼
Sentence Embedding Generation
       │
       ▼
Extractive Sentence Ranking
       │
       ▼
LED Abstractive Summarization
       │
       ▼
Keyword Extraction
       │
       ▼
Entity Recognition
       │
       ▼
Methodology Flowchart
       │
       ▼
Interactive Streamlit Interface
```

---

# Technology Stack

| Category | Technology |
|-----------|------------|
| Programming Language | Python |
| Frontend | Streamlit |
| Deep Learning Framework | PyTorch |
| NLP Framework | Hugging Face Transformers |
| Abstractive Summarization | LED (Longformer Encoder Decoder) |
| Extractive Summarization | Sentence Transformers |
| Keyword Extraction | KeyBERT |
| Scientific Embeddings | SciBERT |
| PDF Processing | PyMuPDF |
| Data Source | arXiv API |
| Deployment | Docker |
| Version Control | Git & GitHub |

---

# Project Structure

```text
Research-Paper-Summarizer
│
├── data/
├── models/
├── notebooks/
├── references/
├── reports/
├── scripts/
├── src/
│   ├── backend/
│   └── frontend/
│
├── README.md
├── docker-compose.yaml
├── .gitignore
└── ResearchPaperSummarizer.ipynb
```

# Workflow

The application follows a hybrid NLP pipeline to generate structured summaries from long scientific research papers.

1. **Paper Acquisition**
   - Upload a research paper in PDF format.
   - Or fetch papers directly from the arXiv API.

2. **PDF Processing**
   - Extract text using PyMuPDF.
   - Remove unnecessary whitespace and formatting.
   - Divide the paper into logical sections.

3. **Extractive Summarization**
   - Generate sentence embeddings using Sentence Transformers.
   - Rank sentences based on semantic similarity.
   - Select the most informative sentences.

4. **Abstractive Summarization**
   - Feed extracted content into the LED (Longformer Encoder-Decoder) model.
   - Generate a coherent summary while preserving context.

5. **Keyword & Entity Extraction**
   - Extract scientific keywords using KeyBERT with SciBERT embeddings.
   - Detect models, datasets, metrics and algorithms using rule-based entity recognition.

6. **Methodology Visualization**
   - Parse procedural text.
   - Automatically generate Mermaid-based methodology flowcharts.

7. **Result Generation**
   - Display summaries, keywords, entities and flowcharts through the Streamlit interface.

---

# Models & Algorithms

| Model / Library | Purpose |
|-----------------|---------|
| **LED (Longformer Encoder-Decoder)** | Generates coherent abstractive summaries for long research papers. |
| **Sentence Transformers** | Creates semantic embeddings for extractive sentence ranking. |
| **KeyBERT + SciBERT** | Extracts domain-specific scientific keywords and concepts. |
| **PyMuPDF** | Extracts and preprocesses text from PDF research papers. |
| **Regex-based Entity Extraction** | Identifies scientific entities such as models, datasets, algorithms, and evaluation metrics. |
| **Mermaid** | Generates methodology flowcharts from extracted procedural text. |

# Why a Hybrid Summarization Pipeline?

Instead of relying on a single summarization technique, this project combines extractive and abstractive approaches.

| Extractive Summarization | Abstractive Summarization |
|--------------------------|---------------------------|
| Selects important sentences | Generates new coherent sentences |
| Preserves factual accuracy | Produces fluent summaries |
| Helps retain important details | Improves readability |

The hybrid approach leverages the strengths of both techniques, resulting in summaries that are both informative and easy to understand.

---

# Installation

Clone the repository

```bash
git clone https://github.com/<your-username>/Research-Paper-Summarizer.git

cd Research-Paper-Summarizer
```

---

Create a virtual environment

```bash
python -m venv venv
```

Activate the environment

### Windows

```bash
venv\Scripts\activate
```

### Linux / macOS

```bash
source venv/bin/activate
```

---

Install backend dependencies

```bash
pip install -r src/backend/requirements_backend.txt
```

Install frontend dependencies

```bash
pip install -r src/frontend/requirements_frontend.txt
```

---

# Running the Project

Start the backend

```bash
cd src/backend

python main.py
```

Open another terminal and start the frontend

```bash
cd src/frontend

streamlit run app.py
```

Once both services are running, open the Streamlit URL displayed in the terminal.

---

# Docker Deployment

To run the application using Docker:

```bash
docker-compose up --build
```

This automatically builds the required containers and launches both the backend and frontend.

---

# Usage

1. Launch the application.
2. Upload a research paper in PDF format or search for one using the arXiv integration.
3. The application processes the document.
4. View:
   - Generated summary
   - Scientific keywords
   - Extracted entities
   - Methodology flowchart
5. Export the generated results.

---

# Input

The application accepts:

- Research papers in PDF format
- Papers retrieved using the arXiv API

---

# Output

The generated output includes:

- Abstractive summary
- Extractive summary
- Scientific keywords
- Named entities
- Section-wise summaries
- Methodology flowchart
- Interactive visualization through Streamlit

---

# Experimental Results

The proposed hybrid summarization pipeline was evaluated on multiple scientific research papers obtained through both PDF uploads and the arXiv API.

The generated summaries consistently captured the primary research objective, methodology, and experimental findings while significantly reducing the amount of text required for manual reading.

---

# BERTScore Evaluation

The generated summaries were evaluated using **BERTScore**, which measures semantic similarity between generated summaries and reference summaries.

| Metric | Score |
|---------|------:|
| Precision | **0.8438** |
| Recall | **0.8761** |
| F1 Score | **0.8597** |

The evaluation indicates that the generated summaries retain most of the semantic information present in the original research papers while remaining concise and readable.

---

# Comparative Analysis

| Feature | Traditional Extractive Methods | Proposed Hybrid System |
|----------|-------------------------------|------------------------|
| Context Awareness | Low | High |
| Readability | Moderate | High |
| Long Document Support | Limited | Excellent |
| Scientific Terminology | Partial | Comprehensive |
| Keyword Extraction | Basic | Context-aware |
| Section-wise Summaries | No | Yes |
| Methodology Visualization | No | Yes |
| Overall Summary Quality | Moderate | High |

---

# Current Limitations

Although the application performs well on long scientific documents, a few limitations remain.

- Mathematical equations are not summarized.
- Tables and figures embedded in PDFs are ignored.
- Scientific diagrams are not interpreted.
- Performance depends on the quality of extracted PDF text.
- Keyword extraction may occasionally include generic scientific terms.

---

# Future Improvements

- Fine-tune transformer models on scientific datasets.
- Support multimodal summarization of text, figures, and equations.
- Integrate OCR for scanned research papers.
- Enable multi-document and citation-aware summarization.
- Add ROUGE and BLEU based evaluation.

---

## References

This project builds upon the following open-source models, libraries, and research papers:

1. **Longformer: The Long-Document Transformer** — Beltagy, Peters & Cohan (2020)
2. **SciBERT: A Pretrained Language Model for Scientific Text** — Beltagy, Lo & Cohan (2019)
3. **KeyBERT** — Minimal Keyword Extraction with BERT Embeddings
4. **Hugging Face Transformers**
5. **Sentence Transformers**

---

# Authors

**Aastha Garg**

Computer Engineering Undergraduate  
Thapar Institute of Engineering & Technology
GitHub: https://github.com/aasthagarg-01

**Vaibhavi Jain**

Computer Engineering Undergraduate  
Thapar Institute of Engineering & Technology

---

# License

This project is intended for educational and research purposes.

Feel free to fork, modify, and extend the project while providing appropriate attribution.

---

## If you found this project useful, consider giving it a ⭐ on GitHub.
