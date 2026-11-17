# build-logs

Build logs from Ken Van Vorhis. How I design and build AI systems that run real businesses, starting with an exotic car rental company. The steps, what broke and how the pieces connect.

## What this is

I'm not a developer. I design the systems and I build them with AI. Every time something real gets built, it gets a build log. Each log covers what was built, how it connects to everything else, the steps in order, what broke and how it got fixed.

These aren't tutorials written after the fact. They're the record of work that's running in a real company right now.

## How it's organized

One file per build log. Every log starts with the same fields.

- `id` never changes
- `date` is the day it was built
- `entity` is the business or brand it belongs to
- `system` is the machine it's a part of
- `status` is planned, in progress or shipped
- `builds_on` points to the earlier logs it depends on
- `video` and `articles` link to where I talk about it

A log only shows up here after I've made a video about it.

## Where to follow along

- YouTube: the video for each build
- LinkedIn: one article on the concept, one on how it was built

First logs are coming soon.
