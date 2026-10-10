# DSAN 6725 Final Project Proposal


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

With so much news online, it can be difficult to keep up with what you care about. Our system takes articles a user saved and searches for additional news based on their interests, turning the most relevant content into a personalized newsletter. For our agent architecture, a search agent will generate queries based on topics they are interested in. It will fetch and parse article content and decide whether the results are useful. This loop will continue to create a corpus. A curator agent will read the corpus, add articles from the read-later folder, deduplicate and rank articles using the user’s interests and feedback, and send gaps back to the search agent. The summarizer agent will summarize each article with citations. The editor agent will contain guardrails for checking summarization content, potentially sending articles back to the summarizer. The output will be saved or sent as an email. One data source will be the user’s local “read-later” folder. We will use SearXNG for web searches and RSS feeds for news articles. To evaluate, we’ll use cosine similarity and SummaC between the source and newsletter to score meaning and hallucinations. The baseline for both is the source compared to an unrelated article. We’ll use Flesch-Reading Ease for readability with a baseline of the source score. The source is the ground truth and we’ll look for all metrics to score high. We will use LLM-as-a-judge to ensure fluency. We’ll use Qwen models running locally to maintain privacy and low cost. We’ll measure the time and tokens needed to produce one newsletter. Our biggest risk is getting a smaller local model to work reliably, particularly with summarization quality and latency. To manage this, we will start with a limited system and improve the prompts and guardrails as we test it. 
