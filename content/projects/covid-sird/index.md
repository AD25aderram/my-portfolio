---
title: "COVID-19 Epidemic Modelling (SIRD)"
date: 2025-03-01
summary: "Numerical simulation of COVID-19 propagation in Morocco using the SIRD differential equation model, with parameter analysis and curve visualisation."
tags:
  - Python
  - Applied Mathematics
  - Data Visualisation
  - Modelling
tech_stack:
  - Python
  - NumPy
  - SciPy
  - Matplotlib
links:
  - type: github
    url: https://github.com/ad25aderram/algorithme-avance
    label: Code
  - type: pdf
    url: https://github.com/AD25aderram/analyse-num/blob/main/B10-Rapport%20AN.pdf
    label: Full Report (PDF)
featured: false
status: "Completed"
role: "Co-Developer"
duration: "2 months"
team_size: 2
highlights:
  - "Numerically solved SIRD ODE system for Moroccan COVID-19 data"
  - "Parameter sensitivity analysis on transmission rate β"
  - "Visualised S, I, R, D population curves over time"
---

An epidemiological modelling project simulating the spread of COVID-19 in Morocco using the SIRD compartmental model — applied mathematics meeting a real-world public health problem.

## The model

The **SIRD model** divides a population into four compartments evolving over time:

| Compartment | Meaning |
|---|---|
| **S** | Susceptible — not yet infected |
| **I** | Infected — currently infectious |
| **R** | Recovered |
| **D** | Deceased |

The dynamics are governed by a system of ordinary differential equations:

```
dS/dt = -β·S·I/N
dI/dt =  β·S·I/N - γ·I - μ·I
dR/dt =  γ·I
dD/dt =  μ·I
```

Where β is the transmission rate, γ the recovery rate, and μ the mortality rate.

## My contribution

- Analysed and implemented the SIRD ODE system
- Solved numerically using SciPy to simulate population evolution over time
- Tuned β, γ, and μ parameters against observed Moroccan COVID-19 data
- Visualised S, I, R, D curves and interpreted dynamics — peak infection timing, convergence behaviour, and sensitivity to β changes

## Key finding

A small change in the transmission rate β shifts the infection peak by weeks — a concrete illustration of why epidemic modelling matters for policy decisions, and why early intervention has outsized impact.

## Tech stack

- **Language**: Python
- **Libraries**: NumPy, SciPy (ODE solving), Matplotlib (visualisation)
- **Focus**: Applied mathematics, numerical methods, data visualisation
