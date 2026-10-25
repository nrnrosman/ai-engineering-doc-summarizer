# ai-engineering-doc-summarizer
AI-powered application designed to help students and beginners understand lengthy or complex documents more easily. The system uses Natural Language Processing (NLP) and a pretrained language model to analyze uploaded documents and generate concise, easy-to-understand summaries.

## Problem Statement

University students and beginners often need to read lengthy academic papers, educational materials, and technical documents to understand new topics. Complex terminology and large amounts of information can make it difficult and time-consuming to identify the main ideas and important findings. AI-based text summarization can help address this problem by using Natural Language Processing (NLP) and pretrained language models to generate shorter summaries while preserving important information. However, generated summaries must be evaluated to ensure that they remain accurate, readable, and faithful to the original documents.

## Evidence of the Problem

**Document summarization as an information-processing task:** Hugging Face describes summarization as producing a shorter version of a document while preserving its important information. This supports the use of automated summarization to condense lengthy content.  
  Source: https://huggingface.co/docs/transformers/main/tasks/summarization

**Existing research on automated summarization:** Zhang et al. (2020) introduced PEGASUS, a pretrained language model approach designed for abstractive summarization. Their research demonstrates the use of pretrained models to generate summaries across different types of documents.  
  Source: https://arxiv.org/abs/1912.08777

## Initial Related Work / Existing Approaches

**1. BART — Denoising Sequence-to-Sequence Pre-training for Natural Language Generation, Translation, and Comprehension (Lewis et al., 2019)**  
  Source: https://arxiv.org/abs/1910.13461  
  Key approach: BART is a pretrained sequence-to-sequence model that can be fine-tuned for text summarization and other language generation tasks.  
  Key limitation: A general summarization model does not automatically ensure that its output is easy for beginners to understand. The summaries may still contain technical terminology or omit important details.

**2. PEGASUS: Pre-training with Extracted Gap-sentences for Abstractive Summarization (Zhang et al., 2020)**  
  Source: https://arxiv.org/abs/1912.08777  
  Key approach: PEGASUS uses a pretraining objective in which important sentences are removed from a document and the model learns to generate them. The authors evaluate the approach on multiple summarization tasks.  
  Key limitation: The research focuses on summarization model performance rather than providing a complete beginner-friendly application with adjustable summary lengths and simplified explanations.

**3. Hugging Face Transformers — Summarization**  
  Source: https://huggingface.co/docs/transformers/main/tasks/summarization  
  Key approach: The documentation provides instructions for using and fine-tuning pretrained summarization models, including T5, and describes evaluation using ROUGE.  
  Key limitation: Using a pretrained model alone does not provide a complete document-upload interface or guarantee that generated summaries are readable, factually accurate, and suitable for beginners.

## Project Objectives

- **O1:** To develop a web-based application that extracts text from uploaded PDF documents and generates concise summaries using a pretrained NLP model.
- **O2:** To simplify complex information and present important ideas in a beginner-friendly format.
- **O3:** To evaluate the generated summaries based on quality, readability, factual accuracy, and coverage of important information.

## Target Users

The target users are university students and beginners who need help understanding lengthy or complex documents. The system is intended for users who want to identify key information from academic research papers, educational materials, and technical reports without reading every detail initially.

## Data Sources

**Source 1: Attention Is All You Need (Vaswani et al., 2017)** — Introduces the Transformer architecture used in modern NLP models.  
  URL: https://arxiv.org/abs/1706.03762

**Source 2: BART: Denoising Sequence-to-Sequence Pre-training for Natural Language Generation, Translation, and Comprehension (Lewis et al., 2019)** — Describes a pretrained sequence-to-sequence model applicable to summarization.  
  URL: https://arxiv.org/abs/1910.13461

**Source 3: PEGASUS: Pre-training with Extracted Gap-sentences for Abstractive Summarization (Zhang et al., 2020)** — Presents a pretrained model and approach for abstractive text summarization.  
  URL: https://arxiv.org/abs/1912.08777


## Weekly Progress

| Week | Focus | Deliverable | Status |
|---|---|---|---|
| W1 | System map and project scope | README and initial repository structure | ✅ Completed |
| W2 | Data collection and document processing | Selected public PDFs and text extraction prototype | Planned |
| W3 | Pretrained model integration | Initial summarization implementation | Planned |
| W4 | Application development | Basic document upload and summary interface | Planned |
| W5 | Beginner-friendly summarization | Simplified explanations and key-point extraction | Planned |
| W6 | System testing and evaluation | Test dataset and initial evaluation results | Planned |
| W7 | Improvement and documentation | Improved summarization quality and technical documentation | Planned |
| W8 | Final testing and presentation | Completed prototype and project demonstration | Planned |

---

**Technologies:** Python, Streamlit, Hugging Face Transformers, PyMuPDF, and ROUGE.

**Project scope:** The initial version will focus on text-based PDF documents and pretrained summarization models. Scanned PDFs and complex document layouts may be excluded from the first implementation. The system is intended for educational purposes and will not replace careful reading of the original documents.

