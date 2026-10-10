# DSAN 6725 Final Project Proposal

## Team Number

01

## Team Name

Grand Theft Agents

## Team Members

| Name | NetID |
| ---- | ----- |
| Mingyang Han | mh2393 |
| Yuhua Pang | yp310 |
| Wenhao Zhou | wz335 |
| Zhaoyang Dong | zd199 |

## Project Title

PreMarket Pulse: Evidence-Grounded Multi-Agent Research and Testable Daily Predictions for Active Stocks

## Abstract

Each morning, investors face hundreds of headlines, filings, and price moves without knowing which stocks matter and why. LLM chat tools answer from memory, cite weakly, and mix pre-open knowledge with later events.

A Discovery Agent narrows the S&P 500 to its 10 hottest stocks over a rolling seven-day window, scoring Alpaca market signals (price change, relative volume, volatility, pre-market movement) and Alpaca news attention deterministically. A Research Agent investigates these stocks and a user watchlist through SEC EDGAR, company releases, and news, writing sourced bullish and bearish evidence. Before the open, a Prediction Agent makes one UP or DOWN call per stock with confidence and reasons, frozen at 9:15 AM ET. After the close, an Evaluation Agent scores direction in code and judges the stated reasons. A timestamped shared memory keeps later information out of predictions.

The agents run in Docker on an AWS EC2 t3.small instance. Claude Sonnet 5 drives research and prediction, which need long context and cross-source reasoning; GPT-5.4 nano handles simple, high-volume news tagging and deduplication; a GPT-5.4 mini judge avoids same-family grading bias. Our unit of work is one stock report, measured in seconds and dollars; all must finish before 9:15.

Ground truth comes from SEC 8-K filings for event recall, Alpaca prices for figure accuracy, and session open and close for direction. We compare directional accuracy over 15 live trading days (about 400 predictions, n beside every rate) against always-up, pre-market-momentum, and random baselines, check calibration, and validate the judge against 100 human-labeled cases.

We debug on historical data and score only live runs. API costs are self-funded, so we track only 10 hot stocks. The biggest risk is time: scoring starts only when all four agents run live, so we build minimal versions first, starting with Agent 1.
