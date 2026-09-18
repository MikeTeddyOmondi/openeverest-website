---
title: "MongoDB provider now supports backup imports via updated Backup CRD"
date: 2026-09-17T17:39:28Z
draft: false
topics:
 - mongodb
 - backups
 - import
 - releases
link: https://github.com/openeverest/provider-percona-server-mongodb/releases/tag/v0.3.0
summary: The Percona Server for MongoDB provider now supports importing existing backups through an updated Backup CRD.
---

The Percona Server for MongoDB provider now supports importing existing backups through an updated Backup CRD, enabling smoother migration and disaster-recovery workflows.

Previously, backup imports were not fully supported by the MongoDB provider's API contract, limiting your ability to bring in externally created backups. The updated Backup CRD aligns the provider with OpenEverest's import requirements so backup restores from external sources work end-to-end.

Upgrade the provider to version 0.3.0 via Helm to use the new import support.
