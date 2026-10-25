# Week 1: Observation Sheet

## Project Title

**AI Document Summarizer for Beginners**

## 1. Purpose of the Observation

The purpose of this observation is to understand the difficulties
students and beginners may face when reading long academic or technical
documents, and to identify how an AI summarization system could help.

## 2. Target Users

-   University students who read academic papers and reports.
-   Beginners who are unfamiliar with technical terminology.
-   Readers who want to identify the main ideas before reading a full
    document.

## 3. Problem Observations

The following are initial observations and hypotheses to validate with
target users. They are not presented as results from a completed survey.

  -----------------------------------------------------------------------
  No.                     Observation or          Possible Effect on
                          Hypothesis              Users
  ----------------------- ----------------------- -----------------------
  1                       Long documents can take Students may struggle
                          considerable time to    to review several
                          read.                   documents within
                                                  limited time.

  2                       Academic and technical  Beginners may find the
                          documents may contain   main ideas difficult to
                          unfamiliar terms.       understand.

  3                       Important information   Readers may have
                          may be spread across    difficulty identifying
                          many sections.          the key points quickly.

  4                       Very short summaries    Users may misunderstand
                          may leave out important the original document.
                          context.                

  5                       AI-generated summaries  Users need to check
                          may contain omissions   summaries against the
                          or inaccurate           source document.
                          statements.             
  -----------------------------------------------------------------------

## 4. Existing Approaches

-   **Reading the full document:** provides context but can take time.
-   **Reading the abstract or conclusion:** gives a quick overview but
    may not cover all important sections.
-   **Manual note-taking:** allows users to choose important points but
    requires effort.
-   **AI summarization tools:** can generate shorter text automatically,
    but the quality and readability of the output must be checked.

Hugging Face's Transformers documentation describes summarization as
producing a shorter version of a document while preserving important
information. It distinguishes extractive summarization from abstractive
summarization.

Reference:
https://huggingface.co/docs/transformers/main/tasks/summarization

## 5. Proposed AI Solution

Develop a simple web application that allows a user to upload a
text-based PDF. The application extracts the text, uses a pretrained NLP
summarization model to generate a concise summary, and displays the
result along with key points.

## 6. Initial User Needs

-   Easy PDF upload.
-   A summary that is shorter than the original document.
-   Key points that help users review the content.
-   Clear, readable output.
-   A reminder to verify important claims against the original document.

## 7. Initial Requirements

### Functional Requirements

1.  The system shall allow users to upload a PDF file.
2.  The system shall extract readable text from the uploaded PDF.
3.  The system shall generate a summary from the extracted text.
4.  The system shall display the summary to the user.
5.  The system shall display key points or important sentences.

### Non-Functional Requirements

1.  The interface should be simple for beginners.
2.  The system should provide clear feedback if a PDF cannot be read.
3.  The summary should be generated within a reasonable waiting time for
    the selected test documents.
4.  The system should handle uploaded documents carefully and avoid
    exposing them unnecessarily.

## 8. Initial Assumptions and Validation

These observations are starting hypotheses. They should be validated by
asking a few target users about their reading habits and by testing the
prototype on public documents.

Possible validation questions: - What types of long documents do you
read most often? - What is the most difficult part of understanding
them? - Would a short summary, key points, or simpler explanations be
most useful? - What errors would make you lose trust in an AI-generated
summary?

## 9. Initial Conclusion

A beginner-friendly document summarizer may help users review long
documents more efficiently. The project should prioritize readable
summaries, clear limitations, and evaluation of factual accuracy rather
than assuming that AI-generated output is always correct.
