---
title: "ClickHouse provider delivers TLS and secure user defaults out of the box"
date: 2026-08-31T18:12:35Z
draft: false
topics:
 - clickhouse
 - security
 - releases
link: https://github.com/openeverest/provider-altinity-clickhouse/releases/tag/v0.1.1
summary: The Altinity ClickHouse provider now enables TLS encryption and sets a secure default user configuration out of the box.
---

The Altinity ClickHouse provider now enables TLS encryption and sets a secure default user configuration out of the box, so new instances start secure rather than requiring manual hardening.

Previously, instances were created with plaintext connections and open default credentials that had to be locked down after provisioning. Now the provider generates a strong default user password at creation time and configures TLS for internal cluster communication automatically.

The default user is still granted limited privileges — only what the operator needs for health checks and reconciliation — so the attack surface is minimized from the first pod.

Upgrade the Altinity ClickHouse provider to version 0.1.1 via Helm to use the new secure defaults.
