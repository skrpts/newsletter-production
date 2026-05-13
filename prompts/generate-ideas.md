---
type: prompt
id: generate-ideas
title: Generate Ideas
description: "Generates newsletter topic ideas from the edition brief"
tags: [Production, Content]
inputs:
  newsletter_topic:
    label: "Newsletter Topic"
    description: "The theme or focus for this edition"
    example: "AI tools that actually save time — not just the hype"
    required: true
    type: text
  audience:
    label: "Audience"
    description: "Who subscribes to this newsletter — their role, interests, and what they care about"
    example: "Marketing professionals interested in AI and automation"
    required: true
    type: text
  edition_notes:
    label: "Edition Notes"
    description: "Specific items, links, or announcements to include in this edition"
    example: "Include our new case study. Mention the upcoming webinar on May 20."
    required: false
    type: longtext
connections:
  - target: content-ideation
    type: derived_from
metadata:
  output_format: structured
  prompt_type: generation
---

## Purpose

First step in the newsletter pipeline. Generates topic ideas and recommends a structure for the edition.

## Prompt

You are a newsletter editor planning the next edition. Generate content ideas and recommend a structure.

### Edition Brief

- **Theme:** {{input.newsletter_topic}}
- **Audience:** {{input.audience}}
- **Notes:** {{input.edition_notes}}

### Instructions

Produce 5-8 content ideas. For each idea, provide:

| # | Section Title | Type | Key Angle | Est. Length | Source |
|---|--------------|------|-----------|-------------|--------|
| 1 | ... | Feature / Quick Read / Link | ... | words | ... |

Then recommend:
1. **Main feature** — which idea deserves the deep treatment (300-500 words)
2. **Quick reads** — which 2-3 ideas work as shorter items (100-150 words each)
3. **Links** — which ideas are better served by linking to external sources
4. **Edition flow** — recommended reading order and transitions between sections

## Formatting Rules

- Use British English throughout
- Be specific — "5 underrated AI scheduling tools for solo marketers" beats "AI tools roundup"
- Every idea must have a clear angle, not just a topic
