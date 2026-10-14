---
title: "provider-milvus can now back up and restore Milvus, with scheduled backups and retention"
date: 2026-10-13T15:02:14Z
draft: false
topics:
 - milvus
 - openeverest
 - backups
 - releases
link: https://github.com/openeverest/provider-milvus/releases/tag/v0.2.0
summary: provider-milvus 0.2.0 adds backup and restore for Milvus via milvus-backup, plus scheduled backups with retention.
---

provider-milvus 0.2.0 can now back up and restore Milvus deployments using milvus-backup, and supports scheduled backups with configurable retention.

Previously, Milvus clusters managed through OpenEverest had no built-in backup path. With this release, backup schedules and retention policies are handled the same way as for other engines, and the provider also rejects downgrades and rolls upgrades in dependency order to keep restores safe.

To learn more, visit the [provider-milvus release notes](https://github.com/openeverest/provider-milvus/releases/tag/v0.2.0).
