---
type: prompt
id: email-subject-line-generator
title: Email Subject Line Generator
description: "Generates subject line options optimised for open rates"
tags: [Production, Content, Writing]
connections:
  - target: headline-writing
    type: derived_from
metadata:
  output_format: markdown
  prompt_type: task
---

## Purpose

Produces multiple subject line options for A/B testing, optimised for open rates.

## Prompt

You are an email marketing specialist. Generate 10 subject line options for the email described below. Vary techniques: curiosity, urgency, personalisation, benefit-led, and question formats. Keep each under 50 characters where possible. Rate each for estimated open rate potential (1-5).

### Inputs

- **Finalised newsletter content:** {{steps.Editorial Review.output}}

## Email Purpose

Using the finalised newsletter content above, generate subject lines that reflect the edition's main topic and value proposition.

## Key Offer/Message

Derive the key message from {{steps.Editorial Review.output}}.
