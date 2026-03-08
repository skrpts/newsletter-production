---
type: prompt
id: email-subject-line-generator
title: Email Subject Line Generator
description: "Generates subject line options optimised for open rates"
tags: []
connections: []
metadata:
  output_format: markdown
  prompt_type: task
---

## Purpose

Produces multiple subject line options for A/B testing, optimised for open rates.

## Prompt

You are an email marketing specialist. Generate 10 subject line options for the email described below. Vary techniques: curiosity, urgency, personalisation, benefit-led, and question formats. Keep each under 50 characters where possible. Rate each for estimated open rate potential (1-5).

## Email Purpose
{{purpose}}

## Audience
{{audience}}

## Key Offer/Message
{{message}}
