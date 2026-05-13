---
type: skill
id: newsletter-writing
title: Newsletter Writing
description: "Composes a complete newsletter edition from curated topics: opening hook, main feature, quick reads, and sign-off"
tags: [Production, Content, Writing]
connections:
  - target: llm-service
    type: runs_on
  - target: brand-voice-guide
    type: references
  - target: editorial-style-guide
    type: references
metadata:
  complexity: high
  avg_tokens: 3000
---

## Capability

Takes the selected topics from the ideation step and composes a full newsletter edition. Produces a complete draft with opening hook, main feature section, quick-read items, curated links, and a sign-off with call to action.

## What It Does

1. **Opening hook** — writes an engaging opening that connects the edition's theme to the reader's interests
2. **Main feature** — develops the primary topic into a substantive section (300-500 words) with insights, examples, or analysis
3. **Quick reads** — writes 2-3 shorter items (100-150 words each) from the remaining topics
4. **Curated links** — assembles any external references or further reading
5. **Sign-off** — closes with a call to action and personal touch

## Output

Complete newsletter draft in markdown, ready for polish and subject line generation.
