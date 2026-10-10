# DSAN 6725 Final Project Proposal

## Team Number

09

## Team Name

The House of Games

## Team Members

| Name               | NetID |
| ------------------ | ----- |
| LeAnn Lo            | lnl20 |
| Nkemdibe Okweye     | no252 |
| Mohammed Elhag      | me878 |
| Oluwatosin Ayokunle | ta732 |
| Mohammad Yassin     | my677 |

## Project Title

RefBot: An AI Referee for Game Night

## Abstract

Game night always ends in arguments. Can you stack a +2? Most people cannot tell
official rules from house rules, and chatbots often repeat the myths. We will build
RefBot, an AI referee that answers rules questions through a regular chat and can
watch a game through a phone camera to check whether a play was allowed.

Our system will use multiple agents. One agent identifies the game and version. A
second searches official rulebooks for about thirty popular games from Hasbro, Mattel,
and other publishers. A third flags house rules. For the camera, another agent reviews
the last thirty seconds, starting with Uno and chess, while a simple rules program
checks whether each play was legal. RefBot will not answer without citing the relevant
rule. The agents will run on a cloud server that our iPhone app connects to. A hosted
vision model (Qwen-VL) will read cards and boards. For answering rules questions and
routing between agents, we will test small local models (Qwen3 8B and Llama 3.1 8B)
and a hosted model (Claude Haiku), keeping whichever performs best on our test set.

To test RefBot, we will write 200 rules questions with answers from the rulebooks and
film 50 game clips, half containing an illegal play. We will compare RefBot with a
regular chatbot and with a single prompt containing every rulebook. We will measure
accuracy, how often each system mistakes a house rule for an official rule, and time
and cost per answer, with confidence intervals. If an AI grades answers, we will
spot-check the results ourselves. RefBot succeeds if it beats both baselines on
accuracy.

Our biggest risk is the camera misreading the game. We will use a fixed overhead
camera and switch to photos if video accuracy stays below 90%.
