---
title: "everestctl upgrade now completes cleanly and honors your Helm values"
date: 2026-10-13T14:54:41Z
draft: false
topics:
 - openeverest
 - cli
 - releases
link: https://github.com/openeverest/openeverest/releases/tag/v1.17.0
summary: everestctl upgrade now upgrades the everest-crds release instead of refusing it, and honors --helm.reuse-values and --skip-wizard as expected.
---

`everestctl upgrade` is now significantly more reliable: it upgrades the `everest-crds` Helm release instead of refusing it, so upgrades complete cleanly end to end.

The CLI also honors `--helm.reuse-values` during upgrades, respects `--skip-wizard` in `everestctl namespaces update`, reports the correct operator constraint string on upgrade errors, and rejects invalid subcommands with a clear message.

To learn more, visit the [release notes](https://github.com/openeverest/openeverest/releases/tag/v1.17.0).
