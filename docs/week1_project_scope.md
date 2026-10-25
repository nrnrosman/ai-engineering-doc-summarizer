# Week 1: Project Scope

## 1. Project Title

**AI Document Summarizer for Beginners**

## 2. Project Overview

The AI Document Summarizer for Beginners is a web-based application
designed to help university students and beginners understand long or
complex documents more easily. Users can upload a text-based PDF, and
the system will extract its text and use a pretrained Natural Language
Processing (NLP) model to generate a concise summary and identify key
points.

The system aims to save reading time and make educational information
easier to understand.

## 3. Problem Statement

Students often need to read lengthy research papers, academic articles,
and technical documents. These documents may contain complex terminology
and large amounts of information, making it difficult for beginners to
identify the main ideas quickly.

An AI-powered summarization system can help by shortening the text while
retaining important information. However, the generated summaries must
still be checked for readability, relevance, and factual accuracy.

## 4. Project Objectives

-   **O1:** To develop a web-based application that extracts text from
    uploaded PDF documents and generates summaries using a pretrained
    NLP model.
-   **O2:** To present concise summaries and important key points in
    beginner-friendly language.
-   **O3:** To evaluate the generated summaries based on information
    coverage, readability, and factual accuracy.

## 5. Target Users

-   University students
-   Beginners reading academic papers
-   Individuals who need to understand educational materials
-   Readers who want a quick overview of technical documents

## 6. Project Scope

### Included Features

-   Upload text-based PDF documents.
-   Extract readable text from PDF files.
-   Generate a concise summary using a pretrained NLP model.
-   Display important key points from the document or summary.
-   Provide a simple and user-friendly web interface.
-   Evaluate the quality of generated summaries using selected
    evaluation methods.

### Excluded Features

-   Extracting text from handwritten documents.
-   Full support for scanned PDFs requiring Optical Character
    Recognition (OCR).
-   Summarizing images, videos, or audio.
-   Training a large language model from scratch.
-   Guaranteeing that every generated summary is completely accurate.
-   Replacing the need to read the original document for critical
    decisions.

## 7. Proposed System Workflow

1.  The user uploads a PDF document.
2.  The system extracts text from the document.
3.  The extracted text is checked and prepared for summarization.
4.  The pretrained NLP model generates a summary.
5.  The system presents the summary and key points.
6.  The user reviews the output and can compare it with the original
    document.

## 8. Proposed Technologies

-   **Programming language:** Python
-   **User interface:** Streamlit
-   **NLP model library:** Hugging Face Transformers
-   **PDF text extraction:** PyMuPDF
-   **Evaluation:** ROUGE and human evaluation
-   **Development environment:** Visual Studio Code

## 9. Evaluation Plan

The system will be evaluated using a small collection of publicly
available documents.

Evaluation criteria: - **Information coverage:** Does the summary
include the document's main ideas? - **Readability:** Is the summary
easy for beginners to understand? - **Factual accuracy:** Does the
summary preserve the meaning of the original document? -
**Conciseness:** Is the summary shorter than the original text while
retaining useful information?

ROUGE may be used to compare generated summaries with reference
summaries when suitable reference summaries are available. Human
evaluation will complement automatic scores because a high overlap score
alone does not guarantee factual accuracy or beginner-friendly language.

## 10. Project Limitations

The quality of the summary depends on the clarity of the extracted text
and the capabilities of the selected model. Very long documents may need
to be divided into smaller sections before summarization. The system may
occasionally omit important details or generate incorrect statements, so
users should verify important information against the original document.

## 11. Expected Outcome

A working prototype that allows users to upload a PDF and receive a
concise, readable summary and key points through a simple web interface.
