# Interpret work status

In a read, `work_status` gives one status for work: `done` or `dropped`;
`overdue` for an open item past its due date; `waiting` for an open item
that is blocked or has a party; `todo` for the other open items.
`who_acts` lists who acts next: the party, or else the owner, of each open
item at the end of its blockers, or of the item itself when nothing blocks
it. `nobody` means that no one is named.

For the status of a guide since a date, such as a weekly status, read the
guide with `include` `["changes_below"]` and `changed_since` set to that
date. The digest `changes_below` gives the items below the guide that are
new, that changed, or that are overdue or waiting now, and the count of
each status.

- A change is a change of state, party, dependency or due date. An edit of
  title, text or citations is not a change. An item that was retired or
  moved out of the guide since the date is not in the digest. An item that
  moved inside the guide reads as new.
- `waits_on` names the ends of the blocker walk: the open items at the end
  of the row's blockers. The walk stops after 10 steps, so an end can have
  blockers of its own. `open_blockers`, in a read of one item, lists each
  open blocker by distance.
- A row can be `waiting` with no `waits_on`, because it has a party.
- `waits_on_overdue` counts the overdue ends. It does not change the
  status of the row.
