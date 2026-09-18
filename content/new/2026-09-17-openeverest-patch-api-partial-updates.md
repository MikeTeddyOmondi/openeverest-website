---
title: "OpenEverest now supports partial updates with PATCH on Instance and BackupStorage APIs"
date: 2026-09-17T10:00:00Z
draft: false
topics:
 - openeverest
 - api
 - cli
 - releases
link: https://openeverest.io/documentation/2.0.0-dev.3/
summary: The Instance and BackupStorage APIs now accept PATCH requests, letting you update individual fields safely without read-modify-write races.
---

The Instance and BackupStorage APIs now accept PATCH with `application/merge-patch+json`, letting you update individual fields safely without read-modify-write races.

Previously, both APIs only supported GET, PUT, and DELETE. Changing one field meant reading the entire object, modifying it, and writing it back — a lost-update window for every client, and a typed client older than the server could silently erase settings it did not model.

With PATCH, absent members keep their value, `null` removes one, and `metadata.resourceVersion` acts as a precondition that fails with 409 when the object has changed since you read it. The `everestctl instance update` and `everestctl backup-storage update` commands sit on the same endpoints, supporting `--set`, `-f`, and `--dry-run` flags for safe, scriptable changes.

This is available in OpenEverest v2.0.0 Developer Preview 3.
