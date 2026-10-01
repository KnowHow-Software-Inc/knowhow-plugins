# Acquire and apply company guidance

Use this flow when a manager supplies SOPs or other documentation for capture,
or when interpreting a procedure for a user's situation. The goal is knowledge
that another agent can find and use without knowing the document exists.

## Intake

### Interpret the supplied material

Read the selected material through the host's available file or connector tools.
If part is inaccessible or unreadable, explain the affected coverage. KnowHow
stores interpreted memories; it does not fetch and import a document merely
because its URL appears in a receipt.

Identify the situations covered, applicable people or roles, required actions,
sequence, exceptions, and supporting evidence. Preserve distinctions between
requirements, examples, suggestions, and unresolved questions. Ask the manager
focused questions when ambiguity would change the meaning or application. Reuse
answers and context already supplied.

Write one memory for each subject that someone would look up or change on its
own; see [subjects and overlap](memory-operations.md#subjects-and-overlap).
Choose boundaries by subject, rather than by paragraph or document. Keep steps,
conditions, and exceptions of one procedure together in one body, in their
order. Give each memory a title that names the subject, so that a search from a
situation can find it.

For example, an isolated “Manager approval is required” loses its trigger. A
memory titled “Customer refund approval” with the threshold, approver, and
exceptions in its body can be found from a refund situation. This is an
illustrative policy only; use the actual source's conditions, thresholds, and
exceptions. When several memories come from one document, cite it once and
reuse its `source_id`.

### Capture and make the interpretation reviewable

Follow the user's requested save/review sequence. A request to save supports
capture of sufficiently clear content as unconfirmed memories; a request to
inspect proposals first leaves them unsaved. Clarify consequential ambiguity
before capturing the affected claim. Neither sequence grants automatic
confirmation. Record an unresolved question as a memory tagged `gap`.

Search for related memories before a write, and read the nearest memories after
it. When a subject already has a memory, update it; follow
[subjects and overlap](memory-operations.md#subjects-and-overlap) when two
memories cover one subject. Source upload alone does not authorize retiring
unrelated knowledge or changing its audience.

Give the manager a concise account of the resulting interpretation: the
memories saved or proposed with their numbers, audience and sources, and
material gaps or ambiguities. Use
[direction and maintenance](memory-operations.md#direction-and-maintenance) if
the manager directs confirmation of stored versions. Approval of the source
document does not by itself approve the agent's exact stored interpretation.

After substantial intake, offer a brief scenario trial when it would help the
manager assess future use. Explain what it could show; a trial is optional.
If the user wants to proceed, read [Help the manager try the result](#help-the-manager-try-the-result).

## Apply guidance to a situation

Search from the problem, relevant roles, and circumstances rather than requiring
an SOP title. Also search for the procedure or rule that governs the situation
by name: a search from the situation alone can rank that procedure low. Check the triggering conditions and relevant exceptions before
applying a retrieved rule. Ask for missing task facts only when they affect the
decision. Read the memory body, and the complete source text when needed, for
ordered procedures or qualifications that a search hit alone cannot establish.

Explain the practical consequence for this task and provide supporting sources.
Preserve unresolved conflicts instead of choosing a rule solely because its
wording matches or its memory is confirmed. When missing company knowledge
blocks progress, use [capability discovery](capability-discovery.md) to find a
useful contributor or propose a question.

## Help the manager try the result

For a requested trial, propose realistic situations in which this guidance
should help, including a relevant exception. A fresh agent should
receive the situation without an SOP title, known tag, memory ID, or instruction
to search memory. Use a fresh session only through an available and authorized
host mechanism; otherwise provide the scenario for the user to try.

Inspect what the agent found and how it applied it. Report missed guidance,
lost qualifications, and unresolved coverage. A successful write or a count of
stored memories establishes capture, not dependable future use.
