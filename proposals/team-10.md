# DSAN 6725 Final Project Proposal


## Team Number

10

## Team Name

Law and Disorder

## Team Members

| Name        | NetID  |
| ----------- | ------ |
| Fareeza Ali | fa689|
| Jiayuan Gong | jg2493 |
| Jen Guo | yg429 |
| Jackson Howes | jh2787 |

## Project Title

Building a Trust Layer for Multi-Agent Systems

## Abstract

Agents share information faster than anyone can review it, so the usual fix is a verifier agent. But a same-model verifier shares its peers' blind spots, and trust fails in both directions: credulous agents accept false claims, paranoid agents reject true ones, and fixing one worsens the other. Users get wrong or incomplete answers.
We build a trust layer that stops false claims without making agents distrust each other, and test it in two systems. In an AgentDojo assistant, an orchestrator delegates to email, calendar, and banking sub-agents, which report back before it acts. In a drone swarm, drones share sightings with each other and a coordinator. The layer sits on every message and checks important claims against evidence it finds itself.
AgentDojo is a public benchmark with tasks, attacks, and scoring; our drone simulator needs no outside data. We call models through the DeepSeek and Anthropic APIs.
We compare against no defense, distrust prompts, a verifier agent, and taint tracking. Ground truth comes from AgentDojo's built-in checks and the simulator, not an LLM judge. We measure false claims reaching an action, true claims blocked, and task success, with confidence intervals. The layer works if it stops as many false claims as the best baseline while blocking fewer true ones or costing less.
Agents are built in Python with LangGraph and run in Docker on AWS EC2. Most runs use DeepSeek V4 Flash, which is cheap enough for thousands of runs; Claude Haiku 4.5 repeats a subset to test another model family.
For each AgentDojo task or drone mission, we measure latency in seconds and cost in dollars.
Our biggest risk is building the drone simulator from scratch. We'll keep it to a simple grid, and if false claims aren't spreading by week three, we'll focus on AgentDojo.
