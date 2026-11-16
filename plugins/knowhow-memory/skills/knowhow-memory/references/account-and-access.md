# Account and access

After setup, or when asked which account is connected, call `show_access`.
Report the KnowHow email, Organization, role and visibility groups it returns.
The connection identifies the person to KnowHow. The email used to sign in
to the agent app can differ.

## Who can read and write a memory

Each memory has one audience. A member can save a memory for themselves,
for the Organization, or for a visibility group they belong to.

| Audience | Who can read it |
| --- | --- |
| Personal | The person who set the personal audience |
| Organization | Every member of the Organization |
| Group | Members of that visibility group |

Anyone who can read a current memory can update it. Group membership matters
only for the group audience. Personal and Organization memories are available
under the same rules even when the member belongs to no groups.

## Check a specific memory

Call `read_memory` with the memory number through the connection whose access
is in question. A `found` result confirms that account can read it.
A `not_found` result can mean the number is unknown or the memory is hidden
from that account.

If an operation returns `not_permitted`, report the required access, account
and role from the result. If the person expected a different account, direct
them to **Connect an agent** in the KnowHow web app. If the account is
correct, an Organization admin can change the role or group membership.
