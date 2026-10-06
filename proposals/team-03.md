# DSAN 6725 Final Project Proposal

## Team Number

03

## Team Name

Team 3

## Team Members

| Name            | NetID  |
| --------------- | ------ |
| Bo Zhu          | bz263  |
| Jing Tan        | jt1573 |
| Munashe Mhlanga | mm5481 |
| Yanmin Gui      | yg452  |

## Project Title

Paper Trail: An Agentic Search Assistant for Verifiable Answers from Enterprise Knowledge

## Abstract

Company knowledge is scattered across Slack, email, wikis, and shared drives, and it changes faster than documents are updated. New employees do not know where to look, everyone risks acting on stale information, and RAG assistants can confidently invent answers. 

We build an internal knowledge search agent. An employee describes what they need. The agent searches, reads documents and threads, and follows leads to mentioned people, tickets, and documents. It compares versions of the same information by date, author, and source to decide which is current, and flags conflicts it cannot resolve. It stops when the evidence is complete and abstains when nothing relevant exists. It returns a list of relevant documents, each with a reference, why it matters, and a note if it is outdated or conflicting. An independent reviewer agent checks the final output and rejects any claim without a supporting document. All actions are read-only.

Our data is EnterpriseRAG-Bench (Onyx, public on GitHub and Hugging Face): about 500,000 documents from nine sources, including Slack, Gmail, Drive, and Jira, plus 500 labeled questions. Tools include BM25 and dense retrieval, document readers, and metadata lookup, with an LLM accessed through a commercial API.

We measure correctness, completeness, Recall@10, and how often the agent identifies the current version on conflicting-information questions and on version conflicts we inject. Working means clearly outperforming the BM25 baseline and almost never answering questions that have no answer in the documents.

Our biggest risk is fabrication when no answer exists. Instead of admitting it found nothing, the agent may stitch loosely related documents into a confident but false answer, or cite a document that does not support its claim. For internal search, one fabricated policy is worse than no answer.
