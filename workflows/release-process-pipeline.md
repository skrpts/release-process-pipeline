---
type: workflow
id: release-process-pipeline
title: Release Process Pipeline
description: "Drafts user-facing release notes from recent commits and pull requests"
tags: [Production, Strategy, Automation]
connections:
  - target: code-review
    type: uses
  - target: text-summarisation
    type: uses
  - target: llm-service
    type: runs_on
  - target: release-checklist
    type: references
  - target: language-polish
    type: uses
  - target: brief-compliance-check
    type: uses
  - target: format-conversion
    type: uses
execution:
  - skill: "text-summarisation"
  - skill: "format-conversion"
    input_from: "text-summarisation"
  - skill: "code-review"
    input_from: "format-conversion"
  - skill: "language-polish"
    input_from: "format-conversion"
  - skill: "brief-compliance-check"
    input_from: "format-conversion"
---

## Overview

This workflow processes recent commits and pull request descriptions to produce polished, user-facing release notes.

## Pipeline Stages

### Stage 1: Analyse Changes

Invoke the **code-review** skill to understand the nature and impact of recent code changes from commit diffs and PR descriptions.

### Stage 2: Draft Release Notes

Invoke the **release-notes-drafter** prompt to categorise changes into features, fixes, and improvements, and draft user-friendly descriptions.

### Stage 3: Format Output

Invoke the **markdown-formatting** skill to produce clean, well-structured release notes ready for publication.

## Output

Formatted release notes containing:

- New features with descriptions
- Bug fixes with brief explanations
- Improvements and performance enhancements
- Breaking changes (if any)

## Inputs

| Name | Required | Description | Example |
|------|----------|-------------|---------|
| `{{input.commit_log}}` | Yes | Commit log or PR descriptions covering the release | Output from `git log --oneline v1.2.0..HEAD` or a list of PR titles and descriptions |

## Outputs

| Name | Description |
|------|-------------|
| Release notes | Formatted markdown release notes categorised into features, fixes, and improvements |

## Setup

Before running this workflow:

1. **Gather your changes** — run `git log` or collect PR descriptions for the changes included in this release. Paste the output directly.

No specific AI provider or API key is required beyond your configured skrptiq LLM provider.

## Provider Notes

- Benefits from a model that understands code changes and technical terminology
- Larger models tend to produce better user-facing descriptions from technical commit messages

## Example Input

To test this workflow immediately after import:

```
Commit log:
a1b2c3d Add dark mode toggle to settings page
d4e5f6a Fix crash when uploading files over 50MB
b7c8d9e Improve search indexing performance by 40%
e0f1a2b Update dependencies to patch CVE-2025-1234
c3d4e5f BREAKING: Remove deprecated /api/v1/users endpoint
```
