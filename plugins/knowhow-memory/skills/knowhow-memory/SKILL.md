---
name: knowhow-memory
description: Use before you answer, plan or write code when this company's decisions, procedures, schedules, people or ongoing work could matter, even in a general question. Recalls and saves company knowledge.
---

# KnowHow Memory

KnowHow Memory holds the company's decisions, fixes and ways of working.
Each memory has a number, such as #12. The tool descriptions give the field
details, and an error result says what to fix. You have five jobs.

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
   a memory out; then do not use it, and say why. When you must check the
   source of a claim, read the memory with `include` `["citations"]` to get
   the source excerpts.
   - A long memory comes back as an index. Read only the body sections that
     the task needs with `sections`. Send `body` `"full"` only when the task
     needs the whole long text.
   - For a question about the whole engagement or project, also read the
     parent in `part_of`: terms for the whole engagement are on the parent.
5. Cite each memory that you use (#12), and say if it is only a proposal.
   Say when memories disagree, and what they do not cover.

**Why:** earlier decisions prevent repeated work and wrong choices.

## 2. Save what matters

**When:** the work produces something that a teammate would want next time:
a decision and its reason, a fix, a way to do a task, or a correction.

1. If the person asked you to save, or already agreed, save. Otherwise, say
   in one or two sentences what you would save, and ask.
2. Search for a memory on the same subject. If one exists, update it.
   Record a change on the memory that it is about. Change a memory only
   when its own state, date or claim changes, and then replace the old
   statement. Do not append a dated line, such as "30 Oct: …".
3. Write one memory for each subject that someone would look up on its own.
   For example, one message about branch rules, CI checks and releases
   becomes three memories that cite that message. Put a decision in its own
   memory, apart from the practice that it chooses.
4. Write for a teammate who was not there. Keep each condition next to its
   claim, such as "SvelteKit only: …".
5. Put a date in `due` on the memory that it is about, and work status in
   `state` (job 5), not in the body. A guide holds no status.
6. To change part of a body, send `body_edits`: the exact `old` text from
   the body and its `new` text. Send `body` only for a new or rewritten
   body.
7. When a source is wrong, has moved, or no longer supports the body, remove
   it with `remove_sources` in the write that changes the memory, and cite
   the replacement in the same write. Read the memory with `include`
   `["citations"]` when you need the excerpts to decide.
8. File the memory (job 3). If it is a part of a guide, link it (job 4).
9. Set an owner only when someone names one. If the content could be private
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
4. When someone says that an entry has the wrong kind or the wrong entry
   above it, propose a change of that entry's `kind` or `parent` with
   `define_entities`. The change needs an Organization admin. Do not add a
   new entry and refile the memories.
5. When an entry's description is stale or an alias is wrong, propose the
   change with `define_entities`. The change needs an Organization admin.

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

When asked whether a guide still applies, read its current parts. Read the
guide with `include` `["history"]` when you need its version history. Explain what the content supports. Update the
guide when the person agrees.

**Choose a link**

To link a memory to another memory, use the first test that fits:

1. It sits inside a guide or a larger memory: `part_of`.
2. It cannot finish, or cannot hold, until the other one does: `depends_on`
   (job 5).
3. The other memory sets terms that it must meet, such as a contract clause,
   a policy or a rule: `governs`, sent on the terms memory.
4. Otherwise, mention the other memory as #<id> in the body.

Link terms once, at the highest memory that they govern. Terms for one module
govern that module; terms for the whole engagement govern the project guide.
An event, a decision or a risk is not terms: write its effect into the memory
that it changes.

**Why:** a guide with linked parts keeps each subject easy to find and update.

## 5. Track work and what it depends on

**When:** the work produces a commitment, a deliverable, an access request or
other work that people promise and wait for, or someone asks what blocks an
item.

1. Give each work item one role tag: `deliverable`, `commitment`, `access`,
   `decision`, `question`, `obligation`, `event` or `risk`.
2. Set `state` only for work: `open`, `done` or `dropped`. Knowledge has no
   state. Never write "blocked" as a state: reads compute it from the open
   items that the memory depends on. Parts never block their parent.
3. Set `due` when someone promises a date. A new promise, such as a new
   date for a module, is its own `commitment` memory with `due`, filed as a
   part of the module. The module's own `due` stays its contract date. Cite
   the message that made the promise.
4. File the item `about` the other party, such as the client company or the
   person who grants access. The other party has no field of its own.
5. Record `depends_on` when the item needs another item done first, or when
   its claim rests on another memory. Pin the dependency to its current
   version when the claim rests on that memory's claim. A read then shows
   `basis_changed` when that memory gets a new version. When a parent must
   wait for one of its parts, record `depends_on` from the parent to that
   part.
6. Record `governs` on a contract clause, policy or rule, to the memories
   that must meet its terms (job 4).
7. To answer "what blocks this?", read the item and use `open_blockers`. Give
   the chain and the evidence for each blocker.
8. Memory keeps the work, its evidence and its changes. Run tasks, plans and
   reminders in the tools that do them, such as the team's issue tracker.

**Why:** the next reader sees what was promised, what is done and what
blocks the work, without the original messages.

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
  If it returns `edit_failed`, read the memory again and send `old` exactly
  as the body has it.
- When you give work to a subagent, give it the memory numbers and the facts
  that you already read, so that it does not read the same memories again.

## Other work

Read [Other tasks](references/other-tasks.md) to turn a document into
memories, find who knows something, or pick up ongoing work.
