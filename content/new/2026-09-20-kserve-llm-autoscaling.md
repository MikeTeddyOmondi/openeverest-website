---
title: "KServe provider now exposes LLM autoscaling with Workload Variant Autoscaler and HPA/KEDA"
date: 2026-09-20T12:10:11Z
draft: false
topics:
 - kserve
 - llm
 - autoscaling
 - releases
link: https://github.com/openeverest/provider-kserve/releases/tag/v0.1.2
summary: The KServe provider now supports automatic scaling of LLM inference workloads via Workload Variant Autoscaler, Horizontal Pod Autoscaler, and KEDA triggers.
---

The KServe provider now supports automatic scaling for LLM inference workloads through Workload Variant Autoscaler (WVA), Horizontal Pod Autoscaler (HPA), and KEDA triggers.

Previously, LLM deployments ran at a fixed replica count regardless of actual traffic, leading to either under-provisioned latency spikes or over-provisioned resource waste.

You can now configure autoscaling rules directly in the KServe provider spec. To learn more, see the [release notes](https://github.com/openeverest/provider-kserve/releases/tag/v0.1.2).
