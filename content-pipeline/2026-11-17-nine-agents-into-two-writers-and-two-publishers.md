---
id: BL-20261117-08
date: 2026-11-17
entity: [Ken Van Vorhis, Prometheus Exotics]
system: content-pipeline
status: shipped
builds_on: [BL-20261115-01, BL-20261116-05]
video: https://www.youtube.com/watch?v=NHwgW9GvoXk
articles:
  linkedin: https://www.linkedin.com/pulse/how-keep-ai-agents-manageable-exotic-car-rental-ken-van-vorhis-u4zwc/
  x:
---

# Nine publishing agents collapsed into four: one writer per brand, one publisher per platform

## What was built

A four-task content engine, built on November 17, 2026. It replaces 9 separate agents that each wrote and posted one lane, which meant one brand on one platform.

- **Two writers.** One for the company and one for my personal brand. Each writes every piece for its brand ahead of time, checks it, saves it and adds it to a queue. Both run in the cloud on a schedule.
- **Two publishers.** One for LinkedIn and one for X. Each only posts what is queued, to whichever account a piece is tagged for, and it changes no words.
- **Two queues.** One file per platform, with one row per finished piece. The top of the file holds a daily cap for each account and the number of pieces the writers keep written ahead.
- **The standards.** Each old agent's instructions were split into a writing half and a posting half, and both halves were kept as the standard for that lane.

## How the pieces connect

1. Each writer reads its sources. The company writer works from voice notes and the live blog posts, and the personal brand writer works from video transcripts.
2. A writer writes the LinkedIn articles and the X pieces for a source in one pass. The company writer also writes the blog post.
3. The writer runs every check at write time. A piece that fails is not queued.
4. The writer saves the piece and adds a row to that platform's queue with the account, the lane and a status.
5. Each publisher reads its queue. Per account it takes new videos first, then company questions, then older videos, and inside a lane it goes top to bottom.
6. Before sending, a publisher confirms the piece has not gone out already, that its source is still live, and that the page it is about to publish matches the file.
7. The LinkedIn publisher runs on a laptop through a signed-in browser. The X publisher runs in the cloud through the official X API.
8. A piece that links another piece waits for it. An X Article that links its LinkedIn article is held until that article is live, and then the address is filled in.

## Steps

1. List every agent with what it wrote and where it posted.
2. Split each agent's instructions into a writing half and a posting half, and keep both as the standard for that lane.
3. Write two queue files with the caps and the buffer sizes at the top.
4. Write four short briefs that point at the standards.
5. Create the four scheduled tasks.
6. Mark every old set of instructions so an old agent that still fires stops and does nothing.
7. Set up the X publisher so it needs no laptop.
8. The same evening, move the company's renter-facing blog into the company writer. It takes the next row from an existing topic list twice a day under the same rules the old blog agent used.

## What broke and how it got fixed

- **Old agents that would not pause.** The working session was not allowed to pause most of the old agents. Fix: each one's own instructions now tell it to stop and do nothing if it still fires. I deleted them by hand the next day.
- **A link to an article that did not exist yet.** An X Article links its LinkedIn article, and that article has no address when both are written together. Fix: the writer leaves a marker in the text and the X publisher fills it in before it sends.
- **A writer the public repo refused.** On the first unattended day, the personal brand writer could not push to this repo, because its task had been created before the repo was attached to it. Two X Articles were written and held. Fix: the task was created again from a session that had both repos, and the first run after that pushed.
- **A sleeping laptop.** The laptop was asleep for one LinkedIn run on the first day. The queued pieces waited for the next run.

## The design choice worth copying

Give a surface its own publisher when publishing needs a different privilege, machine or pace than writing. LinkedIn needs a laptop with a signed-in browser. X needs API keys. Both have daily caps that differ from how fast a writer writes. So each one has a publisher, and the writers never hold those privileges.

The company blog has no separate publisher. The company writer already holds the connection to the website and publishes at the pace it writes.

The queue is a plain file. Moving a row changes the order, setting a row to held stops a piece, and changing one number changes the pace.

## Not proven yet

The four tasks ran on their own for the first time on November 18, 2026, so they have days behind them and not weeks. The X publisher can't yet write an article's X address back into this repo, so that field is empty on recent entries. A third publisher for another platform is a plan and isn't built.

## Tools

Claude scheduled tasks, GitHub, the X API, LinkedIn, Webflow, YouTube.
