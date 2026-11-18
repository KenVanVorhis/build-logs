---
id: BL-20261116-02
date: 2026-11-16
entity: [Prometheus Exotics, Ken Van Vorhis]
system: platform-profiles
status: shipped
builds_on: []
video: https://www.youtube.com/watch?v=HpFQVPEBj10
articles:
  linkedin: https://www.linkedin.com/pulse/how-reposition-exotic-car-rental-brand-every-platform-ken-van-vorhis-qiejc/
  x:
---

# One brand description pushed to every platform

## What was built

One description of my company, written once and pushed to 11 platforms in about an hour, with the website following the same night.

- **A map of every profile.** 16 company profiles plus the website. Each map lists every field the platform lets me edit, the field's limit, what it says today and what it should say.
- **A shared mismatch list.** While each profile was mapped, everything that disagreed with another profile went into one list. It reached about 290 entries.
- **A fact sheet and a description in blocks.** One value for every fact, and one description written as 6 blocks in a fixed order.
- **A change sheet per platform.** Every edit as one row with the current value next to the new value.

The platforms that took the push were Google Business Profile, Yelp, Facebook, LinkedIn, X, YouTube, Nextdoor, Pinterest, Crunchbase, Trustpilot and Apple Business.

## How the pieces connect

1. The fact sheet declares each fact once. Name, category, the 4 makes in a fixed order, the fleet figure, where the company is based, the service area, hours and website.
2. The description is built from the fact sheet as 6 blocks. A platform with a small field takes the first blocks and a platform with a large field takes all of them, so every profile carries the same sentences in the same order.
3. Each platform's map holds its change sheet. The sheet is the fact sheet and the blocks shaped to that platform's fields and limits.
4. One review session checks every change sheet against the fact sheet before anything goes live.
5. The changes are applied in the browser one row at a time, and each saved value is read back from the page.

Search engines and AI assistants compare these profiles with each other and with the website. Agreement between them is the signal.

## Steps

1. Map every profile. One Claude session per platform, working in Chrome, signed in as the owner. It opens every edit form, records each field, its limit and its current value, and saves nothing. 15 sessions ran at the same time and it took about 3 hours.
2. Have each session write every mismatch it finds into the shared list.
3. Decide the positioning. This part was mine and not the AI's. The company is a specialist in Lamborghini, Rolls Royce, Ferrari and McLaren, and its fleet of 300+ vehicles also includes rare and top-trim models from other makes.
4. Build the change set in one session. The fact sheet, the 6 blocks, a short version of 120 characters, and 21 target texts, each one counted in code against its field's limit.
5. Have each platform session write its change sheet into its own map. Still nothing live.
6. Open a fresh session to review every sheet. It checks the wording word for word, the make order, the links and the character counts. 123 changes were ready on 11 platforms.
7. Apply the changes on my go, one row at a time, and read each saved value back. A row that doesn't hold is recorded as a failure.
8. Push the website last, after its own review. It got the same description, structured data that names the founding date, links to every profile, and a new llms.txt file.

## What broke and how it got fixed

- **Addresses.** One platform moved the unit number into its own box and rewrote it. Another replaced the address with its own suggestion and couldn't store a unit number at all. Fix: none. Both are recorded as failures with what the screen showed.
- **A save that didn't stick.** One platform showed its success notice 3 times and kept displaying the old description. Fix: left as it was and marked to recheck.
- **A listing sent back into review.** Saving a new description on one platform resubmitted the whole listing for review with no warning. Fix: the remaining rows were held until I decided, then pushed while it was in review.
- **Locked fields.** One listing copies its fields from another platform on a schedule and locks them. Turning the schedule off didn't unlock them. Fix: turned it back on and held that platform out of the push.
- **A drag that deletes.** On one platform, dropping a board onto another board merges them and deletes the one you dragged. Fix: cancelled the prompt and left the order alone.
- **The voice.** The first version of the description said "its fleet", which reads like someone else wrote about us. Fix: the first sentence names the company, and after that the profile says we and our. Reference records stay in the third person. The descriptions were pushed again to 5 platforms the same evening.
- **Profile copy on the website.** The first website push named me as founder in too many places and opened local pages with the company's home city. Fix: corrected the same night. A profile carries the whole identity in one block and a web page carries only what that page is for.

## The design choice worth copying

Map first, push once. The sessions that map a profile change nothing on it. Every edit is written down next to the current value, checked in one place, and only then applied. And every text is counted against its field's limit before the push, so nothing gets cut off by a platform after it's saved.

## Not proven yet

The new wording is live. Whether search engines and AI assistants describe the company differently hasn't been measured. 2 directories still have to be claimed, 3 mapped profiles were held out of this push, and the rows that failed are tracked in the maps. The AI doesn't rewrite a profile on its own. Every push waits for my go.

## Tools

Claude, Claude in Chrome, GitHub, Webflow.
