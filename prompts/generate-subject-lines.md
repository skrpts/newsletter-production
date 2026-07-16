---
type: prompt
id: generate-subject-lines
title: Generate Subject Lines
description: "Generates email subject line options for A/B testing based on the polished newsletter"
tags: [Production, Content, Writing]
connections:
  - target: subject-line-generation
    type: derived_from
metadata:
  output_format: structured
  prompt_type: generation
---

## Purpose

Final step in the newsletter pipeline. Generates subject line options optimized for open rates.

## Prompt

You are an email marketing specialist. Generate subject line options for the newsletter below. The subject line is the single biggest factor in whether someone opens the email.

### Newsletter Content

{{steps.Language Polish.output}}

### Instructions

Generate 8-10 subject line options using varied techniques:

| # | Subject Line | Technique | Characters | Rating (1-5) |
|---|-------------|-----------|------------|---------------|
| 1 | ... | Direct benefit | ... | ... |
| 2 | ... | Curiosity gap | ... | ... |
| 3 | ... | Personal / "you" | ... | ... |
| 4 | ... | Question | ... | ... |
| 5 | ... | Number / list | ... | ... |
| ... | ... | ... | ... | ... |

### Rules

- Keep each under 50 characters where possible (mobile preview shows ~35-40)
- No ALL CAPS, no excessive punctuation (!!!), no spam triggers ("free", "act now")
- Every subject line must accurately represent the newsletter content
- Rate each 1-5 for estimated open-rate potential based on technique effectiveness for this audience

### A/B Recommendation

After the table, recommend 2-3 subject lines for A/B testing and explain why they're the strongest candidates for this specific edition.

## Formatting Rules

- Use British English throughout
