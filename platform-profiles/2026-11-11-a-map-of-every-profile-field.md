---
id: BL-20261111-01
date: 2026-11-11
entity: [Ken Van Vorhis, Prometheus Exotics]
system: platform-profiles
status: shipped
builds_on: []
video: https://www.youtube.com/watch?v=ddwdPDgtD14
articles:
  linkedin: https://www.linkedin.com/pulse/how-keep-your-exotic-car-rental-brand-consistent-every-ken-van-vorhis-ttofc/
  x:
---

# A map of every editable field on every profile the company controls

## What was built

A map for each profile my company and I control. Each map lists every field the platform lets me edit, with what it says today and what it should say. I call each one a platform skeleton.

- **A map of the website.** It has existed since September 2026 and lists each page with its target keyword, its main heading, its FAQs and its structured data.
- **The first 2 profile maps.** My own LinkedIn profile and my company's LinkedIn page, drafted on November 10, 2026 and rebuilt in the editor the next day. The profile has 95 slots and the page has 38.
- **One row shape for every platform.** A permanent key, the label, the kind of field and its limit, who can see it, the live value, the target and a status word.
- **The rest of the company's profiles.** On November 16 the same shape was used to map the other platforms, which brought the set to 16 company maps plus my own LinkedIn map and the website map.

## How the pieces connect

1. The website map is the plan behind the site. An AI reads it once and knows how the whole site is positioned without opening a page.
2. A profile map does the same for one profile. There is one per brand per platform.
3. Every row has 3 states. The target is what I've decided the field should say. The live value is what a read of the profile found. The gap between them is the work to do.
4. Posts, articles and videos are not in the map. A field sits on the profile until someone changes it, while a post enters a feed with a date on it, so posts are kept in a separate log.
5. Each map carries 4 labels. The type of surface, whether I control it or someone else published it, how a change reaches it, and which audience it's written for.
6. When a mapping session finds two profiles that disagree, it writes the mismatch into one shared list. That list became the input for the push in the next log in this folder.

## Steps

1. Draft the first maps from the public profile pages. This was the wrong way to do it, see below.
2. Walk the editor. A Claude session works in Chrome, signed in as the owner. It opens every edit form, every add menu and every settings screen that changes what a visitor sees.
3. Record each field's label, its kind, its limit and its current value. Save nothing and close every form.
4. Give every field a permanent key built from the platform, the account type, the group and the field. The same key means the same field on any profile of that type.
5. Mark who can see each field. Signed-out visitors, signed-in members, or only the owner.
6. Move anything that is published into a feed out of the map.
7. Write a target for each field and give it a status. OK, FIX, DRAFT, OPEN, LEAVE or N/A.
8. Decide the targets myself, field by field. Then apply the approved edits in the browser and read each one back.
9. Add a line to the map's change log every time something is read or changed.
10. Repeat for every other platform, one session per platform. Each session only maps and changes nothing live.
11. Reconcile the website map against the live site, so it lists what is there now.

## What broke and how it got fixed

- **Reading the public page.** The first drafts were read from the public profile pages, which hide every empty field. They listed 16 rows for my profile and 17 for the company page. The walk in the editor found 95 and 38. Fix: a map is only ever built from the editor.
- **A guessed column.** The first drafts ranked each field by how much an AI assistant might use it. That was a guess. Fix: the column was replaced with who can see the field, which the platform states on its own settings screen.
- **A field with a fixed list.** One platform only accepts services from its own list and neither of my company's services is on it. Fix: none. The field stays empty and the map says why.
- **A map that drifted.** The website map was 2 months old when it was reconciled, and 364 live pages were missing from it. Fix: every missing page was added, and the tasks that publish blog posts now write to the map.
- **Editors that couldn't be opened.** On some platforms Chrome was signed out, and the session doesn't sign in for me. Fix: those maps were read from the public page and say so.

## The design choice worth copying

Separate what stays from what flows. A profile field holds one value until someone decides to change it, so it can have a target and be checked. A post is added to a feed and never replaced, so it belongs in a log. The first drafts mixed the two in one document, and the publishing rows were moved out the next day.

Then split each field into target, live and gap. The target only changes when I decide. The live value is only ever read from the profile and never typed in by hand.

## Not proven yet

How much weight an AI assistant gives any single profile field hasn't been measured. Reading each map again every month is a proposal and isn't running. The longer plan is for a reviewed change to a target to be applied to every profile by agents, with a read afterwards to prove it landed. None of that is built, and today every edit waits for my go.

## Tools

Claude, Claude in Chrome, GitHub, Webflow, LinkedIn.
