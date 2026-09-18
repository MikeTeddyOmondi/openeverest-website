---
title: "MariaDB provider now supports point-in-time recovery"
date: 2026-09-15T07:07:45Z
draft: false
topics:
 - mariadb
n - backups
 - releases
link: https://github.com/openeverest/provider-mariadb/releases/tag/v0.1.5
summary: The OpenEverest MariaDB provider now supports point-in-time recovery, letting you restore a database to any moment within the backup retention window.
---

The OpenEverest MariaDB provider now supports point-in-time recovery (PITR), letting you restore a MariaDB instance to any moment within your backup retention window.

Previously, restores were limited to full backup snapshots. With PITR, you can recover from accidental data loss, schema changes, or user errors without losing everything written after the last snapshot. The provider manages the backup chain and transaction log retention automatically.

Point-in-time recovery is available now for all MariaDB instances managed through OpenEverest. Upgrade the MariaDB provider to version 0.1.5 via Helm to use the new feature.
