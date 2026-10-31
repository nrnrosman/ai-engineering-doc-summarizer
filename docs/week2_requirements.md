**AI Document Summarizer for Beginners**

**Section 0 — Project Framing and Application Scope**

| Section 0 — Project Framing & Application Scope Checkpoint | Save in: docs/week2\_requirements.md |
| :---- | :---- |
| **Problem Evidence** | Students and beginners may find lengthy academic and technical documents difficult to review quickly, especially when they contain unfamiliar terminology. Summarization is an established NLP task intended to produce a shorter version of a document while preserving important information. Hugging Face's documentation describes extractive and abstractive summarization and shows that input length and evaluation are practical engineering considerations. 1\. Hugging Face, Summarization — Transformers documentation: https\://huggingface.co/docs/transformers/main/tasks/summarization 2\. https\://www\.tandfonline.com/doi/full/10.1080/10494820.2025.2604649 |
| **Existing Approaches** | BART – Denoising Sequence-to-Sequence Model: Automatically generates coherent, concise summaries without simply copying sentences from the original text Scholarcy: Reduces the effort required to read lengthy academic papers and identify important findings SciSpace: Makes complex academic documents easier to understand, particularly for students and beginner researchers |
| **Project / Engineering Gap** | Preserving important information and factual accuracy Handling lengthy PDF documents |
| **Objective O1** | To design a beginner-friendly AI document summarization system architecture that integrates PDF text extraction and automatic text summarization. |
| **Objective O2** | To develop an AI document summarisation application that allows users to upload text-based PDF documents and generate concise summaries and key points using a pretrained NLP model. |
| **Objective O3 (if relevant)** | To evaluate the developed system based on summary quality, readability, factual consistency and document processing time. |
| Intended Users | University students, beginners reading academic or technical documents, and readers who want an initial overview before reading a full document. |
| Supported Tasks | \- Upload a text-based PDF. \- Extract readable text. \- Generate a concise summary and key points. \- Allow the user to review the output against the original document. |
| Information / Knowledge Domain | General educational and technical information in public text-based PDFs, initially including research papers and educational reports. The system is not intended to provide authoritative medical, legal, financial, or other professional advice. |
| Operating Context | A user uploads a PDF through a simple web interface, waits for processing, then reviews the summary and key points. This is a coursework prototype, not a production service. |
| Important Constraints | \- Beginner-level implementation experience. \- Use a pretrained model rather than training a large model from scratch. \- Long documents may need chunking due to model input limits. \- Scanned PDFs and complex tables may not extract correctly. \- Evaluation uses a small, manageable set of public documents. \- Processing speed depends on the chosen model and environment. |
| Explicit Out-of-Scope Tasks | OCR for scanned/handwritten documents, summarizing audio, video, or image-only files, guaranteeing complete accuracy, replacing the original document or expert advice, making high-stakes decisions, training a large model from scratch, and building a production service with permanent document storage. |
| Evaluation Focus | Determine whether the prototype extracts supported PDFs, produces useful and shorter summaries, preserves main ideas without introducing unsupported claims, provides readable output, and processes test documents in acceptable time. Targets below are proposed, not measured results. |

**Section 1 — Functional Requirements (FR)**

| ID | Requirement – The system SHALL | Scope Boundary – SHALL NOT |
| :---- | :---- | :---- |
| FR1 | Allow user to upload one supported text-based PDF | Claim support for all PDFs, encrypted PDFs, or scanned PDFs |
| FR2 | Extract readable text and notify the user if no usable text is found | Continue silently with empty or unusable text |
| FR3 | Generate a concise summary from extracted text using an AI summarization capability | Claim the summary includes every detail or is guaranteed correct |
| FR4 | Display the summary and a clearly labelled list of key points | Present generated points as verified facts without a limitation notice |
| FR5 | Display a notice that AI summaries may omit or misstate information and important claims should be checked against the original PDF | Present the summary as a replacement for the original document or professional advice |

**Section 2 — Non-Functional Requirements (NFR)**

| ID | Quality Attribute | Requirement | Measurement Method | Metric | Proposed Threshold |
| :---- | :---- | :---- | :---- | :---- | :---- |
| NFR1 | Performance | Process small supported PDFs within reasonable waiting time | Time 10 runs in the same environment | Median end-to-end time | ≤ 60 seconds for agreed test PDFs up to about 10 pages |
| NFR2 | Reliability | Complete processing without an unhandled crash for supported files | Run 10 supported PDFs and record success/crashes | Successful processing rate  | ≥ 90% |
| NFR3 | Output quality | Preserve main ideas in generated summaries | Compare with references where available and manually rate at least 5 summaries | ROUGE where references exist | Average coverage ≥ 3/4 |
| NFR4 | Usability / readability | Produce output understandable to beginners | Ask 3–5 volunteer reviewers to rate clarity using the same 1–5 scale | Mean clarity rating | ≥ 4.0/5 |

**Section 3 — Responsible AI Requirements (RAI)**

| ID | Risk | Requirement | Measurement Method | Metric | Proposed Threshold |
| :---- | :---- | :---- | :---- | :---- | :---- |
| RAI1 | Factual Consistency | Show a clear notice that summaries can contain omissions/errors and should be checked against the source | Inspect every result screen and relevant error | Notice presence rate | 100% of summary result screens |
| RAI2 | Transparency | Retain the source filename and make the original available for comparison during the session where feasible | Test 5 PDFs and inspect output for unsupported citations | comparison success | zero fabricated page citations |
| RAI3 | Scope | Describe the app as educational summarization, not professional medical, legal, financial, or other high-stakes advice. | Inspect interface and result screens | Scope notice presence | 100% of result views display or link to the notice |

**Reflection — Most Difficult RAI Requirement**  
RAI1, factual consistency, is likely the hardest to measure. A summary can sound fluent while omitting qualifications or adding unsupported claims. ROUGE measures text overlap with a reference and cannot fully establish factual correctness. A practical approach is to identify key claims in each source, check whether the summary preserves them, and record unsupported or contradictory claims using a small manual rubric. This provides useful evidence but cannot guarantee that every error is found.  
