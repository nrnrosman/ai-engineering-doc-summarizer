**AI Document Summarizer for Beginners**

 **2\. Architecture Needs Derived from Requirements**

| Requirement | Need | Architecture Response |
| :---- | :---- | :---- |
| FR1 | User submits a supported PDF | PDF upload component in the interface |
| FR2 | Extract text and report failure | Pretrained summarization capability |
| FR3 | Generate a shorter version of extracted text | Pretrained summarization capability |
| FR4 | Present summary and key points clearly | Results view with separate summary and key-point sections |
| FR5/NFR2 | Handle empty, unsupported or long documents | Input-length check, chunking or explicit limit, clear error messages |
| NFR1 | Measure processing time | Timing around extraction and summarization |
| NRF3 | Evaluate output quality | Evaluation dataset, reference comparisons where available, human rubric |
| NFR4 | Make output readable | Simple presentation layer and clarity review |
| RAI1 / RAI4 | Communicate limitations and scope | Visible disclaimer on interface/results |

**3\. Architecture Decision Records (ADR)**

| Decision | Requirement / Constraint | Alternatives Considered | Selected Option | Trade-off Accepted |
| :---- | :---- | :---- | :---- | :---- |
| Use a pretrained summarization model | A summary within reasonable time, at no per-run cost, and without training a model from scratch | Pretrained model via Hugging Face Transformers | Pretrained model via Transformers, run locally | Lower quality than large hosted LLMs, and a risk of unsupported statements in the summary. This is mitigated by evaluating factual accuracy, not just ROUGE. |
| Do not add external knowledge access | Summaries must reflect the uploaded document only | Base model only; static search over a knowledge base; dynamic retrieval from external sources | No external knowledge component. The uploaded PDF is the only source. | The system cannot check the summary against outside sources. This is handled by notices and by keeping the original available for comparison |

 **4\. Initial Requirements Traceability Matrix**

| Objective | Requirement | Evaluation Criterion | Architecture Element | Later Evidence |
| :---- | :---- | :---- | :---- | :---- |
| O2 | FR1/FR2 | PDF upload and extraction success | Upload interface, extraction, validation | Results from 10 supported PDFs and extraction-failure log |
| O2 | FR3/FR4/NFR3 | Main-idea coverage and usefulness | Text preparation, summarization, results view | Outputs, reference comparisons where available, and rubric scores for ≥5 documents |
| O3 | RAI1/RAI4 | Warning and scope notice presence | Interface/result disclaimer | Checklist confirming notice on each result screen |
| O3 | RAI2/RAI3 | Source comparison and no unintended persistent copies | Session-level source access and temporary-file cleanup | \| Five-PDF source test and temporary-storage inspection |

**6\. Reflection — Most Important Trade-off**  
The main trade-off is using a pretrained model while supporting long documents. Pretrained models keep development manageable but have finite input lengths and may omit details. Chunking can cover more of a document, but adds complexity and may lose relationships between sections. 

