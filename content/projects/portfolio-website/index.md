---
title: "Personal Portfolio Website"
date: 2026-4-01
summary: "Built and deployed a personal portfolio using Hugo + HugoBlox, with automated CI/CD via GitHub Actions — learning Linux, YAML, and static site generation along the way."
tags:
  - Hugo
  - GitHub Actions
  - Linux
  - DevOps
  - Web Development
tech_stack:
  - Hugo
  - HugoBlox
  - GitHub Actions
  - GitHub Pages
  - YAML
  - Markdown
  - Arch Linux
links:
  - type: github
    url: https://github.com/AD25aderram
    label: Code
  - type: website
    url: https://lnkd.in/d8UCWENZ
    label: Live Portfolio
featured: true
status: "In Progress"
role: "Solo Developer"
duration: "Ongoing"
team_size: 1
highlights:
  - "Automated deployment pipeline with GitHub Actions triggered on every push"
  - "First hands-on experience with YAML configuration and static site generators"
  - "Built and deployed entirely on Arch Linux"
  - "Configured HugoBlox themes and layouts using Markdown front matter"
---

A personal portfolio site built from scratch — and a hands-on introduction to the modern developer workflow, from static site generation to automated deployment.

## Overview

The goal was simple: have a live portfolio to showcase projects. The outcome was something more valuable — a practical understanding of how modern deployment pipelines actually work, gained by building one myself.

## Approach

The stack centres on **Hugo** as the static site generator, with **HugoBlox** for theming and layout configuration. Content is written in Markdown with YAML front matter, and every push to the main branch triggers an automated deployment via **GitHub Actions** to **GitHub Pages**.

Key learning areas:

- **YAML** — understanding the syntax, structure, and role of `.yml` files in configuring GitHub Actions workflows
- **Markdown customisation** — using front matter to configure pages, projects, and metadata within a static site generator
- **GitHub Actions** — writing and reading CI/CD workflows that automate build and deploy steps
- **Linux environment** — setting up and managing the entire development workflow on Arch Linux for the first time

## Architecture

```
[Push to main] → [GitHub Actions Trigger]
                        ↓
                 [Hugo Build Step]
                        ↓
               [Deploy to GitHub Pages]
```

*Every commit kicks off the full build-and-deploy cycle automatically — no manual steps.*

## Tech Stack

- **Static Site Generator**: Hugo + HugoBlox
- **Deployment**: GitHub Pages
- **Automation**: GitHub Actions
- **Configuration**: YAML, Markdown
- **Environment**: Arch Linux

## Key Takeaways

Sometimes the side-quests are the real learning. Setting up this portfolio introduced version-controlled deployments, declarative configuration, and Linux-native development workflows — all in the context of a project that was genuinely mine to own end to end.
