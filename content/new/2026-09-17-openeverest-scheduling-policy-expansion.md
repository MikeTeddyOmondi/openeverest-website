---
title: "OpenEverest scheduling now supports tolerations, node selectors, and topology spread constraints"
date: 2026-09-17T10:00:00Z
draft: false
topics:
 - openeverest
 - kubernetes
 - scheduling
 - releases
link: https://openeverest.io/documentation/2.0.0-dev.3/
summary: Instance scheduling in OpenEverest now supports tolerations, node selectors, topology spread constraints, and custom scheduler names alongside affinity rules.
---

Instance scheduling in OpenEverest now supports tolerations, node selectors, topology spread constraints, and custom scheduler names, all grouped under a unified `schedulingPolicy` block.

Previously, `ComponentSpec` only exposed `affinity`, which was never the whole placement story. A component pinned to a tainted node pool needed tolerations, and zone spreading normally requires `topologySpreadConstraints` — both had to be handled outside OpenEverest or not at all.

The new `schedulingPolicy` struct lives in the common API because placement is not instance-specific. You can now set `schedulerName`, `nodeSelector`, `affinity`, `tolerations`, and `topologySpreadConstraints` in one place, and every component that supports scheduling honours the same fields consistently.

This is available in OpenEverest v2.0.0 Developer Preview 3. Existing instances using the old `affinity` field will need to migrate to the new structure before the next preview release.
