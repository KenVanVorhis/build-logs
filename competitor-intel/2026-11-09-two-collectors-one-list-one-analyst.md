---
id: BL-20261109-01
date: 2026-11-09
entity: [Prometheus Exotics, Ken Van Vorhis]
system: competitor-intel
status: shipped
builds_on: [BL-20261108-01]
video: https://www.youtube.com/watch?v=CAUL5dIf4bg
articles:
  linkedin: https://www.linkedin.com/pulse/how-track-competitors-ai-without-reading-every-report-ken-van-vorhis-pgyhc/
  x:
---

# Two competitor collectors, one shared list and one weekly analyst

## What was built

I had two AI workflows researching the other agencies in my market, each sending me its own report in its own app. In one day they were rebuilt into one stream.

- **A web collector.** A scheduled Claude task that reads each agency's website every morning for listed cars, prices and what the homepage says.
- **A social collector.** An agent in a separate app that reads Instagram and Threads, and on Mondays the Meta Ad Library.
- **One shared list.** Both collectors read who they track from the same private GitHub repo, where each agency has one note with one permanent id.
- **One analyst.** A third agent reads both collectors' files every day, messages me only when something needs me that day, and writes one analysis a week.

## How the pieces connect

1. The private repo is the seam. Each collector writes one data file and one readable file a day, named by the date, into its own folder.
2. Neither collector summarizes. They save what they saw with its date and nothing else.
3. The web collector's code, its site adapters and its dictionary of car models live in the repo. A script rebuilds the previous day's snapshot from the repo, and the collector's own code works out every change, not the AI model.
4. The social collector reads its watch list from the agency notes at the start of every run and writes only inside its own folder.
5. The runs are staggered in the morning, web first, then social, then the analyst.
6. The analyst reads the newest file from each collector with the previous 7 days for context. On Mondays it lines the two feeds up by agency and saves the analysis in the repo, with one dated line on the note of each agency that had a real change.
7. Three writers push to one repo, so each one pulls the latest version first and retries a refused push once.

## Steps

1. Audit the old setup. The web collector had been running every day since October 5 into its app's own database.
2. Take the paid SEO data calls out. The allowance was used up in about two prompts.
3. Change the reports from daily to weekly and send them to the repo.
4. Give every tracked agency one note with one id, and move the social accounts onto those notes. People got their own notes, and who works where became a relationship note that can change when someone moves.
5. Rule that collectors only collect. The store moved out of the app and into the repo as dated files.
6. Write the new contract for the web collector and the script that packs a day's data into the repo and unpacks the day before.
7. Write a new prompt for the social collector that ends its own reports, and a brief for the analyst.
8. Have the social collector find the newly added agencies on Instagram. It accepts an account only when two things agree, such as the link in the bio and the city, and when two accounts could be the one it lists both and tracks neither until I pick.
9. Have the analyst prove it can read and write the repo before it's trusted with anything.
10. Run the first morning. Both collectors delivered on November 10, and the first weekly analysis on the new setup was written on November 16.

## What broke and how it got fixed

- **A weekly run that had quietly stopped.** The audit found the Monday branch of the web collector had ended early for five weeks because one setting was missing from the task. The daily runs were healthy, so nothing looked wrong. Fix: the redesign, and an analyst that reports when a collector didn't write its file.
- **A scheduled task that couldn't save.** The first run on the new design collected everything and couldn't push to the repo, because the task had been created before the repo existed. A test task created from a session with the repo attached pushed in under a minute. Fix: create the task again.
- **One agency under two ids.** The two collectors filed the same agency under different ids. Fix: the agency's note is the anchor for its id.
- **A car read as the wrong car.** The dictionary of car models read one sports car as a different make's model. Fix: the dictionary, plus five models it was missing.
- **A side branch.** The analyst's session pushed its work to a side branch nobody else reads. Fix: its routines push to the main branch and confirm it landed.
- **A look-alike account.** One handle belonged to a different business with a similar name. It wasn't tracked until I said which one I meant.
- **A late drop.** On the first morning the social collector delivered about an hour and a half after its scheduled time.

## The design choice worth copying

Collectors don't analyze. A summary throws away the detail you need later, and raw data can be read again while an analysis can't be regenerated from a summary. So the collectors may add arithmetic, such as the change in a count since yesterday, and they never add an opinion.

The second choice is one list. Every finding is tied to an agency's note by its id, so the website view and the social view of the same agency meet in one place.

## Not proven yet

It only reads what's public. A car listed on a website is advertised reach, not a car that's available, and likes and comments are the only engagement numbers it has for other agencies. A count that reverses the next day is treated as a bad read, so the analyst waits a day before raising a jump. I'm still checking what it reports against what I can see for myself.

## Tools

Claude, GitHub, Python, Instagram, Threads, Meta Ad Library.
