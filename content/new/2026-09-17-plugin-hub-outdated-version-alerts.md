---
title: "Plugin Hub now detects and alerts outdated plugin and provider versions"
date: 2026-09-17T11:21:31Z
draft: false
topics:
 - plugin-hub
 - ui
 - updates
 - releases
link: https://github.com/openeverest/plugin-hub/releases/tag/v0.1.15
summary: The Plugin Hub now automatically detects when installed plugins or providers are out of date and shows update alerts directly in the catalog.
---

The Plugin Hub now automatically detects when installed plugins or providers are out of date and shows clear update alerts directly in the catalog UI.

Previously, you had to manually check whether newer versions were available or rely on external monitoring. Now the Hub compares the installed versions against the latest catalog versions and surfaces an **Update available** badge in the catalog table alongside any component that has a newer release.

When you open the detail drawer for an outdated plugin or provider, a warning banner appears with the exact `helm upgrade` command needed to bring it current. This is available now for all OpenEverest deployments — upgrade the Plugin Hub to version 0.1.15 via Helm or the release tarball.
