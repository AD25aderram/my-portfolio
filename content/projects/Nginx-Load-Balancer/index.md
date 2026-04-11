---
title: "Nginx Load Balancer & Reverse Proxy"
date: 2026-04-10
summary: "Built and deployed a multi-container load balancing setup using Nginx, Node.js, and Docker Compose — with SSL termination, health checks, and a live monitoring dashboard."
tags:
  - Nginx
  - Docker
  - Node.js
  - DevOps
  - backend
tech_stack:
  - Nginx
  - Node.js
  - Express
  - Docker
  - Docker Compose
  - SSL/TLS
links:
  - type: github
    url: https://github.com/AD25aderram/nginx-servers
    label: Code
featured: true
status: "Complete"
role: "Solo Developer"
duration: "2 days"
team_size: 1
highlights:
  - "Round-robin load balancing across 3 independent Node.js containers"
  - "SSL/TLS termination at the Nginx layer with self-signed certificates"
  - "Docker health checks on every upstream node with automatic failure detection"
  - "Live monitoring dashboard showing the active serving instance and real-time health check logs"
  - "Server-side HTML injection to identify which container handled each request"
---

A hands-on deep-dive into how production traffic actually gets distributed — built from scratch using Nginx as a reverse proxy in front of three Dockerized Node.js app instances.

## Overview

The goal was to understand load balancing not just in theory but by building and operating it. The result is a fully containerized system where Nginx round-robins incoming HTTPS requests across three identical Node.js instances, each running in its own Docker container — with health checks, SSL termination, and a live dashboard that makes the load balancing visible in real time.

## Approach

Each app instance is a lightweight Express server, containerized with Docker and orchestrated via Docker Compose. Nginx sits in front of all three, handling SSL termination and distributing requests using round-robin by default.

Key areas explored:

- **Reverse proxying** — configuring Nginx to forward requests to upstream containers by service name over Docker's internal network
- **Load balancing algorithms** — round-robin as the default, with awareness of alternatives like `least_conn` and `ip_hash`
- **SSL/TLS** — terminating HTTPS at the Nginx layer so upstream apps only deal with plain HTTP internally
- **Docker health checks** — using `wget` to probe each container's `/health` endpoint, with configurable interval, timeout, retries, and start period
- **Container networking** — understanding the difference between host-mapped ports and internal container ports, and why health checks use port `3000` not `3001/3002/3003`
- **Server-side templating** — injecting the `APP_NAME` environment variable into HTML at request time so the dashboard shows which instance is serving

## Architecture

```
[Client / Browser]
       ↓
  [Nginx :443]  ← SSL termination + round-robin
  /     |     \
App1  App2  App3   ← Node.js containers on internal port 3000
:3001 :3002 :3003  ← host-mapped for direct debug access
```

*Each reload through Nginx cycles to the next upstream instance — visible live on the dashboard.*

## Health Check Setup

Every container runs a health check via Docker Compose:

```yaml
healthcheck:
  test: ["CMD", "wget", "-qO-", "http://localhost:3000/health"]
  interval: 30s
  timeout: 5s
  retries: 3
  start_period: 10s
```

The `/health` endpoint on each app logs every probe hit in memory, which the frontend fetches every 15 seconds via `/api/info` to populate the live request log.

## Tech Stack

- **Reverse Proxy**: Nginx 1.28
- **App Runtime**: Node.js 20 (Alpine)
- **Framework**: Express
- **Containerization**: Docker + Docker Compose
- **Security**: SSL/TLS with certificate termination at Nginx
- **OS**: Windows + Docker Desktop

## Key Takeaways

Building this made abstract networking concepts concrete. Understanding why a health check uses port `3000` instead of `3001`, why `__APP_NAME__` needs server-side injection rather than client-side JS, and why a self-signed cert behaves inconsistently across round-robin rotations — these are the kinds of details that only surface when you actually operate the system yourself.
