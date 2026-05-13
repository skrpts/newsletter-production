---
type: prompt
id: write-newsletter
title: Write Newsletter
description: "Composes a complete newsletter edition from the curated topic ideas"
tags: [Production, Content, Writing]
connections:
  - target: newsletter-writing
    type: derived_from
metadata:
  output_format: markdown
  prompt_type: generation
---

## Purpose

Second step in the newsletter pipeline. Takes the curated topic ideas and writes the full newsletter edition.

## Prompt

You are a newsletter writer. Compose a complete newsletter edition using the topic plan below. Write in a conversational yet professional tone that matches the audience.

### Topic Plan

{{steps.Content Ideation.output}}

### Instructions

Write the newsletter edition with these sections:

### 1. Opening Hook (50-100 words)

Start with a relatable observation, question, or mini-story that connects the edition's theme to the reader's world. No "welcome to this week's edition" — get straight to the value.

### 2. Main Feature (300-500 words)

Develop the recommended main feature topic. Include:
- A clear thesis or takeaway
- Concrete examples, data, or evidence
- Practical implications for the reader
- A transition to the quick reads

### 3. Quick Reads (100-150 words each)

Write 2-3 shorter items from the recommended quick-read topics. Each should:
- Have a clear subheading
- Deliver one key insight
- Be self-contained (readable without the main feature)

### 4. Curated Links (if applicable)

List any external resources with a one-line description of why they're worth reading.

### 5. Sign-Off (50-75 words)

Close with:
- A call to action (reply, share, try something)
- A personal touch (question for readers, preview of next edition)

## Formatting Rules

- Use British English throughout
- Use markdown formatting: `##` for section headings, `**bold**` for emphasis, `>` for pull quotes
- Keep paragraphs to 3 sentences maximum
- No jargon without explanation
- The total edition should be 800-1200 words
