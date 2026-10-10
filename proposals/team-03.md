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

DevAccess: A Swahili Agent That Answers Development Questions from World Bank and UN Documents and Data

## Abstract

Development evidence is published in English and split between long reports and separate datasets. For this project we focus on Swahili speakers. They must read English and know which portal holds each piece. The World Bank's AVA assistant answers only from reports, so it cannot tell a farmer which months are dry locally.

DevAccess is a conversational multi-agent system that hears and answers in Swahili. Through ElevenLabs, audio is incorporated. A supervisor keeps conversation state and routes each turn: a query agent translates questions and rewrites follow-ups, a data agent selects indicators and regions from live APIs, an evidence agent retrieves report passages and project results, and a verification agent rejects unsupported claims, retrieving more or abstaining. Turns are capped at eight steps.

We tested four public APIs for Tanzania and Kenya: World Bank Climate Change Knowledge Portal (regional rainfall), UN SDG Global Database (indicators), World Bank Documents & Reports (about 380 completion reports), and IATI (UN agency project results). Documents are indexed on demand and frozen for testing.

Agents run in LangGraph on our laptops. Gemini 3.1 Flash-Lite runs agents as the cheapest current model that outlives the course; a week-one pilot checks its Swahili against backups GPT-5.6-luna and DeepSeek Flash. Free BGE-M3 embeddings handle multilingual retrieval.

Ground truth comes from 100 questions and 30 conversations validated by a Swahili speaker, API values, and World Bank evaluators' outcome ratings. We measure correctness, groundedness, and citation accuracy against direct-LLM and translation-RAG baselines, plus seconds and dollars per answered turn. Working means beating both baselines with no unsupported claims, at about one cent and under 30 seconds per turn.

Our biggest risk is the low-cost model writing poor Swahili or missing unsupported claims; the week-one pilot tests four models first, and any agent can switch models by configuration.