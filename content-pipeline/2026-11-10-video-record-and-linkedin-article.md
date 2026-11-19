---
id: BL-20261110-01
date: 2026-11-10
entity: [Ken Van Vorhis, Prometheus Exotics]
system: content-pipeline
status: shipped
builds_on: []
video: https://www.youtube.com/watch?v=TOMZ1G2I3ds
articles:
  linkedin: https://www.linkedin.com/pulse/how-turn-every-youtube-video-linkedin-article-ai-ken-van-vorhis-nsalc/
  x:
---

# One record per video, and a LinkedIn article written from it

## What was built

A pipeline around the YouTube videos I already film, built in one day.

- **A brief deposit.** ChatGPT helps me plan each video from a voice note. After I post the video and paste the link back, it saves the plan as one file in the private GitHub repo that holds everything my AI tools know about my business.
- **A video log.** A scheduled Claude task runs twice a day in the cloud. It finds each new file and completes it into a full record of the video.
- **An article publisher.** A second scheduled Claude task runs on my laptop. It writes one LinkedIn article from the record and publishes it on my profile through my own browser.

## How the pieces connect

1. I send ChatGPT a voice note about what I built or learned. It gives me a title, a description, a thumbnail, an opening and an outline.
2. I film the video and upload it myself.
3. I paste the video link back into ChatGPT. It commits one new file to the repo with the plan and my original voice note, word for word.
4. The video log adds the live record below that deposit and changes nothing above it. The record holds the live title and description, suggested chapters, the timestamped transcript, the thumbnail and notes on where the video differed from the plan.
5. The article publisher reads the whole record, writes the article, saves it to the repo, then places it in LinkedIn with the thumbnail as the cover and the video embedded under the first paragraph.

Everything is keyed by the YouTube video id, so every file about one video can be found from that id.

## Steps

### The brief deposit

1. ChatGPT contributes the final title, the thumbnail description, the outline, the idea bullets and the prompt I sent.
2. Write only after I confirm the video is posted, so ideas I never film stay out.
3. Use a fixed template. One new file per video, and never edit a file that already exists.

### The video log

1. List the brief files and take each one that has no live record yet, at most 2 a run.
2. Pull the timestamped transcript through Firecrawl.
3. Pull the live title, description, publish time, length and counts through Windsor.ai.
4. Download the live thumbnail from YouTube's public image address.
5. Append the record: description, 4 to 7 suggested chapters, the transcript, and facts-only notes on the plan against what was said.
6. Later, add a row of numbers at day 1, day 7 and day 30, and the comments at day 7.

### The article publisher

1. Find the oldest video with a finished record and no article.
2. Read the plan, the description, the full transcript, the delivery notes and the thumbnail before writing a word.
3. Write the article from what I said, and save it to the repo before opening LinkedIn.
4. Upload the cover, type the title, paste the body, then read the page back and count headings, list items and bold runs against the file.
5. Embed the video under the first paragraph.
6. Run a gate of checks. If any check fails, leave a saved draft and tell me.
7. Click Publish once and record the live address.

## What broke and how it got fixed

- **Transcripts.** The analytics tool holds no transcripts, and YouTube refused bulk transcript pulls from the cloud and from a script in my browser. Fix: the checks were not worked around. Firecrawl returns timestamped segments from the cloud, so it became the route.
- **A batch that went nowhere.** One chat session spent 56 Firecrawl credits on tests and a 10-video batch whose result was too large to move through the conversation. Fix: Firecrawl is now used only inside scheduled tasks that name it.
- **A video the analytics tool can't see yet.** Filtering by video id returns nothing for a video that is only hours old. Fix: repeat the call without the filter and pick the row.
- **Captions that aren't ready.** A transcript call minutes after upload can come back empty. Fix: skip the video and let the next run take it.
- **Late numbers.** The analytics tool returned no rows for some videos for days, so day 1 rows were captured late.
- **The cover upload.** Clicking LinkedIn's upload button opens the laptop's file window, which the agent can't see or use. Fix: send the image straight to the page's file input.
- **Writing in the wrong place.** The article was first written by the video log, hours before publishing. Fix: the same evening the writing moved into the publisher, so it writes with the transcript, the thumbnail and everything else in view.
- **The Publish click.** On the first scheduled run that reached my browser, the session's permission check refused the click, so the article stayed a draft and I published it by hand. The first fully unattended publish worked 4 days later.

## The design choice worth copying

One file per video, and every step only adds to it. The plan stays untouched at the top, the record goes below it, and the article is written from both. Because the plan and the transcript sit in the same file, the AI writes from 2 versions of me explaining the same idea.

## Not proven yet

Whether AI assistants or search engines cite these articles hasn't been measured. Publishing still depends on my laptop being open, because the last step runs through my own browser. On 2026-11-17 these tasks were regrouped into one writer and one publisher per platform, and that arrangement has no track record yet.

## Tools

ChatGPT, Claude scheduled tasks, GitHub, Firecrawl, Windsor.ai, YouTube, LinkedIn.
