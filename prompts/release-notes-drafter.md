---
type: prompt
id: release-notes-drafter
title: Release Notes Drafter
description: "Task prompt for drafting user-facing release notes from commits and PRs"
tags: [Production, Strategy, Automation]
connections:
  - target: code-review
    type: derived_from
  - target: markdown-formatting
    type: derived_from
---

## Purpose

Converts raw commit messages and pull request descriptions into polished, user-facing release notes grouped by category.

## Prompt

Given the analysed changes from the code review stage and the raw commit data, draft user-facing release notes grouped by: features, fixes, and improvements.

### Inputs

- **Code review analysis:** {{steps.code-review.output}}
- **Raw commit log:** {{input.commit_log}}
