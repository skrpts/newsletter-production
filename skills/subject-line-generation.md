---
type: skill
id: subject-line-generation
title: Subject Line Generation
description: "Generates email subject line options optimised for open rates, ready for A/B testing"
tags: [Production, Content, Writing]
connections:
  - target: llm-service
    type: runs_on
metadata:
  complexity: low
  avg_tokens: 800
---

## Capability

Takes the polished newsletter and generates multiple subject line options across different approaches: direct benefit, curiosity, personal, urgency, and question formats. Each option is rated for estimated open-rate potential.

## What It Does

1. **Analyses the newsletter** — identifies the main topic, key value proposition, and emotional hooks
2. **Generates options** — produces 8-10 subject lines using varied techniques
3. **Rates each option** — estimates open-rate potential (1-5) based on technique and content fit
4. **Recommends A/B set** — suggests 2-3 options for A/B testing with rationale

## Output

Subject line options with ratings and A/B testing recommendations.
