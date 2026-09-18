---
title: "OpenEverest provider upgrades now require explicit approval for disruptive changes"
date: 2026-09-17T10:00:00Z
draft: false
topics:
 - openeverest
 - operations
 - upgrades
 - releases
link: https://github.com/openeverest/openeverest/releases/tag/v2.0.0-dev.3
summary: OpenEverest now gates provider upgrades behind an explicit maintenance approval system, so disruptive changes like rolling restarts require operator consent.
---

OpenEverest now gates provider upgrades behind an explicit maintenance approval system, so disruptive changes like rolling restarts require operator consent instead of happening silently.

Previously, upgrading a provider was an act of faith: the new operator might restart every pod or refuse to manage an instance whose version was dropped from the catalog, and you only found out afterwards. Three layers now prevent that.

**Disruption is authorized, not assumed.** Each instance carries a `spec.maintenance.autoApproveUpTo` tolerance — NonDisruptive, RollingRestart, or Downtime — defaulting to NonDisruptive. Any action exceeding that threshold is held in `status.pendingMaintenance` with a unique approval token. You copy the token into `spec.maintenance.approved` to authorize exactly that occurrence. Stale approvals cannot authorize future actions, and repeatedly failing approved actions trip a circuit breaker so a crash-looping provider cannot keep disrupting a running instance.

**Deprecated versions surface before the upgrade.** A read-only `ComponentVersionDeprecated` condition names affected versions and the provider release that removes them, giving you advance warning without blocking anything.

**The upgrade is preflighted.** A Helm pre-upgrade hook checks the target catalog before the upgrade proceeds, blocking upgrades that would strand an instance on a removed version.

This is available in OpenEverest v2.0.0 Developer Preview 3.
