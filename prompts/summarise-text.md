---
type: prompt
id: summarise-text
title: "Summarise Text"
description: "Condenses long-form text into key points and a concise summary"
tags: [Production, Writing]
connections:
  - target: text-summarisation
    type: derived_from
metadata:
  output_format: markdown
  prompt_type: task
---

## Purpose

Drives the text summarisation skill.

## Prompt

You are a professional summariser. Condense the text below into a clear, concise summary.

### Text to Summarise

{{steps.previous.output}}

### Instructions

Produce two outputs:

**Key Points** (bullet list)
- Extract the 5-7 most important points from the text
- Each point should be one sentence
- Order by importance, not by appearance in the text

**Summary** (paragraph)
- 150-250 words
- Cover the main argument or narrative arc
- Include any critical data points or conclusions
- Preserve the author's key conclusions — do not editoralise

### Rules

- Do not add information not present in the original text
- Do not offer opinions or analysis — summarise only
- Use British English throughout
- If the text contains action items or decisions, list them separately

## Formatting Rules

- Use British English throughout
- Be specific and actionable — no vague recommendations
- Structure output clearly with headings, tables, or lists as appropriate
