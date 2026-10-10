# DSAN 6725 Final Project Proposal

<!--
Copy this file to proposals/team-NN.md, where NN is your two digit project group
number. Project group 7 submits proposals/team-07.md.

Fill in every section. The validator ignores comments like this one, so leave them
in place or delete them.
-->

## Team Number

<!-- Your project group number, digits only. Example: 07 -->
07

## Team Name

<!-- A short name for your team. Example: Retrieval Rangers -->
ASU Sun Devils

## Team Members

<!--
One row per member, 2 to 4 members. Give your full name and your Georgetown NetID,
the short login like ab1234 rather than your email address.
-->

| Name | NetID |
| ---- | ----- |
|  Nikhil Poluri    |  np752 |
|  Sam Gold    |   sg1951    |
|  Matt Hakim    |    mh2451   |
|  Bilal Malik    |     bm1262  |
## Project Title


 PrivateBench: Generating Private Coding Benchmarks for Cost-Aware AI Model Selection and Routing

## Abstract

<!--
250 to 300 words, and no more than 300. Cover all seven. One sentence each does
for 5 and 6.

1. The problem you solve and why it matters
2. Your agent architecture: what the agents are and how they coordinate
3. The data sources and external tools or APIs you will use
4. How you will evaluate the system: the metrics, the baseline you run against,
   and where your ground truth comes from
5. Where the agents run, which models you use, and why those models
6. The latency and the cost you will measure for one unit of work
7. The biggest risk to finishing in eight weeks, and your plan for it

Read "What makes an evaluation credible" in README.md before you write 4. It
carries more weight than anything else you build.
-->

It is important that individuals or teams know which large language models (LLMs) perform tasks best, considering efficacy and cost. While public leaderboards are capable of offering useful comparisons, they are often prone not only to data contamination but also to overgeneralization.
PrivateBench takes an input that explains the user's workload and tasks, tools, and constraints; generates private benchmarks; and investigates whether choosing a model at different steps improves our success metric per dollar. An orchestrator manages multiple agents to extract details from the input, generate realistic tasks, and verify testing quality. An agent will attempt those tests with LLMs being swapped in and out. We will utilize SWE-smith for generating tasks, DeepSWE for contamination-resistant evaluations, and Pier to run those tasks in isolated environments. Public access is confirmed.
The grader will compare checked tests with a one-pass generation and routing against a fixed model and escalations, where we start with the cheapest model and scale up if it struggles. Metrics include grading errors, task success, cost, and completion time. Two human judges will compare grader accuracy. Success would be quantified as less than 5% total false categorizations and a 5% increase in task success at similar costs for unseen tasks, with confidence intervals reported for routing. The risk we face is the incorrect verdicts placed by the grader, so it is crucial to start with a small set of tasks whose correctness we know, and scale up if those constraints are resolved.
We propose running the agents on an Ubuntu m7i.xlarge VM. The models will be accessed through a hosted API, utilizing Bedrock. The initial model selection is GPT Luna, Gemini Flash, and GPT Sol to compare different price tiers. We classify our unit as one software-repair run, for which we can measure completion time and total cost.
