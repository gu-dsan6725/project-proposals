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

Product-Safe Ad Generator: AI agents that make ad images and headlines without changing the product

## Abstract

Small online sellers have plain product photos but few ad images. AI image tools often change the product's color, shape, or logo, so sellers must check every result by hand.

Our agents turn a product photo and a short request into an ad image and headline without changing the product. A short video is a stretch goal. A planning agent reads the catalog record and finds reference scenes. A generation agent cuts out the product and creates only the background. A copy agent writes the headline from catalog facts. A checking agent tests each result and sends failures back for up to two fixes. Guardrails block logo changes, made-up claims, and added people or brands.

Our data is the Amazon Berkeley Objects dataset (CC BY 4.0), available for download from AWS. We will use 20 development and 60 test products, with three requests each, for 180 test tasks.

The baseline is one prompt that edits the whole image. Ground truth is the original photo, the catalog record, and 300 outputs that two team members label as usable or not. We report color and shape match, text match, supported-claim rate, and usable-ad rate with n and confidence intervals, plus judge agreement with our labels.

The agents run on a cloud GPU VM. We compare a hosted Gemini image model with open-source Qwen-Image-Edit on quality and cost, and measure time and cost per usable ad.

The biggest risk is an AI judge that disagrees with people, so we label first and trust the judge only once it matches us.