---
id: BL-20261116-05
date: 2026-11-16
entity: [Ken Van Vorhis, Prometheus Exotics]
system: content-pipeline
status: in progress
builds_on: [BL-20261110-01]
video: https://www.youtube.com/watch?v=yGq98Hntizo
articles:
  linkedin: https://www.linkedin.com/pulse/how-build-exotic-car-rental-company-public-without-hours-van-vorhis-tbzjc/
  x:
---

# Build logs to video topics to articles to a public repo

## What was built

A loop that turns the work I do with AI each day into a video, two articles and a public record. It was built on November 16 and 17, 2026.

- **A build log.** Every working session with AI writes an entry at the point of the build. It covers what was built, how it connects, the steps, what broke and where it's heading. It's private and it holds everything.
- **A nightly task.** A scheduled Claude task runs at midnight in the cloud. It reads the day's entries and the day's commits and turns them into video topics, each with a concept and the sub-concepts inside it.
- **A topic list for ChatGPT.** ChatGPT reads the list when I plan a video. The topics are suggestions, and I can still film my own idea.
- **Two articles per video.** LinkedIn gets the concept. X gets the build log as an X Article, sent through the official X API.
- **This repo.** One file per build log, with the same fields at the top of each one.

## How the pieces connect

1. Working sessions write build entries as the work happens.
2. The nightly task reads them with the day's commits and writes topics for ChatGPT.
3. ChatGPT plans the video from a topic and I film it. The tasks from the earlier log pull the transcript and publish the concept article on LinkedIn.
4. The filmed video is matched back to its topic, and the topic carries the ids of the build entries behind it.
5. For a video with a build behind it, the entry is written into this repo first. Then the X Article is published with links to the video, the repo entry and the LinkedIn article.
6. A video with no build behind it gets one ordinary post on X.

Every build entry and every topic has a permanent id, which is what lets them be joined.

## Steps

### The build log and the topics

1. Settle what each reader needs. ChatGPT gets a thin list, and the article writer gets the thick log.
2. Give every build entry and every topic a permanent id.
3. Make the capture a rule every session follows, because a midnight task starts with no memory of the day.
4. Have the midnight task fill gaps from the commits when a session forgot.
5. Let the video be the gate. Nothing reaches this repo until I've filmed it.

### The split between LinkedIn and X

1. Decide where the build detail goes. The choices were one long article, two LinkedIn articles, or a split by platform.
2. Put the concept on LinkedIn and the build log on X, with this repo as the technical home both link to.

### Publishing to X

1. Read the platform's rules first. X bans browser automation and automated likes, and it allows automated original posts.
2. Open a developer account and set the app's permissions to read and write.
3. Sign each request with the account's keys. A script checks the keys, uploads the cover, creates the Article as a draft and then publishes it.
4. Add a mode for ordinary posts, for the videos that get no Article.

## What broke and how it got fixed

- **A task that couldn't remember.** The first design had the midnight task do the remembering. A scheduled task wakes with no recollection of the day. Fix: capture moved into the working sessions and the task became the distiller.
- **What is public.** The rule for what could be shown went through 3 versions in one conversation. It went from tags on each entry, to built is public and plans are private, to open by default with a short list of things that stay closed.
- **Too many articles.** Two LinkedIn articles per video would have meant 4 a day on a 2-video day. Fix: the split by platform.
- **Publishing through the browser.** The first fallback for X was to publish through Chrome. It was withdrawn because X's developer guidelines ban browser automation. Fix: the official API.
- **Reading a post back.** The first version of the script couldn't sign a read request that carried a query string, so reading a post back failed. Fix: the query pairs are now signed with the rest of the request.
- **A half-failed send.** A draft that was created and then refused at publish could have produced a second draft on the next run. Fix: the draft's id is recorded and the draft is held for me.

## The design choice worth copying

Capture at the point of the build and distill later. The session that did the work writes the entry, because it's the only one that knows what happened. The nightly task only sorts and groups.

Then let the video be the gate for what goes public. The decision to talk about something is made once, by filming it.

## Not proven yet

Whether the X Articles and this repo reach a more technical audience hasn't been measured. The topic list is new, and the first videos planned from it were filmed on November 18, 2026. An app that replays this repo over time is an idea and isn't built.

## Tools

Claude scheduled tasks, ChatGPT, GitHub, the X API, YouTube, LinkedIn.
