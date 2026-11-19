---
id: BL-20261108-01
date: 2026-11-08
entity: [Ken Van Vorhis, Prometheus Exotics]
system: vault
status: shipped
builds_on: []
video: https://www.youtube.com/watch?v=9FIMmY8F1zg
articles:
  linkedin: https://www.linkedin.com/pulse/how-give-every-ai-tool-same-memory-your-business-ken-van-vorhis-emzlc/
  x:
---

# My AI's memory moved into a private GitHub repo that every tool reads

## What was built

Everything my AI tools know about my business used to sit in a notes folder on my laptop, synced through a cloud drive. Over two days it became a private GitHub repo that Claude writes to, ChatGPT reads, and scheduled agents use with my laptop closed.

- **Day 1, the structure.** Every note was read again and sorted into folders by function. Every note got the same six fields at the top, and the index pages are generated from those fields.
- **Day 2, the move.** The private repo was created and the whole folder was pushed, 2,528 files and about 203 MB. The same evening the laptop folder was replaced by a clone of the repo, and Obsidian was pointed at the clone as a viewer.

## How the pieces connect

1. The repo is the one copy that counts. If a chat or a tool's built-in memory disagrees with it, the repo is right.
2. One file at the top of the repo tells Claude what to read first for each kind of work. A second file does the same for other AI models.
3. Each tool gets its own GitHub permission. Claude's GitHub app is limited to this one repo and can read and write. ChatGPT's connector reads the whole repo.
4. Claude writes from the cloud. It clones the repo in its own session, edits, commits and pushes, and my laptop isn't part of that.
5. The folder on my laptop is a cache. GitHub Desktop pulls the changes, shows each one as a before and after, and can undo one with a click. Obsidian opens that folder so I can read the notes.
6. Scheduled agents clone the same repo in the cloud, so they read the same memory and save their work back to it.

## Steps

1. Audit the old folder. Of 698 notes, 256 had nothing linking them to anything and 56 more had nothing pointing at them. The index had drifted out of the folder, new notes were being saved without their fields and links, and newer projects had no index page.
2. Decide the structure. Folders by function, one folder for every company and person, and one running log.
3. Apply it. 25 batches of AI agents read every note in full, sorted it, and wrote the six fields at the top, which say what kind of note it is, who it's about, whether it's current, who may see it, what it holds in one sentence and which index it belongs under. 18 files with no value, such as exact duplicates and empty files, were retired.
4. Empty the AI's built-in memory into the folder. All 163 files in it were checked against the notes, which created 45 new notes and extended 17. That memory was then rewritten as a short router that points into the folder.
5. Create the private repo and limit the Claude GitHub app to it.
6. Scan for secrets before the first push, and exclude passwords and keys, app settings that belong to one machine and archive files over GitHub's 100 MB limit.
7. Push the folder.
8. Move the laptop copy out of the synced drive into a plain folder that is a clone of the repo, point Obsidian at it and freeze the old folder.
9. Rule that writes happen in the cloud only and the laptop only pulls.
10. Connect ChatGPT to the repo to read, with its own entry file.
11. Two days later, give ChatGPT one way to write. When I confirm a video is posted it adds one new file with a fixed template, and it never changes or deletes a file that's already there.

## What broke and how it got fixed

- **Git and a synced drive in one folder.** They fight over lock files, the drive churns on git's own files, and files that exist only in the cloud are invisible to git. Fix: the folder left the drive the same evening the repo went live.
- **No GitHub sign-in on the laptop's command line.** The AI couldn't push from the laptop. Fix: pushes came from its cloud session, and GitHub Desktop was installed for the laptop side.
- **A second, cleaned copy for ChatGPT.** The AI proposed a separate repo with sensitive notes stripped out. I overruled it, because my own AI tools should read everything, and only tools that act for a single company get a curated export.
- **A wrong claim about ChatGPT.** The AI told me ChatGPT's GitHub connector could only read. ChatGPT reported that it could write files, and the AI corrected itself.
- **ChatGPT's write path.** It started as a pull request for the AI to review. I overruled that to a direct save of one new file, because it's only depositing data that another agent expands later.
- **A scheduled agent that couldn't save.** An agent created before the repo existed couldn't push to it. Fix: create the agent again from a session that has the repo attached.
- **Links on GitHub's site.** Links between notes written the way Obsidian writes them show as plain text on GitHub. I accepted that, because the tools read the files and I read them in Obsidian.

## The design choice worth copying

Separate where the memory lives from how it's organized. GitHub gave me history, access from the cloud and a permission per tool. The six fields at the top of every note and the entry file are what let a tool find the right handful of notes out of hundreds.

Then keep one writer per kind of change. One AI writes, the others read or add a new file in a situation I've named, and nothing counts as my decision until I've ruled on it.

## Not proven yet

A reviewer that checks every proposed change before the other tools read it isn't built. ChatGPT's write path covers one kind of file. The memory still needs upkeep, and I read what comes back before anything goes out under my name.

## Tools

Claude, ChatGPT, GitHub, GitHub Desktop, Obsidian.
