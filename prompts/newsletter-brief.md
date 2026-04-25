---
type: prompt
id: newsletter-brief
title: "Newsletter Brief"
description: "Collects newsletter topic, audience, and edition details"
tags: [Production]
inputs:
  newsletter_topic:
    label: "Newsletter Topic"
    description: "The theme or focus for this edition"
    example: "AI tools that actually save time — not just the hype"
    required: true
    type: text
  audience:
    label: "Audience"
    description: "Who subscribes to this newsletter"
    example: "Marketing professionals interested in AI and automation"
    required: true
    type: text
  edition_notes:
    label: "Edition Notes"
    description: "Specific items, links, or announcements to include"
    example: "Include our new case study, mention the upcoming webinar"
    required: false
    type: text
connections:
  - target: content-ideation
    type: derived_from
metadata:
  output_format: markdown
  prompt_type: task
---

You are a newsletter editor. Generate content ideas and structure for this edition.

**Topic:** {{input.newsletter_topic}}
**Audience:** {{input.audience}}
**Notes:** {{input.edition_notes}}

Produce 5-8 content ideas with section title, content type, key angle, estimated length, and source. Recommend structure and sequencing.
