---
type: document
id: release-checklist
title: Release Checklist
description: "Standard checklist for pre-release and release-day procedures"
tags: [Production, writing:product, communication:status]
connections: []
---

# Release Checklist

## Pre-release

- Run full test suite
- Security scan all dependencies
- Update version numbers
- Review and finalise changelog
- Tag release candidate

## Release Day

- Merge release branch to main
- Create GitHub release with notes
- Deploy to staging and verify
- Deploy to production
- Notify stakeholders
- Monitor error rates for 24 hours
