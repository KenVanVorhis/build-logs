---
id: BL-20261114-01
date: 2026-11-14
entity: [Ken Van Vorhis, Prometheus Exotics]
system: entity-graph
status: shipped
builds_on: []
video: https://www.youtube.com/watch?v=XlHJm-iiTXA
articles:
  linkedin: https://www.linkedin.com/pulse/how-build-knowledge-graph-exotic-car-rental-companys-ai-van-vorhis-rozdc/
  x:
---

# An entity graph for my AI's memory: attribution, typed relationships and dated facts

## What was built

Three layers over the private GitHub repo that holds everything my AI tools know about my business, built in one day.

- **Attribution.** Every note that names a person, a company, a tool or an idea says so at the top of the file. Every one of those entities has its own note, and each entity note carries a generated list of every record in the repo that names it.
- **Typed relationships.** A fixed list of relationship kinds, and every relationship note mapped to one or more typed links between two entities.
- **Dated facts.** A list of facts on an entity's note, each with the date it became true or the dates it started and ended, where it came from, how sure it is and whether it's current, past or wrong.

The same day the entity notes were sorted into folders by type, and each one got a permanent id.

## How the pieces connect

1. One script is the hub. It finds notes that name an entity without attributing it, writes the list of records onto each entity note and validates the typed links and the dated facts.
2. One command pulls everything the repo holds on a single entity.
3. The same command can answer as of a date, so it returns what was true on that day and not only what is true now.
4. A short box under the title of each entity note with facts says what is true now, so a reader who stops at the top gets the current state.
5. A rule in the instructions every AI session reads makes each session attribute what it writes, so the graph keeps growing without a cleanup job.

## Steps

1. Write the rule. Any note or data file that names an entity carries it at the top of the file.
2. Build the script, then backfill. 335 notes gained about 1,050 attributions, and all 137 entity notes got their list of records.
3. Close the loose ends. 450 names that pointed at no entity note were brought down to 62. Variant spellings became aliases, and new placeholder notes were created and marked unconfirmed.
4. Sort the entity notes into folders by type and give each one a permanent id.
5. Draft a vocabulary of relationship kinds and map all 70 relationship notes to typed links. The script validated them, 10 judgment calls went to me, and the mapping was applied after my corrections. That gave 85 typed links of 21 kinds with 0 errors.
6. Pilot dated facts on 4 entities, 41 facts, each one taken from what the repo already said with its date and source. A second batch brought it to 97 facts on 16 entities, and the list of fact types grows when a new fact needs one.
7. Generate the current-state box on every entity note that has facts.
8. Test recall in a fresh session that can only read. I asked 20 fixed questions with the answers written down first.

## What broke and how it got fixed

- **Names that led nowhere.** 450 names written before the rule pointed at no entity note, so those entities couldn't be pulled. Fix: aliases for the variants and placeholder notes for the rest.
- **An old claim at the top of a note.** After the facts were added, the body of two entity notes still described an old arrangement in the present tense, so a reader who stopped at the top got a claim that was no longer true. Fix: the current-state box, and a rule that a new fact that makes body text wrong fixes the body in the same change.
- **Facts everywhere weren't needed.** A second recall test on entities with no dated facts also scored 20 of 20, because their notes were current. Fix: facts are added where a state changes or two notes disagree, not to every entity.

## The design choice worth copying

Put the attribution in the file that holds the record, and generate the index from it. Nobody maintains a separate list of what belongs to whom. Each session writes what it knows at the top of the file it creates, and the script rebuilds every entity's list from that.

Then keep the past instead of overwriting it. A fact that stops being true is marked past with an end date, and a fact that was wrong is marked wrong, so the AI can say what was true on any date.

## Not proven yet

The recall tests were 20 questions each, written by the same AI that built the graph. Whether answers stay this good as the number of entities grows hasn't been measured. Publishing the same profile links from the graph onto the company's public pages is planned and isn't built.

## Tools

Claude, GitHub, Python, Obsidian.
