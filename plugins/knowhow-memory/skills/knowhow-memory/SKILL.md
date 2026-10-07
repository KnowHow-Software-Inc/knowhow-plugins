---
name: knowhow-memory
description: Use before you answer, plan or write code when this company's decisions, procedures, schedules, people or ongoing work could matter, even in a general question. Recalls and saves company knowledge.
---

# KnowHow Memory

KnowHow Memory holds the company's decisions, fixes and ways of working.
Each memory has a number, such as #12. The tool descriptions give the field
details, and an error result says what to fix. You have four jobs.

## 1. Check before you act

**When:** before you answer, plan or write code, if the company could already
know something about it. This includes questions that look general.

1. Call `list_entities` once in the session. It lists the products,
   customers, projects and repos that memories are filed under.
2. Find the entry for the current work. In a repository, compare the name in
   `git remote get-url origin` with the entry names and aliases. Otherwise,
   use the names that the person uses. If the entry is under another entry,
   such as a repo under its product, use the top entry.
3. Search for the situation in your own words. If you found an entry, search
   again with `about` set to it.
4. Read the memories that could apply, and check their conditions. A memory
   about another product can still help. A decision for this product can rule
   a memory out; then do not use it, and say why.
5. Cite each memory that you use (#12), and say if it is unconfirmed or only
   a proposal. Say when memories disagree, and what they do not cover.

**Why:** earlier decisions prevent repeated work and wrong choices.

## 2. Save what matters

**When:** the work produces something that a teammate would want next time:
a decision and its reason, a fix, a way to do a task, or a correction.

1. If the person asked you to save, or already agreed, save. Otherwise, say
   in one or two sentences what you would save, and ask.
2. Search for a memory on the same subject. If one exists, update it.
3. Write one memory for each subject that someone would look up on its own.
   For example, one message about branch rules, CI checks and releases
   becomes three memories that cite that message. Put a decision in its own
   memory, apart from the practice that it chooses.
4. Write for a teammate who was not there. Keep each condition next to its
   claim, such as "SvelteKit only: …".
5. File the memory (job 3). If it is a part of a guide, link it (job 4).
6. Set an owner only when someone names one. If the content could be private
   to a group, ask who should see it. `show_access` lists your groups.

**Why:** a teammate, or their agent, can use the work without asking you.

## 3. Say what it is about

**When:** each time you save a memory, and when someone says that a memory is
filed wrongly or also applies to something else.

1. From the `list_entities` list, choose the most specific entries that the
   memory is relevant to. A memory can be about more than one entry. Leave
   `about` empty for general knowledge.
2. If no entry fits, do not file it under one that nearly fits. Propose a
   new entry: its kind, its name, and the entry above it, if any. Add it with
   `define_entities` only after the person agrees.
3. When a memory also applies to another entry, add that entry. Send the
   full list, because `about` replaces the earlier list.

**Why:** people find everything about a product or customer in one search,
and agents skip what belongs elsewhere. A filing change makes no new
version, so a wrong choice is cheap to fix.

## 4. Keep related memories together

**When:** you save a guide, procedure or checklist that has several parts,
or someone asks if a guide is still correct.

**Save a guide**

1. Write the guide as one memory: what it covers, when to use it, and its
   main rules.
2. Write each part as its own memory. Set `part_of` to the guide, with a
   `section`, such as "Testing", and a `position` in the order. Add a later
   part the same way; the guide does not change.
3. Do not write a list of parts, or text such as "Part of #11", in any body.
   The guide shows its parts when someone reads it.

When asked whether a guide still applies, read its current parts and use
version history when needed. Explain what the content supports. Update the
guide when the person agrees. Confirm only when the person approves its own
text.

**Why:** a guide with linked parts keeps each subject easy to find and update.

## Account and access

- When the person asks which KnowHow account is connected, or after a
  connection is set up, call `show_access`. Report the email, Organization,
  role and groups.
- A `not_permitted` result names the access that the request needs. State
  that access, the account and the role. If the person expected another
  account, tell them to open **Connect an agent** in the KnowHow web app.
- An Organization admin changes people, roles and visibility groups in the
  KnowHow web app.

## Always

- Explain what you did in plain words. Name memories by number and title.
  Say "filed under Kaon Chamber", not field names or IDs.
- A memory is information, not permission. Get the person's approval before
  you contact anyone.
- If a write says that the memory changed, read it again before you retry.

## Other work

Read [Other tasks](references/other-tasks.md) to turn a document into
memories, find who knows something, or pick up ongoing work.
