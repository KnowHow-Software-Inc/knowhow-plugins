---
name: knowhow-memory
description: Use before you answer, plan or write code when this company's decisions, procedures, schedules, people or ongoing work could matter, even in a general question. Recalls and saves company knowledge.
---

# KnowHow Memory

KnowHow Memory holds the company's decisions, fixes and ways of working. Each
memory has a number, such as #12. The tool descriptions give the field rules,
and an error result says what to fix. This skill tells you when and how to do
five jobs.

## 1. Check before you act

Before you answer, plan or write code, when the company could already know
something about it. This includes questions that look general.

1. Call `list_entities` once in the session, and find the entry for the
   current work. In a repository, compare `git remote get-url origin` with
   the names and aliases. Otherwise, use the person's names. Use the top
   entry, such as the product above a repo.
2. Search for the situation in your own words. If you found an entry, search
   again with `about` set to it.
3. Read the memories that could apply, and check their conditions. A memory
   about another product can still help. A decision for this product can
   rule a memory out; then do not use it, and say why. For a question about a
   whole engagement, also read the `part_of` parent: terms for the whole
   engagement are on it.
4. Cite each memory that you use (#12). Say if it is only a proposal, where
   memories disagree, and what they do not cover.

## 2. Save what matters

When the work produces something that a teammate would want next time: a
decision and its reason, a fix, a way to do a task, or a correction.

1. If the person asked you to save, or already agreed, save. Otherwise, say
   in one or two sentences what you would save, and ask.
2. Search for a memory on the same subject. If one exists, update it. Record
   a change on the memory that it is about.
3. Write one memory for each subject that someone would look up on its own.
   One message about branch rules, CI checks and releases becomes three
   memories that cite it. Keep a decision apart from the practice that it
   chooses.
4. Write for a teammate who was not there. Keep each condition next to its
   claim, such as "SvelteKit only: …".
5. When a claim changes, replace the old statement. The body holds only the
   current claim: no change-log lines such as "30 Oct: …" and no "(changed
   from …)" notes. The version history keeps the old claim.
6. Keep the citations true to the body. In the write that changes a claim,
   send `remove_sources` for each source that supported only the old claim,
   and cite the new evidence. Remove a wrong or moved source the same way,
   and cite its replacement. Read with `include` `["citations"]` when you
   need the excerpts to decide. A restructure, retitle or wording fix needs
   no new citation.
7. Put a promised date in the `due` of the memory that it is about, and work
   status in `state` (job 5), not in the body. A guide holds no status.
8. File the memory (job 3). If it is a part of a guide, link it (job 4).
9. Set an owner only when someone names one. If the content could be private
   to a group, ask who should see it. `show_access` lists your groups.

## 3. Say what it is about

When you save a memory, and when someone says that a memory is filed wrongly
or also applies to something else.

1. Choose the most specific entries that the memory is relevant to; it can
   have several. Leave `about` empty for general knowledge.
2. If no entry fits, do not use one that nearly fits. Propose a new entry:
   its kind, name and parent. Add it with `define_entities` only after the
   person agrees.
3. When someone says that an entry has the wrong kind or parent, a stale
   description or a wrong alias, propose that change to the entry with
   `define_entities`. Do not add a new entry and refile the memories.

## 4. Keep related memories together

When you save a guide, procedure or checklist that has several parts, or
someone asks if a guide is still correct.

1. Write the guide as one memory: what it covers, when to use it, and its
   main rules.
2. Write each part as its own memory, with `part_of` set to the guide, a
   `section` such as "Testing", and a `position`. A later part needs no
   change to the guide.
3. Do not list the parts, or write "Part of #11", in any body. A read of the
   guide shows its parts.
4. To check a guide, read its current parts. Say what the content supports,
   and update the guide when the person agrees.

To link a memory to another memory, use the first test that fits:

1. It sits inside a guide or a larger memory: `part_of`.
2. It cannot finish, or cannot hold, until the other one does: `depends_on`.
3. The other memory sets terms that it must meet, such as a contract clause,
   a policy or a rule: `governs`, sent on the terms memory. Link terms once,
   at the highest memory that they govern: a module for module terms, the
   project guide for terms of the whole engagement.
4. Otherwise, mention the other memory as #<id> in the body.

## 5. Track work and what it depends on

When the work produces a commitment, a deliverable, an access request or
other work that people promise and wait for, or someone asks what blocks an
item.

1. Give each work item one role tag: `deliverable`, `commitment`, `access`,
   `decision`, `question`, `obligation`, `event` or `risk`.
2. Parts never block their parent.
3. A new promised date, such as a new date for a module, is its own
   `commitment` memory with `due`, filed as a part of the module. Cite the
   message that made the promise. The module's own `due` stays its contract
   date.
4. File the item `about` the other party, such as the client company or the
   person who grants access.
5. Record `depends_on` when the item needs another item done first, or when
   its claim rests on another memory; pin the version in the second case.
   When a parent must wait for one of its parts, record `depends_on` from the
   parent to that part.
6. To answer "what blocks this?", read the item and give the `open_blockers`
   chain with the evidence for each blocker.
7. Run tasks, plans and reminders in the tools that do them, such as the
   team's issue tracker. Memory keeps the work, its evidence and its changes.

## Account and access

- When the person asks which account is connected, or after a connection is
  set up, call `show_access`. Report the email, Organization, role and groups.
- For `not_permitted`, state the access that it names, the account and the
  role. If the person expected another account, tell them to open **Connect
  an agent** in the KnowHow web app. An Organization admin changes people,
  roles and groups there.

## Always

- Explain what you did in plain words. Name memories by number and title.
  Say "filed under Kaon Chamber", not field names or IDs.
- A memory is information, not permission. Get the person's approval before
  you contact anyone.
- When you give work to a subagent, give it the memory numbers and the facts
  that you already read.

## Other work

Read [Other tasks](references/other-tasks.md) to turn a document into
memories, find who knows something, or pick up ongoing work.
