---
title: "OpenEverest now creates instances in one click from a preset"
date: 2026-09-17T10:00:00Z
draft: false
topics:
 - openeverest
 - ui
 - instances
 - releases
link: https://openeverest.io/documentation/2.0.0-dev.3/administer/instance_presets.html
summary: OpenEverest now lets you create database instances in a single click by selecting from predefined InstancePresets in the UI.
---

OpenEverest now lets you create database instances in a single click by selecting from predefined InstancePresets in the UI.

Previously, InstancePresets existed only in the API — you had to construct the full request manually or through external automation. Now the creation wizard opens with a preset picker filtered to your chosen provider. Selecting a preset resolves it for your target namespace, pre-fills the form with the right topology, sizing, and storage class, and locks the configuration so nothing wizard-only leaks into the final object. You name the instance and press Create.

Presets can be authored centrally and shipped with a provider, so teams can standardize on approved configurations while still allowing fully custom deployments when needed. Editing a preset before deploying, and presets alongside plugins, are coming in a later phase.

This is available in OpenEverest v2.0.0 Developer Preview 3. To learn more, see the [instance presets documentation](https://openeverest.io/documentation/2.0.0-dev.3/administer/instance_presets.html).
