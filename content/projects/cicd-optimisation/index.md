---
title: "Pipeline Optimisation with Operations Research"
date: 2025-12-01
summary: "Applied PERT/CPM and graph algorithms to model and optimise a banking application's CI/CD pipeline, identifying a critical path of 64 minutes."
tags:
  - Python
  - Algorithms
  - Operations Research
tech_stack:
  - Python
  - PERT/CPM
  - Graph Theory
  - Topological Sort
links:
  - type: github
    url: https://github.com/ad25aderram/RO-projet
    label: Code
  - type: pdf
    url: https://github.com/AD25aderram/RO-projet/blob/main/rapport%20RO%20IAGI-01.pdf
    label: Full Report (PDF)
featured: true
status: "Completed"
role: "Co-Developer"
duration: "1 month"
team_size: 4
highlights:
  - "Critical path identified at 64 minutes minimum deployment time"
  - "Modelled real DevOps pipeline as a scheduling problem"
  - "Concrete resource prioritisation recommendations"
---

An operations research project that treats a real-world DevOps pipeline as a scheduling problem — applying classical OR methods to reduce deployment time for a critical banking application.

## Overview

CI/CD pipelines in high-stakes environments like banking have strict reliability and performance requirements. The challenge was to model the pipeline mathematically and find the minimum possible deployment duration while respecting task dependencies and enabling parallelism where possible.

## Approach

The pipeline was modelled as a **directed acyclic graph (DAG)** where each node is a pipeline stage and edges represent precedence constraints.

Methods applied:

- **Kahn's topological sort** — to establish a valid execution order
- **PERT/CPM** — to compute earliest and latest start dates for each task
- **Critical path analysis** — to identify zero-slack tasks that directly determine total duration
- **Slack analysis** — to find where parallelisation opportunities exist

## Results

- **Critical path: 64 minutes** — the theoretical minimum for a full deployment cycle
- Identified which pipeline stages offered the most optimisation potential
- Produced concrete managerial recommendations for resource prioritisation and risk mitigation

## Architecture diagram

```
[Checkout] → [Build] → [Unit Tests] ─────────────────────────┐
                    ↘                                          ▼
                     [Integration Tests] → [Security Scan] → [Deploy]
                                        ↗
                   [Docker Build] ──────
```

*Stages on the critical path have zero slack — any delay directly increases total deployment time.*

## Tech stack

- **Language**: Python
- **Methods**: PERT/CPM, topological sort (Kahn's algorithm), critical path analysis, graph theory

## Key takeaways

Operations research techniques that seem purely theoretical deliver actionable insights in modern software engineering — especially where reliability and time-to-market are critical. This project changed how I think about pipeline design.
