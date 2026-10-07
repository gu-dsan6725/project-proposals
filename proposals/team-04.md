# DSAN 6725 Final Project Proposal

## Team Number

04

## Team Name

TEAM NAME

## Team Members

| Name                 | NetID  |
| -------------------- | ------ |
| Ishika Gobin.        | ig294  |
| Sharanya Atluri      | sa2292 |
| Yi-Ting Chin         | yc1348 |
| Sebastian Villalobos | sv642  |

## Project Title

TuneCheck: comparing a base model and its fine-tuned version on the actions they take as agents

## Abstract

Teams fine-tune open models to improve a task, then must decide whether to release the
new version. Fine-tuning can change unintended behavior, even on benign data. A model
that improves at its task might also take a forbidden action or skip a required
escalation. Chat-based evaluations show what a model says, not what it does when it
can act.
 
We will build TuneCheck, a multi-agent system that supports this release decision for
tool-using workflows, each defined by its task, tools, permissions, and simulated
environment. It runs as a state machine with five agents. An orchestrator plans runs
and handles failures. A data agent checks and versions training data. After a
preflight check confirms the base model can use the tools, a training agent fine-tunes
a supported Qwen3 model with one fixed QLoRA recipe. Qwen3-8B is our provisional
reference because it supports tool use and may permit repeated audits within eight
weeks. An eval builder drafts test cases; code computes expected outcomes, and a human
freezes the suite. An audit agent compares base and fine-tuned models on the same
frozen cases and explains where their behavior differs, citing the cases.
 
Training data comes from a small approved collection of public datasets; test cases
are synthetic. We evaluate five workflows using ordinary fine-tunes, unchanged
controls, and independently confirmed regressions, holding out final cases by scenario
type. Code scores task success, tool-call validity, permission violations, state
changes, and escalations. We report regression detection rates, false alarms,
unnecessary refusals, and cost and time per report. A well-prompted base model shows
whether fine-tuning was needed. A ModelLens probe tests whether internal activations
contain information about unauthorized actions before they happen.
 
The service runs on a Jetstream2 VM with a GPU worker. The main risk is GPU access,
with pay-per-use GPU jobs as the fallback.
