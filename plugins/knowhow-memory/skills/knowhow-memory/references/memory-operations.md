# Memory operations

## Subjects

Example: a developer sends one long chat message about CI/CD, testing and
releases. Propose one memory for each subject: branching rules, CI checks,
required tests, release process and hotfix exception. Cite the message once and
reuse its `source_id` in the other memories. A shared tag, such as `ci-cd`,
groups them. Set no owner, because the message states none.

When one memory covers two subjects, write the second subject as a new memory,
then write a new version of the original without it.

## Direction

Direction is the person's own words for the exact action. Silence, no
objection and your confidence are not direction. Approval of a source document
or a reply does not approve the stored version. Reuse direction already given
for the same action, and ask only for what is missing.

## Outcomes

- `stale_version`: read the memory again and check the change and the direction
  against the current version before you retry. Do not increment the version
  automatically.
- A tool error that says to check state: read the memory before a retry,
  because the change can have committed.
