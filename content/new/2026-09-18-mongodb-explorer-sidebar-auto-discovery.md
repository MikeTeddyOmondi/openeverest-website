---
title: "MongoDB Explorer plugin now auto-discovers your instances in the sidebar"
date: 2026-09-18T07:38:11Z
draft: false
topics:
 - mongodb
 - explorer
 - ui
 - releases
link: https://github.com/openeverest/plugin-mongodb-explorer/releases/tag/v0.1.16
summary: The MongoDB Explorer plugin now automatically discovers and lists your OpenEverest-managed MongoDB instances directly in the sidebar.
---

The MongoDB Explorer plugin now automatically discovers and lists your OpenEverest-managed MongoDB instances directly in the sidebar. Previously, the sidebar showed only a static message directing you to open a cluster manually, and you had to navigate through individual database detail pages to find an instance.

The plugin queries the OpenEverest cluster, namespace, and instance APIs using your existing authentication token, then filters and displays only the MongoDB instances you have access to in a clean table view. Each row shows the instance name, namespace, and Kubernetes cluster, with an **Explore** button that takes you straight to that instance's MongoDB Explorer tab.

The update also adds loading, empty, and error states with retry support, so the experience is reliable even when clusters are still spinning up or temporarily unreachable. To use the new discovery feature, upgrade the MongoDB Explorer plugin to version 0.1.16 via Helm or the release tarball.
