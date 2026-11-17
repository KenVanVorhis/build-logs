---
id: BL-20261115-01
date: 2026-11-15
entity: [Prometheus Exotics, Ken Van Vorhis]
system: content-pipeline
status: shipped
builds_on: []
video: https://www.youtube.com/watch?v=d3C9sbCy2Ck
articles:
  linkedin: https://www.linkedin.com/pulse/how-attract-car-owners-exotic-rental-fleet-written-ken-van-vorhis-u9soc/
  x:
---

# A blog writer and a LinkedIn publisher that run on a schedule from voice notes

## What was built

Two scheduled AI agents.

- **The blog writer** runs once a day in the cloud. It takes a voice note I recorded about one concept and publishes a post about it to my company blog.
- **The LinkedIn publisher** runs on my laptop. It publishes 1 article a day on my company's LinkedIn page. Each article answers one question from the bottom of a live blog post and links back to that post.

## How the pieces connect

1. I record a voice note about one concept. It gets saved word for word in a private GitHub repo that holds everything the AI knows about my business.
2. The blog writer turns the note into a post. Every post ends with 5 questions that car owners ask.
3. Each question goes into a queue.
4. The LinkedIn publisher takes the next question from the queue, writes the answer from the live post and the voice note, and publishes it with a link back to the post.

Both agents read one instruction file at the start of every run, and both write what they learned at the bottom of that file when they finish.

## Steps

### The blog writer

1. Look for a concept that has a finished voice note and no post yet. If there isn't one, write nothing.
2. Use the voice note as the spine. Every claim about what I did or think comes from my own words.
3. Check every outside fact against a primary source that same day. Leave out anything that can't be confirmed, or write it as my opinion.
4. Write the post with 5 owner questions at the bottom.
5. Publish that one new item through the website's CMS. Touch nothing else on the site.
6. Open the live page and check it, including the question markup search engines read.
7. Record the post in the knowledge base and send me a numbered list of everything it softened, cut or added.

### The LinkedIn publisher

1. Read the queue. It started at 50 questions from the first 10 posts.
2. Try 3 times a day, because the laptop has to be open. Stop after 1 article.
3. Use the question as the title, word for word. Write the answer only from the live post and the voice note.
4. Switch the author to the company page. Check it before typing and again before publishing.
5. Link back to the blog post, mark the question done, save the live address.

## What broke and how it got fixed

- **Cover upload.** The upload refused files from the agent's scratch folder. Fix: copy the image into the agent's working copy of the repo, upload it, remove it.
- **Headings.** LinkedIn changes the size of pasted headings. Fix: the check before publishing counts headings and doesn't match their size.
- **Two agents, one repo.** When one agent saves while another is mid-run, generated index files collide. Fix: keep the newer copy, rebuild the indexes, continue.
- **A source that refuses automated reads.** One government site blocks them. Fix: facts that depend on it are left out.

## The design choice worth copying

Keep the task's prompt short and put the whole procedure in a file the agent reads every run. To change how the agent behaves, change the file. The task itself never gets rebuilt.

## Not proven yet

Both agents publish on their own every day. Whether car owners find these pages and reach out hasn't been measured.

## Tools

Claude scheduled tasks, GitHub, Webflow, LinkedIn.
