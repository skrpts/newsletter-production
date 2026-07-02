---
type: workflow
id: newsletter-production
title: Newsletter Production
description: "Produces a complete newsletter edition: topic ideation, full draft, language polish, and subject line options for A/B testing"
tags: [Production, Content, Writing]
connections:
  - target: content-ideation
    type: uses
  - target: newsletter-writing
    type: uses
  - target: language-polish
    type: uses
  - target: subject-line-generation
    type: uses
  - target: llm-service
    type: runs_on
  - target: brand-voice-guide
    type: references
  - target: editorial-style-guide
    type: references
metadata:
  estimated_duration: "5-10 minutes"
  trigger: manual
output_step: "subject-line-generation"
composite_steps:
  - "content-ideation"
  - "newsletter-writing"
  - "language-polish"
  - "subject-line-generation"
execution:
  - skill: "content-ideation"
    prompt: "generate-ideas"
    step_type: "generation"
    output: { name: "ideas", type: "list" }
  - skill: "newsletter-writing"
    prompt: "write-newsletter"
    step_type: "generation"
    output: { name: "newsletter_draft", type: "text" }
  - skill: "language-polish"
    prompt: "polish-language"
    step_type: "content"
    output: { name: "polished_newsletter", type: "text" }
    context:
      voice_profile: "Neutral professional tone"
      grammar_strictness: "Professional"
  - skill: "subject-line-generation"
    prompt: "generate-subject-lines"
    step_type: "generation"
    output: { name: "subject_lines", type: "list" }
---

## Overview

This workflow produces a complete, send-ready newsletter edition from a topic brief. It handles ideation, writing, editorial polish, and subject line generation in a single pipeline.

## Pipeline

### Step 1: Topic Ideation

**Skill:** content-ideation | **Prompt:** generate-ideas

Generates 5-8 content ideas from your edition brief, then recommends which to use as the main feature, quick reads, and curated links. Produces a structured topic plan with angles, lengths, and reading order.

**Input:** Newsletter topic/theme, audience description, and any specific items to include.

**Output:** Ranked topic plan with main feature, quick reads, and edition flow.

### Step 2: Newsletter Writing

**Skill:** newsletter-writing | **Prompt:** write-newsletter

Composes the full newsletter edition from the topic plan: opening hook, main feature (300-500 words), 2-3 quick reads (100-150 words each), curated links, and sign-off with call to action. Target length: 800-1200 words.

**Output:** Complete newsletter draft in markdown.

### Step 3: Language Polish

**Skill:** language-polish | **Prompt:** polish-language

Surface-level cleanup: spelling, grammar, punctuation, sentence clarity. Does not change the structure, tone, or content — just makes it publication-ready.

**Output:** Polished newsletter draft.

### Step 4: Subject Line Generation

**Skill:** subject-line-generation | **Prompt:** generate-subject-lines

Generates 8-10 subject line options using varied techniques (direct benefit, curiosity, personal, question, number). Rates each for open-rate potential and recommends 2-3 for A/B testing.

**Output:** Subject line options with ratings and A/B testing recommendations.

## Inputs

| Name | Required | Description | Example |
|------|----------|-------------|---------|
| `{{input.newsletter_topic}}` | Yes | The theme or focus for this edition | "AI tools that actually save time" |
| `{{input.audience}}` | Yes | Who subscribes to this newsletter | "Marketing professionals interested in AI" |
| `{{input.edition_notes}}` | No | Specific items, links, or announcements to include | "Include our new case study" |

## Outputs

| Name | Description |
|------|-------------|
| Newsletter draft | Complete, polished newsletter in markdown |
| Subject line options | 8-10 options with ratings and A/B recommendations |

## Setup

No external services required — this workflow runs entirely on your configured LLM provider.

## Provider Notes

- The writing step is the most token-intensive (3,000+ tokens for the full draft)
- The ideation and subject line steps are lightweight
- Works well with any capable model; stronger models produce better prose in the writing step

## Example Input

To test this workflow immediately after import, use **Try with Examples**:

```
Newsletter Topic: "Five practical ways to reduce meeting fatigue in remote teams"
Audience: "Team leads and managers at fully remote companies"
Edition Notes: "Mention our new async standup feature. Link to the Basecamp remote work guide."
```
