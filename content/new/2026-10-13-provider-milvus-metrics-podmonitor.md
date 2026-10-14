---
title: "provider-milvus now exposes Milvus metrics through a Prometheus PodMonitor"
date: 2026-10-13T15:02:14Z
draft: false
topics:
 - milvus
 - openeverest
 - monitoring
 - releases
link: https://github.com/openeverest/provider-milvus/releases/tag/v0.2.0
summary: provider-milvus 0.2.0 scrapes Milvus metrics via a Prometheus PodMonitor, so clusters are observable out of the box.
---

provider-milvus 0.2.0 now scrapes Milvus metrics with a Prometheus PodMonitor, making Milvus clusters deployed through OpenEverest observable out of the box.

Previously, setting up metrics collection for Milvus required manual scrape configuration. The bundled PodMonitor lets existing Prometheus setups discover and collect Milvus metrics automatically.

To learn more, visit the [provider-milvus release notes](https://github.com/openeverest/provider-milvus/releases/tag/v0.2.0).
