**AI Document Summarizer for Beginners**

**Evaluation Criteria Table**

| Objective/ Requirement | Criterion | Capability Bucket | Measurement Method | Metric | Proposed Threshold | Expected User Outcome |
| :---- | :---- | :---- | :---- | :---- | :---- | :---- |
| O2 / FR1–FR2 | PDF upload and text extraction | Domain-specific capability | Test 10 supported text-based PDFs and check extracted body text. | Successful extraction rate | At least 9/10 files | Users can submit common PDFs without copying all text manually |
| O2 / FR3 / NFR3 | Summary preserves main ideas | Generation capability | Compare with reference summaries where available | ROUGE | Average coverage ≥ 3/4 | Users receive a useful overview rather than a summary that misses most key ideas. |
| O2 / FR4 / NFR4 | Summary and key points are understandable | Generation capability | Ask 3–5 volunteer reviewers to rate clarity on a consistent 1–5 scale | Mean clarity rating | ≥ 4.0/5; report sample size | Beginners can understand the output |
| O3 / RAI1 | Limitation notice is visible | Instruction-following capability | Inspect all result screens and relevant limit/error states | Warning presence rate | 100% of result screens | Users are reminded to verify important claims |

**Reflection — Most Important Criterion**  
The most important criterion is main-idea coverage together with factual consistency. The app is useful only if the summary helps beginners understand the document without materially changing its meaning. Speed and interface quality matter, but a fast and readable summary that misrepresents the source would fail the main purpose.  
