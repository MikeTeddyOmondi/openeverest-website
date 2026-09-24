---
title: "MongoDB Explorer plugin adds cluster overview and clickable cell details"
date: 2026-09-23T18:59:05
draft: false
topics:
 - mongodb
 - mongodb-explorer
 - ui
 - releases
link: https://github.com/openeverest/plugin-mongodb-explorer/releases/tag/v0.1.17
summary: The MongoDB Explorer plugin now surfaces cluster health at a glance and lets users expand truncated table cells inline without leaving the table view.
---

The MongoDB Explorer plugin now surfaces a cluster overview panel and lets you inspect any truncated table cell without switching away from the table view.

The new overview shows replica-set membership, identifies the primary, and surfaces health and uptime for each node. For sharded clusters, it also displays shard topology and balancer state so you can diagnose topology issues at a glance.

Previously, long cell values were truncated with no way to read the full content. You can now click on any truncated cell to open an inline detail modal and see the complete value or nested JSON structure.

These updates are in MongoDB Explorer plugin v0.1.17, available now through Helm or the Extension Hub.
