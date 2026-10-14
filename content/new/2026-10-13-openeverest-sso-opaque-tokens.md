---
title: "OpenEverest SSO now supports opaque tokens and no longer stalls on login redirects"
date: 2026-10-13T14:54:41Z
draft: false
topics:
 - openeverest
 - sso
 - releases
link: https://github.com/openeverest/openeverest/releases/tag/v1.17.0
summary: Single sign-on in OpenEverest now accepts opaque tokens from identity providers and reliably completes the login redirect.
---

OpenEverest single sign-on now accepts opaque tokens from identity providers, and the long-standing redirect stall that could hang SSO logins is fixed.

Previously, some identity providers that issue opaque reference tokens instead of JWTs could not be used with OpenEverest, and certain logins stalled mid-redirect. Both are resolved in 1.17.0.

To learn more, visit the [release notes](https://github.com/openeverest/openeverest/releases/tag/v1.17.0).
