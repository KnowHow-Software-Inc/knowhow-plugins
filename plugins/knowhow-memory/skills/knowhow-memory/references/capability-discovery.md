# Find relevant experience and resolve a knowledge gap

Use this flow when the user asks who can help, or a specific missing answer
prevents useful progress. Make the capability discoverable in context: explain
that you can look for people with relevant demonstrated contributions.

## Investigate the missing question

Make the question specific enough to investigate. Reuse relevant memory searches
and evidence already obtained. A weak search does not establish that the
organization lacks an answer. A current memory tagged `gap` can show that the
question is already known and who was asked.

Use `find_people` with a `query` for contributors on a related topic. It ranks
the suppliers and owners of visible matching memories. Each person has the
matching memories with their number, title, and role: `supplier`, `owner`, or
both. Read the relevant memories with `read_memory` before you rely on them.

Search other accessible sources when they can help: repository documentation,
Git history, messages, or shared files through available host tools. These may
identify experience even when KnowHow has no attributed memory on the topic.
Search from the question and related work; follow concrete evidence instead of
exhaustively inspecting every connected system.

## Explain whom to ask

Identify the contribution that connects a candidate to the question: authoring a
procedure, implementing a related change, explaining an exception, or handling a
similar case. Distinguish an author from someone who merely forwarded a document
or participated in a channel.

Contribution supports a reason to ask; it does not establish decision authority,
ownership, availability, or expertise in every related subject. A display name
alone does not resolve identity across systems. Preserve the evidence and
uncertainty, and resolve an ambiguous recipient before sending.

The task can end with the relevant people and evidence. When outreach would
resolve a clear gap, proactively offer a concrete proposal with:

- The recipient and channel, if one is available.
- Why their demonstrated contribution is relevant.
- The focused question and context you would send.

Include enough context for an answer, within the intended recipient's permitted
audience. Access to restricted evidence does not authorize sharing it with a new
audience. Keep the proposal useful even if the user chooses to contact the person
directly.

## Contact only after approval

Obtain the user's approval of the concrete outreach before sending. Reuse
approval already given for that same action. If the host has a sending tool and
the recipient is resolved, start the approved conversation and report its actual
outcome. If the host cannot send, provide a draft. If approval is declined, leave
the gap explicit without contacting the person.

An uncertain send outcome calls for checking the channel state before a repeat
that could send the same message twice. Follow-up messages and background reply
monitoring need authorization within their own scope; a first message does not
establish an open-ended outreach task.

## Bring the answer back

When the answer is available through the user or an authorized channel, assess
whether it resolves the original question. Preserve qualifications and separate
the person's advice from a decision they are authorized to make.

Apply useful knowledge to the original task. Capture under the user's request
or existing authorization. Cite the conversation by locator, text, or both. Set
`supplier` to the person who answered, by person ID or corporate email; resolve
an ambiguous identity instead of guessing a match. When the answer resolves a
memory tagged `gap`, write the answer as a new version of that memory and
remove the tag. Use [memory operations](memory-operations.md#direction-and-maintenance)
for confirmation or other changes. A reply is evidence, not automatic approval
of an exact stored memory version.
