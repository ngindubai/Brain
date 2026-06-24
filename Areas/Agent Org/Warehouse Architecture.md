---
title: Warehouse Architecture
area: Agent Org
tags: [agents, warehouse, postgres, data]
source: https://claude.ai/chat/8ed658bc-9b08-4a45-84bd-3561ee4dc195
updated: 2026-06-24
---

# Warehouse Architecture

The data layer for the humanless companies. Rewritten on 20 June after the first plan was challenged as undersized. Part of [[Agent Org]].

## Why it was resized

The real scale: roughly 266,000 pages across seven sites, 40 blogs a day across ten sites, ten humanless companies with full departments and hundreds of workers. The first design was too small.

## The design

A production Postgres deployment, hosted off the laptop on managed infrastructure (Neon):

- Connection pooling
- Time partitioning
- Read replicas
- Multi-tenancy via a shared schema with row-level security
- pgvector on for embeddings

The principle: simple, boring, non-distributed infrastructure one person can run. Every reporting routine dual-writes here (machine-readable) as well as to Slack (human-readable). The command deck reads the warehouse, not the Slack messages.

Source: chat 8ed658bc.
