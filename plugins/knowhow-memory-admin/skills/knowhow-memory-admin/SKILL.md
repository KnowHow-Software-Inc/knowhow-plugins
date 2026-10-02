---
name: knowhow-memory-admin
description: Use when a Clerk Organization admin asks to create or rename a KnowHow visibility group, or to add or remove a member. Invitations and account access stay in Clerk.
---

# KnowHow Memory administration

Do only the change that the admin asks for. Ask only when a target or the
change is ambiguous.

- **Create:** use the requested slug and display name. List the groups first
  only to resolve the target or prevent a duplicate.
- **Rename:** resolve the group ID, then rename.
- **Add member:** resolve the group and the person. Use `search_people` for a
  partial name or email, and do not guess between matches. If the person is not
  in the directory, use `materialize_person` with their exact verified
  corporate email, then add them.
- **Remove member:** select the person from the group's current membership.

Report the outcome from the returned membership. If an error says the change
can have committed, read the current state before a retry.

Adapter keys and identity-binding repair are operator work.
