# Memory operations

Read the relevant section for memory boundaries, overlap, reads, direction,
maintenance, or recovery. Ordinary capture and recall start in
[the core skill](../SKILL.md).

## Subjects and overlap

Write one memory for each subject that someone would look up or change on its
own: one job, one procedure, one register. Keep steps, conditions, and
exceptions of one subject together in one body.

Example: a developer sends one long chat message about CI/CD, testing, and
releases. Propose one memory for each subject, such as branching rules, CI
checks, required tests, release process, and hotfix exception. For each
subject, update an existing memory or write a new one. The chat message is one
source: cite it by `text` or `locator` once, then reuse its `source_id` in the
other memories. A shared tag, such as `ci-cd`, groups them. Set no owner,
because the message states none.

Before a write, search for the subject. After a write, read the `nearest`
memories in the result. They are information only and never block a write.

- When a nearest memory has the same subject, update that memory with `id` and
  `expected_version`. Do not keep two memories on one subject.
- Keep each memory's subject. For a new subject, write a new memory. When one
  memory covers two subjects, move the second subject to a new memory and write
  a new version of the original without it.
- When two memories cover one subject, tell the person and propose which one to
  retire. Put the change in the memory you propose to keep. Retire the other
  only on the person's direction, with the kept memory in `replaced_by`.

`exact_duplicate` means a current memory in the same audience has the same
title and body after lowercasing and collapsing whitespace. It returns that
memory's `id`; update or cite that memory instead.

## Change a memory

A write with `id` needs `expected_version`: the current version number you
read. Send only the fields that change; an omitted field stays unchanged.

- A change to `title`, `body`, `effective`, or `supplier`, or new `citations`,
  makes a new version. `body` replaces the whole body. The new version keeps
  the earlier citations and adds the new ones. Its supplier is the `supplier`
  you send, else you. A new version starts unconfirmed.
- A change to `tags`, `owner`, or `audience` changes the memory and makes no
  version. `tags` replaces all tags.
- `null` clears `owner` or `effective`.
- A request with no effective change returns `unchanged`.

## Read a memory

`read_memory` with `id` returns `found`: the memory, its current version, and
the history of all versions (number, title, recording time, recorder, and
whether it is confirmed). Set `version` to read an earlier version.

Each citation shows its `source_id`, locator, quote, location, the start of the
source text, and the text length. When the evidence matters beyond that start,
call `read_memory` with the same `id` and the `source_id` to get the complete
text (`source`). `replaced_by` on a retired memory names the memory that
replaced it.

## Show memories to a person

Call `show_memories` with `ids` when a person must look at stored memories:
after a capture the person must check; when they ask to see, check, or confirm
a memory; or when two current memories can cover one subject. Showing is
optional and is not approval. An MCP Apps host renders the view; other hosts
receive the memory hits as text. Name those memories in the conversation.

The view can confirm the displayed version using the person's words. Other
changes to a shown memory come from the person's words in the conversation.

## Direction and maintenance

Confirm, retire, or change an audience only on the person's direction. Put the
person's words, quoted, in `direction`. Silence, lack of objection, and agent
confidence are not direction. Reuse direction already given for the same exact
action; obtain only what is missing.

- `confirm_memory` with `id`, `version`, and `direction` records that the
  person approved that exact version. The version must be current. Approval of
  a source document does not approve the stored interpretation. A repeated
  confirmation returns the existing record.
- `retire_memory` with `id`, `expected_version`, `direction`, and optional
  `replaced_by` removes the memory from current retrieval. Retirement is final
  and deletes nothing. `replaced_by` must be a different current memory that
  you can see; otherwise the result is `invalid_replacement`.
- A write with `id` and `audience` needs `direction`. Obtain explicit direction
  before removing access from current readers.

Outcomes that change nothing:

- `stale_version` gives `current_version`. Read the memory again, reassess the
  change and the direction against the current version, then retry
  deliberately. Never increment the version blindly or retry automatically.
- `memory_retired`: the memory is retired. Change its replacement, or write a
  new memory.
- `not_found`: no visible memory has this `id`, the memory does not cite this
  `source_id`, or the `version` does not exist.
- `not_permitted`: you cannot use this group audience. Choose a group from
  `list_visibility_groups`.
- `person_not_found` names `supplier` or `owner`: the person ID is unknown, or
  no active Organization member has that email. Resolve the person, or leave
  the field out.

A tool error means invalid input or an unavailable dependency. When the error
says to check state, read the memory before a retry; the earlier change may
have committed.
