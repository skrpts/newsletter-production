---
type: workflow
id: newsletter-production
title: Newsletter Production
description: "Newsletter workflow: topic selection, writing, editorial review, and subject line testing"
tags: [Production, Content, Review, Writing]
connections:
  - target: content-ideation
    type: uses
  - target: newsletter-writer
    type: uses
  - target: editorial-review
    type: uses
  - target: email-subject-line-generator
    type: uses
  - target: llm-service
    type: runs_on
  - target: content-briefing
    type: references
  - target: headline-writing
    type: uses
  - target: newsletter-html-template
    type: uses
metadata:
  estimated_duration: "10-20 minutes"
  trigger: manual
---

## Overview

This workflow produces a complete newsletter edition from topic selection through to a send-ready email with tested subject lines. It combines ideation, writing, editorial review, and subject line generation into a repeatable production process.

## Pipeline Stages

### Stage 1: Topic Selection

**Input:** Audience profile, recent content, upcoming announcements, industry news

Invoke the **content-ideation** skill to generate topic ideas for the newsletter edition. Select the main feature topic and 2-3 quick read items from the ranked list.

**Output:** Selected topics with angles for the edition.

### Stage 2: Newsletter Writing

**Input:** Selected topics from Stage 1, audience details, brand guidelines

Invoke the **newsletter-writer** prompt to compose the full edition: opening hook, main feature, quick reads, curated links, and sign-off.

**Output:** Complete newsletter draft.

### Stage 3: Editorial Review

**Input:** Newsletter draft from Stage 2

Invoke the **editorial-review** skill to check grammar, style, and tone consistency. Apply corrections to produce a clean final draft.

**Gate:** All errors resolved before proceeding.

**Output:** Editorially reviewed newsletter.

### Stage 4: Subject Line Testing

**Input:** Finalised newsletter content summary

Invoke the **email-subject-line-generator** prompt to produce 10 subject line options across direct, curiosity, and personal categories. Select 2-3 for A/B testing.

**Output:** Subject line options ready for A/B test configuration.

## Error Handling

- If ideation produces insufficient topics, supplement with curated external links
- If the newsletter exceeds 1,000 words, trim quick reads before cutting from the main feature
- If subject lines exceed character limits, regenerate with stricter constraints

## Inputs

| Name | Required | Description | Example |
|------|----------|-------------|---------|
| `{{input.audience_profile}}` | Yes | Audience profile | `Paste the relevant brief, notes, source material, or dataset here.` |
| `{{input.recent_content}}` | Yes | recent content | `Paste the relevant brief, notes, source material, or dataset here.` |
| `{{input.upcoming_announcements}}` | Yes | upcoming announcements | `Paste the relevant brief, notes, source material, or dataset here.` |
| `{{input.industry_news}}` | No | industry news | `Paste the relevant brief, notes, source material, or dataset here.` |

## Outputs

| Name | Description |
|------|-------------|
| Selected topics | Selected topics with angles for the edition |
| Complete newsletter draft | Complete newsletter draft |
| Editorially reviewed newsletter | Editorially reviewed newsletter |
| Subject line options ready for A/B test configuration | Subject line options ready for A/B test configuration |

## Setup

Before running this workflow:

1. No external services required — paste your content directly and provide any supporting context as inputs or source nodes.
2. Review the included documents, assets, or source nodes and customise them to match your team, brand, or domain conventions where needed.
3. No specific AI provider or API key is required beyond your configured skrptiq LLM provider.

## Provider Notes

- Most stages work with any capable model; stronger models usually improve synthesis, judgement, and writing quality.
- Extraction, classification, and formatting steps generally run well on smaller or faster models.
- Because there are no vendor-specific integrations here, provider choice is mostly a trade-off between speed, quality, and cost.

## Example Input

To test this workflow immediately after import:

```
Audience Profile: "Paste the relevant brief, notes, source material, or dataset here."
Recent Content: "Paste the relevant brief, notes, source material, or dataset here."
Upcoming Announcements: "Paste the relevant brief, notes, source material, or dataset here."
Industry News: "Paste the relevant brief, notes, source material, or dataset here."
```

