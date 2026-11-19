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
- LinkedIn: an article on the concept
- X: an article on how it was built ([@KenVanVorhis](https://x.com/KenVanVorhis))

## Build logs

### content-pipeline

- [A blog writer and a LinkedIn publisher that run on a schedule from voice notes](content-pipeline/2026-11-15-blog-and-linkedin-publisher.md) (2026-11-15, shipped)
- [One record per video, and a LinkedIn article written from it](content-pipeline/2026-11-10-video-record-and-linkedin-article.md) (2026-11-10, shipped)

### platform-profiles

- [One brand description pushed to every platform](platform-profiles/2026-11-16-one-brand-description-every-platform.md) (2026-11-16, shipped)
- [A map of every editable field on every profile the company controls](platform-profiles/2026-11-11-a-map-of-every-profile-field.md) (2026-11-11, shipped)
