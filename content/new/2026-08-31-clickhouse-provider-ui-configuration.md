---
title: "ClickHouse provider adds UI-based engine parameter tuning"
date: 2026-08-31T18:12:35Z
draft: false
topics:
 - clickhouse
 - ui
 - configuration
 - releases
link: https://github.com/openeverest/provider-altinity-clickhouse/releases/tag/v0.1.1
summary: The Altinity ClickHouse provider now exposes engine configuration parameters in the OpenEverest UI, letting you fine-tune settings at creation and edit time.
---

The Altinity ClickHouse provider now exposes engine configuration parameters in the OpenEverest UI, letting you fine-tune settings at creation and edit time.

Previously, ClickHouse engine settings were hard-coded or had to be managed outside OpenEverest. Now the provider surfaces tunable parameters through the standard OpenEverest instance wizard, so you can adjust memory limits, query settings, and other engine options directly without touching Kubernetes manifests.

The parameters are validated against the provider's schema and applied during instance provisioning or updates, so misconfigurations are caught early.

Upgrade the Altinity ClickHouse provider to version 0.1.1 via Helm to use the new configuration support.
