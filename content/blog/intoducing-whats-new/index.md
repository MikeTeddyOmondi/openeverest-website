---
title: "Introducing the What's New page"
date: 2026-09-21T09:00:00
draft: false
image:
    url: blog-whats-new-cover.jpg
authors:
  - spron-in
tags:
  - blog
  - release
  - providers
  - plugins
  - ai
summary: "A single feed for everything shipping across OpenEverest — the core, providers, and plugins. Here is why we built the What's New page and how an AI-powered pipeline keeps it up to date."
---

With the modular architecture of OpenEverest v2 we ended up with a good-to-have problem: new providers and plugins, each with their own release cadence. We needed a way to tell users that new releases are out — not just for the core product, but for all of these components too.

<div class="not-prose my-8 rounded-2xl border border-[#e5e7eb] bg-gradient-to-br from-[#f7f9ff] to-[#eef2ff] p-6 sm:p-8">
  <p class="text-sm font-semibold uppercase tracking-wide text-[#7790DE]">Try it now</p>
  <h3 class="mt-1 text-2xl font-bold text-[#161641]">See everything we just shipped</h3>
  <p class="mt-2 max-w-2xl text-[#3f3f5a]">The What's New page is a single, filterable feed of every user-facing update across OpenEverest, its providers, and its plugins. Take a look before you read on.</p>
  <div class="mt-5 flex flex-wrap gap-4">
    <a href="/new" class="inline-flex items-center justify-center px-6 py-3 rounded-full font-semibold text-white bg-[#161641] hover:bg-[#7790DE] transition-colors">Explore What's New &rarr;</a>
    <a href="/new/index.xml" class="inline-flex items-center justify-center px-6 py-3 rounded-full font-semibold text-[#161641] border-2 border-[#161641] hover:bg-[#161641] hover:text-white transition-colors">Subscribe via RSS</a>
  </div>
</div>

We first tried to solve this with a blog post — [OpenEverest Pulse: August 2026](https://openeverest.io/blog/pulse-august-2026/). The problem with that approach is that it does not scale. With more than 15 plugins and providers today it is already easy to miss an interesting feature or update. What happens when there are hundreds?

That is why we introduced the [What's New](https://openeverest.io/new) page. To be frank, we borrowed the idea from [aws.amazon.com/new](https://aws.amazon.com/new/): concise feature updates that cover the breadth of the product lines, all in one place, with filters and an RSS feed to subscribe to.

## Under the hood

The interesting part is how these pages are built. Manually watching the releases of the core, every provider, and every plugin does not scale either. Good thing we live in the age of AI.

We built a skill that our OpenClaw bot runs every day. It scans for new releases of OpenEverest and of every extension listed in [the Hub](https://github.com/openeverest/hub), then turns each user-facing change into its own announcement. It works as a three-stage pipeline where two deterministic scripts bookend a single AI step:

1. **Fetch.** A lightweight script queries GitHub for releases published that day — the core repo plus every extension in the Hub index — and writes a compact manifest.
2. **Decide and write.** The LLM reads the release notes and splits them into individual customer-facing features, writing one concise, AWS-style page per feature. This is where judgement matters: dependency bumps, refactors, and CI chores are skipped, and only user-facing changes make the cut.
3. **Open the PRs.** Another script stages the pages and opens one pull request per page, so each announcement can be reviewed and merged independently.

Large Language Models are used only where judgement is needed — to write the announcement and to dig deeper when a release is thin on detail. When an issue or pull request referenced in a release does not explain the change well enough, OpenClaw reads the code itself and decides whether it is worth announcing and how to describe it.

Once the pages are ready, the PRs are opened for review. Maintainers review, edit where needed, and merge — nothing is auto-published.

And of course there are filters on the page and an RSS feed to subscribe to changes.

We would love to hear what you think and how this can be improved.

<div class="not-prose flex flex-wrap gap-4 my-8">
  <a href="/new" class="inline-flex items-center justify-center px-6 py-3 rounded-full font-semibold text-white bg-[#161641] hover:bg-[#7790DE] transition-colors">See What's New &rarr;</a>
  <a href="/community/" class="inline-flex items-center justify-center px-6 py-3 rounded-full font-semibold text-[#161641] border-2 border-[#161641] hover:bg-[#161641] hover:text-white transition-colors">Join the community</a>
</div>