# DSAN 6725 Final Project Proposal

<!--
Copy this file to proposals/team-NN.md, where NN is your two digit project group
number. Project group 7 submits proposals/team-07.md.

Fill in every section. The validator ignores comments like this one, so leave them
in place or delete them.
-->

## Team Number

06

## Team Name

The Hidden Layers

## Team Members

| Name | NetID |
| Ellie Byrd | eb1481 |
| Katie DiPaolo | kmd347 |
| Maura Mann | mm5514 |

## Project Title

Machine-Made Morning News

## Abstract

With so much news and content online, it can be difficult to keep up with what you actually care about. Our system takes articles a user has saved for later and searches for additional news based on their interests. It then turns the most relevant content into a short, personalized newsletter. For our agent architecture, a search agent will generate queries based on topics the user is interested in. It will run them, fetch and parse article page content, and decide whether the results are good enough. This loop will continue to create a solid corpus. A curator agent will read the corpus, add articles from the read-later folder, deduplicate and rank articles to the user’s interests, and send any gaps back to the search agent. The summarizer agent will write a summary of each article with citations to the text. The editor agent will contain the guardrails for checking summarization content, potentially sending articles back to the summarizer. It will send the final output to be saved or sent as an email. One data source will be the user’s local “read-later” folder. We will use SearXNG for web searches and RSS feeds for general news articles. To evaluate the system, we will use cosine similarity between the source material and newsletter to ensure meaning is retained. We will use the Flesch-Reading Ease score to maintain readability and the SummaC score to measure whether the newsletter includes hallucinations. Lastly, we will use LLM-as-a-judge to ensure fluent output. Our biggest risk is getting a smaller local model to work reliably overall. We are especially concerned about the summarization quality and latency. To manage this, we will start with a more limited version of the system and improve the prompts and guardrails as we test it.
