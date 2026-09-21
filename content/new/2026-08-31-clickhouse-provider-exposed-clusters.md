---
title: "ClickHouse provider now exposes cluster topology through the OpenEverest API"
date: 2026-08-31T18:12:35Z
draft: false
topics:
 - clickhouse
 - api
 - releases
link: https://github.com/openeverest/provider-altinity-clickhouse/releases/tag/v0.1.1
summary: The Altinity ClickHouse provider now exposes cluster topology and connection details through the OpenEverest API for easier integration and monitoring.
---

The Altinity ClickHouse provider now exposes cluster topology and connection details through the OpenEverest API, making it easier to integrate ClickHouse instances with external tools and monitoring systems.

Previously, cluster connection endpoints and topology information were not surfaced through the provider's API contract, so external consumers had to discover them through Kubernetes directly. Now the provider publishes cluster endpoints, shard topology, and replica counts in the standard OpenEverest instance status, accessible through the API or UI.

This enables third-party integrations, custom dashboards, and automated connection string generation without needing cluster-level Kubernetes access.

Upgrade the Altinity ClickHouse provider to version 0.1.1 via Helm to use the exposed cluster API.
