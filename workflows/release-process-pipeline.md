---
type: workflow
id: release-process-pipeline
title: Release Process Pipeline
description: "Drafts user-facing release notes from recent commits and pull requests"
tags: [Production]
connections:
  - target: code-review
    type: uses
  - target: markdown-formatting
    type: uses
  - target: release-notes-drafter
    type: uses
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
