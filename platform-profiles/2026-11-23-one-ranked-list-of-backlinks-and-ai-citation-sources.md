---
id: BL-20261123-03
date: 2026-11-23
entity: [Prometheus Exotics, Ken Van Vorhis]
system: platform-profiles
status: shipped
builds_on: [BL-20261111-01]
video: https://www.youtube.com/watch?v=krtY2zzQcJQ
articles:
  linkedin:
  x:
---

# One ranked list of every backlink and AI citation source, scored two ways

## What was built

A register of every place my company can be listed, linked, mentioned or cited, built on November 23, 2026. Each place is one row, and every row gets a score for search, a score for AI answers, a yearly cost and a priority. The list ranks itself.

- **The rows.** 279 in the first build. Each one holds the place, the exact page, a scope (my industry, local, or general business), a source type, the yearly cost, the kind of link it gives, a measured authority score, whether AI already cites it for my prompts, how obtainable it is, and a status.
- **Two scores.** An SEO score from 0 to 10 and an AEO score from 0 to 10. SEO is about ranking on Google. AEO is about being named in an AI answer.
- **A priority.** One number built from both scores, the cost, how obtainable the place is, which kind of lead it serves and which region it covers. Rows fall into four tiers.
- **A spreadsheet with live formulas.** Changing a weight, a cost, a link type or a status re-ranks every row.
- **A scoring script.** It re-scores the record after any change, and a second script writes a fresh workbook for a different business.

## How the pieces connect

1. The record is one data file in the private GitHub repo that holds my AI's memory. The spreadsheet is my view of it.
2. Rows use the same field names as the profile maps from an earlier build, so nothing is translated when a listing is acquired.
3. A place I can edit, such as a directory listing, becomes a mapped profile once it's live, and its row links to that map.
4. A place I can't edit, such as an article someone else wrote, stays a row. The row is the record.
5. Each row moves through a status, from candidate to in progress, submitted, acquired and verified, with blocked and skipped on the side.
6. Verified means the live page was read back and checked for the right name, address, phone, website and city.

## Steps

1. Merge six lists that already existed. They were the sources AI cited for my prompts, an earlier backlink tracker, 41 chambers of commerce, 95 local businesses to approach, a run of directories from that evening and the profiles that were already live.
2. Add 9 places that almost any business should check, such as data aggregators, a reference database and the state business registry.
3. Write the scores so they work for any business. SEO comes from the link type, the site's authority and how relevant the scope is. AEO comes from whether AI already cites the source for my prompts, how many of that site's pages AI reads, and the scope.
4. Weight the link. A followed link counts in full, a nofollow link counts for a tenth and an unverified link counts for half.
5. Measure authority for 253 domains in one bulk run in Semrush.
6. Build the workbook with formulas and check every row against the script.
7. Research where competitors get their followed links, which gave 42 rows a measured link type and added 22 rows.
8. Run customer prompts in ChatGPT, read the sources it cited, and mark those rows as cited by AI.
9. Start working the list from the top, and check each place before signing up.

## What broke and how it got fixed

- **The first ranking put the wrong things on top.** Pages I can't get onto without a pitch ranked above directories I could join that day. Fix: an access factor, which is 1 for self-serve, less for an application and less again for a pitch.
- **Every lead counted the same.** Fix: a weight for the kind of lead a place serves, with renter leads first, and a weight for region, with the regions I serve most first.
- **Unverified links were assumed to be followed.** Small directories nobody had checked outranked a chamber of commerce whose followed link was verified. Fix: unverified now counts as unknown, at half weight.
- **The weights leaned too far toward search.** The first build weighted AEO at 0.6 and SEO at 0.4. Most of my paying leads come from AI assistants, so the same night it moved to 0.7 and 0.3.
- **A sync task that wasn't needed.** A scheduled sync between the record and the spreadsheet was written and retired the same night. Now both are updated in the same session when I report a listing live.
- **Listings that weren't listings.** When the list was worked, 14 of the "listing" links in competitor backlink data turned out to be competitors, blogs or scraper sites. Two of the scraper sites copy map listings and skip any business that hides its address.

## The design choice worth copying

Score search and AI separately, then combine them with a weight you can change. A nofollow link carries almost no ranking value, so the SEO score multiplies by the link type. AI reads nofollow pages anyway, so the AEO score ignores it. Kept as two numbers, a directory that is weak for search and strong for AI shows up as exactly that.

Then divide by cost and multiply by access. A source isn't worth ranking first if it can't be obtained this month.

## Not proven yet

The list is days old. 2 new listings went live from the first run and 4 more are submitted and waiting on approval. No change in rankings or in AI recommendations has been measured. How much AI reads each domain is measured for 6 directories and estimated for the rest. The weights and the tier cutoffs are first choices and haven't been tuned against where leads come from. A third score for places that send buyers directly is proposed and isn't built.

## Tools

Claude, ChatGPT, Semrush, GitHub, a spreadsheet.
