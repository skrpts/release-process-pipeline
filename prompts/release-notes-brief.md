---
type: prompt
id: release-notes-brief
title: "Release Notes Brief"
description: "Collects commit log and release context for release notes"
tags: [Production]
inputs:
  commit_log:
    label: "Commit Log"
    description: "Git commit history or changelog for this release"
    example: "Paste git log output here"
    required: true
    type: file
    accept: ".txt,.md"
  version:
    label: "Version"
    description: "Version number"
    example: "v2.3.0"
    required: false
    type: text
  highlights:
    label: "Highlights"
    description: "Features or fixes to emphasise"
    example: "New dashboard, fixed login timeout"
    required: false
    type: text
connections:
  - target: text-summarisation
    type: derived_from
metadata:
  output_format: markdown
  prompt_type: task
---

You are a technical writer producing release notes.

**Version:** {{input.version}}
**Highlights:** {{input.highlights}}

### Commit Log

{{input.commit_log}}

Produce structured release notes: Summary, New Features, Improvements, Bug Fixes, Breaking Changes. Translate developer language into user-facing descriptions. Skip internal refactoring and CI changes.
