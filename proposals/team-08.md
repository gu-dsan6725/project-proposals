# DSAN 6725 Final Project Proposal

## Team Number

08

## Team Name

Pixel Perfect

## Team Members

| Name | NetID |
| ---- | ----- |
| Dun Xie | dx64 |
| Jianan Huang | jh2629 |
| Yixuan He | yh973 |
| Zizheng Wang | zw520 |

## Project Title

Pixel Perfect Ad Studio for Campaign Images from Phone Photos

## Abstract

A drink photographed on a kitchen counter can look flat in a social ad. An image
generator can improve the lighting and still change the lettering on the can.
Small food brands need a campaign image that fits their brief and shows the
product a buyer will receive.

Pixel Perfect will run a LangGraph workflow on a Linux VM. We will test local
rembg segmentation and hosted Gemini models for visual reasoning and background
generation to keep GPU work off the VM. A planner searches our repository for
rules on lighting, placement and props. The seller confirms the cutout, layout and any
headline. The compositor places the original foreground and approved text over
the generated scene. A critic checks product identity and fit to the brief and
can request one background repair. Sellers can approve a finished image and
request a five-second LibTV pilot clip, which we will inspect for label drift.

We aim to shoot 120 photos of drinks and fries across 60 product groups and
reserve 40 whole groups, or 80 photos, for testing. Two reviewers, blind to the
method, will score each output against its source and brief. We will compare the
agent with a fixed prompt used once and with the same prompt retried once under
the same quality trigger.
We target 80% usable ads. Each must score at least four out of five for fidelity,
brief fit and finish, keep any approved text readable and contain no critical
product or claim error. Failed and withheld outputs stay in the denominator. We
will report critic agreement with reviewers, 95% bootstrap intervals using whole
product groups, throughput, latency and cost per task.

Clutter can hide product edges. We will inspect development masks and request a
new photo before generation when the cutout cannot preserve the product.
