---
title: "Automatic secure password generation is now available in the Valkey provider"
date: 2026-09-16T13:12:41Z
draft: false
topics:
 - valkey
 - security
 - releases
link: https://github.com/openeverest/provider-valkey/releases/tag/v0.1.6
summary: Automatic secure password generation is now available when creating Valkey instances through OpenEverest.
---

The OpenEverest Valkey provider now automatically generates a strong, random password for the default user at instance creation time, so new instances start with secure credentials instead of hard-coded or blank defaults.

Previously, the default user password was either hard-coded, left empty, or required manual configuration after provisioning — a security risk and an extra operational step. Now the provider generates the password through a Kubernetes Secret at creation, stores it securely, and passes it to the Valkey operator during initialization.

The generated Secret is owned by the instance and follows the same lifecycle, so deleting the instance also cleans up the credential. You can read the password from the Secret for client connections or rotate it through standard Kubernetes Secret management.

Upgrade the Valkey provider to version 0.1.6 via Helm to use automatic secure password generation.
