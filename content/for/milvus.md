---
title: "Milvus"
technology: "Milvus"
summary: "Run Milvus, the open-source vector database, on any Kubernetes cluster. Deploy a single-process standalone instance or a distributed cluster, autoscale query nodes, roll out upgrades without downtime, and back up collections to S3 through a single UI and API, powered by the Milvus Operator."
description: "Self-hosted Milvus vector database on Kubernetes with OpenEverest: standalone or distributed clusters, autoscaling, rolling upgrades, scheduled backups and restore, GPU builds, and bundled or external etcd and S3-compatible storage."
tagline: "A vector database for RAG and semantic search, on your platform."
logo: "/images/for/milvus/logo.png"
weight: 10
draft: false
aliases:
  - "/for/vector-database/"

# Carousel: screenshots are required; add a slide with `youtube:` for an embedded video.
slides:
  - image: "/images/for/milvus/for-milvus-0.png"
    title: "Standalone or Cluster"
    description: "Pick a single-process standalone instance for development, or a distributed cluster with independently sized proxies, query, data, and streaming nodes - and review every setting before you create it."
  - image: "/images/for/milvus/for-milvus-1.png"
    title: "Instance Overview"
    description: "See every component at a glance, copy the host, port, root credentials, or connection URL into pymilvus or any Milvus SDK, and edit sizing in place."
  - image: "/images/for/milvus/for-milvus-2.png"
    title: "Scheduled Backups"
    description: "Back up collections on demand or on a schedule to any S3-compatible storage, with retention, and restore them into the same instance or a new one."
  - image: "/images/for/milvus/for-milvus-3.png"
    title: "Visual Inspector"
    description: "Follow every Milvus pod as a live graph - status, readiness, restarts, and node placement - and stream logs from the coordinator, proxies, or query nodes without leaving the UI."

# Key capabilities. `icon` maps to layouts/partials/feature-icon.html keywords.
capabilities:
  - icon: "database-engines"
    title: "Standalone or Distributed"
    description: "Start with a single-process instance, or run Milvus 2.6 as a cluster with an active-standby coordinator and separately scalable proxies, query, data, and streaming nodes."
  - icon: "scaling"
    title: "Scaling & Autoscaling"
    description: "Scale each component on its own and let proxies, data, and query nodes autoscale on CPU or memory. Scaling in below what a loaded collection's replicas need is refused."
  - icon: "backup"
    title: "Backups & Restore"
    description: "On-demand and scheduled backups to S3-compatible storage with count- or time-based retention, restored into an existing instance or a brand-new one."
  - icon: "config"
    title: "Rolling Upgrades"
    description: "Curated Milvus 2.6 versions, upgraded component by component in the right order. Downgrades are refused, because Milvus migrates its metadata on upgrade."
  - icon: "storage"
    title: "Bundled or External Dependencies"
    description: "Get etcd and object storage bundled and sized for you, with the write-ahead log kept in object storage (Woodpecker) - or point Milvus at your own etcd and S3-compatible bucket."
  - icon: "resources"
    title: "GPUs & Node Pools"
    description: "Switch to GPU builds with one version change, and split query nodes across GPU pools - with their own node selectors, tolerations, and secondary networks."
  - icon: "private-deploy"
    title: "Secure by Default"
    description: "Authentication is always on: OpenEverest generates the root password and the storage credentials, keeps them in Kubernetes Secrets, and applies a new root password when you change it."

# Open-source repositories powering this integration.
repos:
  - label: "provider-milvus"
    url: "https://github.com/openeverest/provider-milvus"
    description: "The OpenEverest provider that integrates Milvus into the platform, built on the Provider SDK."

# Plugins and integrations that extend Milvus on OpenEverest.
ecosystem:
  - title: "Inspector"
    label: "openeverest/plugin-inspector"
    url: "https://github.com/openeverest/plugin-inspector"
    description: "An OpenEverest UI plugin that adds an Inspector tab to instance pages: the pods behind a Milvus instance as a live graph or a table, streamed container logs, and kubectl-style pod details."
  - title: "Prometheus"
    label: "prometheus-operator/prometheus-operator"
    url: "https://github.com/prometheus-operator/prometheus-operator"
    description: "Turn on monitoring and OpenEverest creates a PodMonitor that scrapes every Milvus component, ready for your Prometheus and Grafana dashboards."

# Attribution to the projects that power Milvus on OpenEverest.
powered_by:
  - name: "milvus-io/milvus"
    url: "https://github.com/milvus-io/milvus"
    description: "Milvus is the open-source, cloud-native vector database built for scalable similarity search on billions of vectors."
  - name: "zilliztech/milvus-operator"
    url: "https://github.com/zilliztech/milvus-operator"
    description: "Milvus instances on OpenEverest are powered by the open-source Milvus Operator, which manages Milvus and its dependencies on Kubernetes."
  - name: "zilliztech/milvus-backup"
    url: "https://github.com/zilliztech/milvus-backup"
    description: "Backups and restores run the upstream milvus-backup tool, which copies collections and their index definitions to S3-compatible storage."

# FAQ: rendered as an accordion and emitted as FAQPage structured data for SEO.
faq:
  - question: "Is Milvus free to run on OpenEverest?"
    answer: "Yes. OpenEverest, Milvus, and the Milvus Operator are all open-source with no licensing fees, and everything runs on your own Kubernetes cluster, in the cloud or on-premises."
  - question: "What is a vector database used for?"
    answer: "A vector database stores embeddings - numeric representations of text, images, or audio - and finds the most similar ones fast. It powers retrieval-augmented generation (RAG), semantic and hybrid search, recommendations, and deduplication."
  - question: "How does OpenEverest run Milvus under the hood?"
    answer: "The [provider-milvus](https://github.com/openeverest/provider-milvus) provider translates an OpenEverest `Instance` into a `Milvus` resource for the open-source [Milvus Operator](https://github.com/zilliztech/milvus-operator), which runs Milvus and its etcd and object storage. Read the walkthrough in [Milvus on OpenEverest](/blog/milvus-on-openeverest/)."
  - question: "Standalone or cluster - which should I choose?"
    answer: "Standalone runs Milvus as a single process and is the smallest footprint, ideal for development and small datasets. The cluster topology splits Milvus into proxies, a coordinator, and query, data, and streaming nodes that scale independently, for production and larger collections."
  - question: "Which Milvus versions are supported?"
    answer: "OpenEverest ships curated Milvus 2.6 versions, including GPU builds. Upgrades roll out component by component; downgrades are refused. See the [provider repository](https://github.com/openeverest/provider-milvus) for the current version matrix."
  - question: "Do I need Pulsar or Kafka?"
    answer: "No. New clusters keep the write-ahead log in object storage with Woodpecker, so the only dependencies are etcd and S3-compatible storage. Pulsar is still available if you prefer it."
  - question: "Can I use my own S3 bucket and etcd?"
    answer: "Yes. Instead of the bundled ones, point Milvus at an existing etcd cluster and an S3-compatible bucket, such as Amazon S3 or MinIO. A `rootPath` lets several instances share one bucket or etcd."
  - question: "How do backups and restores work?"
    answer: "Backups use the upstream milvus-backup tool to copy collections and their index definitions to S3-compatible storage, on demand or on a schedule with retention. Restore into the same instance, or start a new instance from a backup - restores need Milvus 2.6.12 or newer."
  - question: "Can Milvus use GPUs on OpenEverest?"
    answer: "Yes. Pick a GPU version to run the GPU build of Milvus, request GPUs per component, and use deployment groups to place query nodes on specific GPU node pools."

# Optional override of the closing call-to-action text.
cta_description: "Deploy OpenEverest on any Kubernetes cluster and run your first Milvus vector database in minutes."

# Trademark attribution, rendered at the bottom of the page.
trademark_note: "Milvus and Zilliz are trademarks of their respective owners. OpenEverest is not affiliated with, endorsed by, or sponsored by these organizations. These names are used for identification purposes only."
---
