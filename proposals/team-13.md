# DSAN 6725 Final Project Proposal

## Team Number

13

## Team Name

Roomwise

## Team Members

| Name | NetID |
| ---- | ----- |
| Samuel Villarreal | sv635 |
| Junyi Tang | dt786 |
| Juncheng Han | jh2732 |
| Tianyu Zhao | tz297 |

## Project Title

Roomwise: An AI Agent for Roommate Matching and Apartment Search

## Abstract

Roomwise will help Washington, DC renters balance housing costs, commutes, amenities, and roommate compatibility through apartment search and optional two-person roommate matching.

A coordinator will pass structured renter preferences to matching, search, and verification agents. Matching ranks consenting profiles and explains conflicts; search retrieves listings through RentCast’s `GET https://api.rentcast.io/v1/listings/rental/long-term` endpoint, property details from permitted websites, and Google Routes/Places results; verification reconciles unit identities, checks evidence, and flags unknown fees. The coordinator returns ranked, cited recommendations. Contact sharing requires consent. API access and website permissions remain unverified.

Agents will run in a Linux VM on a local desktop; a minimal workflow will run in week one. Claude Sonnet 4.5, hosted by Anthropic, will handle tool selection, extraction from varied listing text, and evidence-based explanations because these tasks require language interpretation across sources. Local Python will enforce constraints, score preferences, and calculate costs for reproducibility.

One task is a search for one household, assessing up to ten listings and returning up to three recommendations. Targets are p95 latency below 60 seconds and mean model-plus-external-API cost below $0.25 per task. From week one, we will log elapsed seconds, token usage, API charges, failures, and throughput, separating cached and live runs.

Our evaluation harness will compare agents with deterministic filters and preference scoring on 100 held-out synthetic scenarios. Two teammates will label eligibility, amenities, and known monthly costs from dated listing snapshots and resolve disagreements. Targets are at least 95% hard-constraint satisfaction, amenity extraction F1 of 0.90, and monthly-cost mean absolute error below $10 where costs are complete. We will report sample sizes, confidence intervals, baseline scores, and changes prompted by separate development-set failures. Blinded user preferences will assess ranking usefulness.

The biggest risk is unavailable rental data; we will test access first and fall back to a permitted, dated, manually curated DC dataset.
