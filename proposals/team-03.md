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

Company knowledge is scattered across chats, email and goes stale quickly. Employees cannot find the current answer, and AI assistants confidently invent one.

We build a multi-agent system on top of a context layer: a graph of people, teams, projects, tickets, and documents, with owners, dates, and version links, extracted from the corpus. For each employee request, an investigator agent uses this graph to plan searches, reads text and page images, follows leads to related people and tickets, and compares versions to decide which is current. It returns relevant documents with references, flags outdated or conflicting ones, and abstains when nothing exists. An independent reviewer agent rejects any claim without supporting evidence. All actions are read-only.

Our data is EnterpriseRAG-Bench (Onyx, public): about 500,000 documents from nine sources plus 500 labeled questions. We augment it with document screenshots, PDF pages, tables, and figures rendered from its 1,875 spreadsheets, 153 slide decks, and wiki tables, removing text originals so answers require the images.

Qwen3-VL-Plus (Alibaba Cloud API) runs the investigator because one model reads page images and calls tools. Qwen-Plus runs the reviewer because checking claims against cited text is simpler; it never sees the investigator's reasoning. Local Qwen3-Embedding keeps indexing free. Agents run in a Docker container on an AWS EC2 instance.

Ground truth comes from the benchmark's gold documents and answer facts, the facts we render into each image, and injected version conflicts. We measure correctness, Recall@10, current-version accuracy, image-question accuracy, and abstention on unanswerable questions, plus seconds and dollars per answered question from week one. Working means clearly beating the benchmark's baselines at a few cents and under a minute per question.

Our biggest risk is fabrication when no answer exists: the agent may stitch loosely related documents into a confident but false answer.
