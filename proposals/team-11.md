# DSAN 6725 Final Project Proposal

<!--
Copy this file to proposals/team-NN.md, where NN is your two digit project group
number. Project group 7 submits proposals/team-07.md.

Fill in every section. The validator ignores comments like this one, so leave them
in place or delete them.
-->

## Team Number

11

## Team Name

Vinny Squad

## Team Members

| Name | NetID |
| ---- | ----- |
| Vinny Turtora     |vt216       |
| Laurent Calac     |lj589       |
| Nashita Syed      |sj1073      |
| Nikhil Patla      |np767       |

## Project Title

Airlock

## Abstract

Coding agents run shell commands in real repositories, and their mistakes reach disk before review. Public reports describe agents deleting databases and home directories. When tests guard the merge, agents can pass them by editing the tests, and checkpoint features such as Claude Code's miss whatever the shell changed.

We will build Airlock, a multi-agent system that runs each coding task as a transaction. A planner agent searches the repository and writes a task contract: files in scope, checks to pass. The worker, built on mini-swe-agent, then solves the task in a branch of an isolated sandbox, and only its patch leaves. In a clean sandbox holding the base image plus that patch, a policy checker inspects the diff and side-effect log, the tests run, a test-writer agent adds tests derived from the issue, and a reviewer agent hunts for test tampering. Commit authority belongs to a plain-code controller, which commits the patch or rolls the sandbox back and returns the reasons for one retry. We compare three backends: git worktrees, Docker containers, and smolvm microVMs.

Tasks come from SWE-bench Pro (Python, Go), SWE-bench Multilingual (Rust, Go), and Impossible-SWEbench, where any passing patch must cheat; all three load from Hugging Face. We also write 40 trap tasks and a crash-injection suite. The metrics are false-accept and false-reject rates, rollback correctness, and latency and dollars per task. Working means accepting under 10% of cheating patches, rejecting under 10% of correct ones, and restoring the exact prior state after every injected crash.

The biggest risk is smolvm, a young tool that needs KVM on an x86 host. We hide all backends behind one interface, run on a cloud VM with nested virtualization, and let Docker carry the results if smolvm fails our week-two check.
