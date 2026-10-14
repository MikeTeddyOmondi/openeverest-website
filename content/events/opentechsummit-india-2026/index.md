---
title: "Meet OpenEverest at OpenTechSummit India 2026"
date: 2026-10-14
draft: false
summary: "Two talks on running LLMs on Kubernetes and an OpenEverest project table — find us at OpenTechSummit India in Mumbai on Thursday, November 5."
event_name: "OpenTechSummit India 2026"
event_url: "https://eventyay.com/fossasia/ots2026/"
event_date: 2026-11-05
location: "Mumbai, India — Jio World Centre"
date_range: "November 5, 2026"
image:
  url: "/images/resources/opentechsummit-india-2026.jpg"

# Where to find us
schedule:
  - label: "Project table"
    value: "Thursday, November 5 · Exhibition area"
  - label: "Talk"
    value: "Prefill, Decode, and Despair — 1:15–1:30 PM IST · Main Stage"
  - label: "Lightning talk"
    value: "What Actually Happens When You Send an LLM Request to Kubernetes? — 4:05–4:10 PM IST · Main Stage"
  - label: "Venue"
    value: "Jio World Centre, G Block, Bandra Kurla Complex (BKC), Mumbai"

# OpenEverest team at the event
representatives:
  - name: "Sergey Pronin"
    role: "OpenEverest Maintainer"
    github: "spron-in"
    avatar: "/authors/spron-in/avatar.png"
    bio: |
      Sergey is a product leader focused on delivering robust open-source solutions.
      He leads the OpenEverest platform and is a passionate advocate for running
      data workloads on Kubernetes.

  - name: "Atharva Mhaske"
    role: "OpenEverest Contributor"
    github: "atharvamhaske"
    avatar: "/authors/atharvamhaske/avatar.png"
    bio: |
      Atharva is a backend engineer and open source contributor to OpenEverest.
      He enjoys digging into how things work under the hood and writing about it.
---

## OpenEverest at OpenTechSummit India

[OpenTechSummit India](https://eventyay.com/fossasia/ots2026/) is a one-day open
technology and community event organized by FOSSASIA as part of Devcon 8 at the
Jio World Centre in Mumbai. OpenEverest is there with two talks on serving LLMs
on Kubernetes and a project table in the exhibition area.

## Our talks

### [Prefill, Decode, and Despair: Disaggregated LLM Serving Made Boring](https://eventyay.com/fossasia/ots2026/talk/CRTVXC/)
**Sergey Pronin** · Thursday, November 5 · 1:15–1:30 PM IST · Main Stage

KServe can serve large language models on Kubernetes — but past "hello world,"
it gets sharp. Disaggregated prefill/decode, four kinds of parallelism,
autoscaling that behaves differently under KEDA versus HPA, and gateway wiring
where one wrong setting silently breaks routing. Sergey shows how OpenEverest's
KServe provider hides all of that behind a single, technology-agnostic Instance
resource: ten lines of YAML for an OpenAI-compatible endpoint, and the real
traps it saves you from along the way.

### [What Actually Happens When You Send an LLM Request to Kubernetes?](https://eventyay.com/fossasia/ots2026/talk/JXPX9P/)
**Atharva Mhaske** · Thursday, November 5 · 4:05–4:10 PM IST · Main Stage

A chat completion is rarely one Pod. It crosses a Service, a gateway, a model
proxy, a serving controller that may scale from zero, and a model server that
streams tokens back — each hop with its own failure mode. Atharva maps that path
end to end, using OpenEverest as a concrete case: an Instance CR declares
intent, a provider creates a KubeAI Model, and status writes the phase and
endpoint back.

## Visit the OpenEverest project table

OpenEverest is an open source project to manage databases, storage, and LLMs on
Kubernetes, governed by the CNCF. Stop by the
[OpenEverest table](https://eventyay.com/fossasia/ots2026/exhibition/645/) to:

- **See how OpenEverest runs LLMs** alongside databases with the same
  Instance-based API.
- **Talk databases on Kubernetes** — providers, plugins, and what it takes to
  build your own DBaaS.
- **Get involved** — learn how to contribute and where newcomers can start.

Bring your questions — and your production war stories.

## Not at OpenTechSummit but want to connect?

- Star the project on [GitHub](https://github.com/openeverest/openeverest)
- Join the conversation on our [community channels](/#community)
- Browse other [upcoming events](/resources/)
