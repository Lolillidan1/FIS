---
document_id: FIS-FOUND-005
title: FIS Communication Foundation
category: Foundation
scope: universal
workers: none
dependency: none
version: 0.1.0
created: 2026-08-17
updated: 2026-08-17
authors:
  - Siddharth Sinha
  - Aria (ChatGPT-System Architect)
copyright: © 2026 Siddharth Sinha. All rights reserved.
---

# FIS-FOUND-005 — FIS Communication Foundation

## 1. Purpose

`FIS-FOUND-002 — FIS Intelligence Worker & Role Framework` establishes communication as controlled FIS architecture while deliberately leaving the complete communication mechanism to `FIS-FOUND-005` and later specifications.

This Foundation establishes the conceptual communication model of FIS.

Its purpose is to define:

- what FIS communication is;
- when FIS communication is required;
- who may participate in communication;
- the fundamental Session Types;
- the fundamental Communication Types;
- the distinction between Sessions, Communications, and Messages;
- the distinction between communication capability, permission, authority, and responsibility;
- the foundational model for mediated Worker communication;
- and the boundaries between communication architecture and its later implementation.

This Foundation does not define the final transport mechanism, communication package schema, trigger syntax, database schema, API implementation, queue implementation, or complete acknowledgement and failure protocols.

Those subjects belong to later Definitions, Templates, Logic, Specifications, and Logistics resources.

---

## 2. Communication as a FIS System Capability

FIS is a distributed intelligence system containing multiple participants that may operate in separate conversational or computational environments.

A participant may therefore require communication with another participant without sharing the same direct interaction interface.

FIS communication exists to provide a controlled system mechanism for such interaction.

The fundamental model is:

```text
Participant A
      ↓
FIS Communication
      ↓
Participant B
```

The communication mechanism is therefore part of FIS architecture rather than an incidental property of a particular AI application.

---

## 3. Direct Interaction and FIS-Mediated Communication

FIS distinguishes between an existing direct interaction channel and a formal FIS-mediated communication channel.

The current Principal–Assistant interaction has a direct conversational interface.

Ordinary Principal–Assistant conversation therefore does not require the FIS-mediated communication mechanism established by this Foundation.

The primary purpose of the current communication architecture is to enable communication where the required direct participant channel does not exist, particularly between separate Worker instances.

The distinction is:

```text
Existing direct channel
        ↓
Direct interaction

No suitable direct channel
        ↓
FIS-mediated communication
```

The existence of a Session Type does not by itself require use of the FIS communication transport.

---

## 4. Communication Participants

A **Participant** is an entity that is formally involved in a communication relationship.

The foundational Participant Types are:

```text
Principal
Assistant
Worker
```

Participant identity SHALL remain distinct from communication mechanics.

A participant is identified by the applicable FIS identity framework.

For Workers, the canonical Worker Role ID established by `FIS-FOUND-002` remains the authoritative role identifier.

The communication system SHALL NOT redefine Worker identity.

---

## 5. Worker Communication Equality

All Workers SHALL use the same fundamental FIS communication architecture unless a higher-authority rule establishes an explicit exception.

Communication architecture is therefore Worker-role-agnostic at the protocol level.

A Worker does not receive a different fundamental communication language merely because of its specialized role.

However:

> **Communication protocol equality does not imply equality of authority, permission, capability, responsibility, or expertise.**

A Worker may be capable of communicating through a particular Communication Type without being authorized to use that Communication Type with every participant or for every purpose.

Applicable authority, role, responsibility, routing, and permission rules SHALL be established by the applicable FIS architecture.

The communication foundation therefore separates:

```text
Communication Capability
Communication Permission
Communication Authority
Communication Responsibility
```

These concepts SHALL NOT be treated as interchangeable.

---

## 6. Assistant Communication Role

The Assistant is a distinct FIS participant role and is not merely another Worker.

The Assistant may communicate with Workers using the same fundamental Communication Types available to other participants where applicable.

The Assistant additionally has system-level responsibilities established by the FIS participant framework and later communication architecture.

These responsibilities may include:

- initiating Assistant–Worker communication;
- coordinating Worker communication;
- mediating Worker–Worker communication;
- preserving communication continuity;
- and performing communication-related system responsibilities assigned by higher-authority FIS rules.

These additional responsibilities do not make the Assistant a Worker.

The detailed operational responsibilities of the Assistant are outside this Foundation and are addressed by applicable later resources, including `FIS-FOUND-007`.

---

## 7. Session

A **Session** is a bounded period of active interaction between defined Participants, established for continuity and operational state tracking.

A Session identifies the continuing interaction relationship rather than every individual exchange occurring within it.

A Session therefore answers:

> **Who is engaged with whom in this operational interaction?**

A Session MAY contain multiple formal Communications.

A Session MAY also contain ordinary interaction that does not require formal FIS-mediated communication.

The formal Session Types are defined in Section 8.

---

## 8. Session Types

FIS recognizes the following foundational Session Types:

```text
PA
PW
AW
WAW
PAW
```

### 8.1 PA — Principal–Assistant

A direct interaction between the Principal and Assistant.

```text
Principal
    ↕
Assistant
```

PA is a recognized Session Type for session tracking and system continuity.

Ordinary PA interaction does not require the FIS-mediated communication mechanism because the Principal and Assistant already possess a direct conversational interface.

PA is therefore primarily a Session concept within the current communication architecture rather than a requirement to use a communication transport.

### 8.2 PW — Principal–Worker

A direct interaction between the Principal and a Worker without the Assistant being an active communication participant.

```text
Principal
    ↕
Worker
```

PW is a formally recognized Session Type even where the current implementation does not provide a suitable direct communication mechanism.

The current inability to execute PW conveniently SHALL NOT invalidate the Session Type.

If the Assistant is required to participate in the interaction, the interaction SHALL instead be established under the applicable PAW model.

### 8.3 AW — Assistant–Worker

An interaction between the Assistant and a Worker.

```text
Assistant
    ↕
Worker
```

AW is the primary Session Type for Assistant-directed specialist Worker communication.

### 8.4 WAW — Worker-to-Worker Interaction

An interaction whose Participants are two Workers.

```text
Worker A
    ↕
Worker B
```

The Assistant mediates WAW communication as an FIS system rule.

The Assistant is not thereby added as a communication Participant.

Therefore:

```yaml
session_type: WAW
participants:
  - Worker A
  - Worker B
```

is sufficient to establish the participating Workers.

The mediation mechanism is an architectural rule and does not need to be repeated in participant-facing communication metadata.

### 8.5 PAW — Principal–Assistant–Worker

An interaction involving the Principal, Assistant, and one or more Workers where Worker involvement is explicitly established as part of the initial Session.

```text
Principal
    ↕
Assistant
    ↕
Worker
```

PAW is distinguished by its initialization condition.

A PAW Session SHALL be established when the Principal explicitly indicates at Session initialization that Worker participation is part of that Session.

For example, a future Login mechanism MAY represent this condition as:

```text
Login PAW
```

The exact trigger syntax is outside this Foundation.

Once established as PAW, the interaction remains one Session for the purposes of Session tracking, even though formal Worker communications may occur within it.

---

## 9. PAW Initialization Boundary

Worker involvement alone does not retroactively convert an existing PA Session into PAW.

The distinction is:

```text
Login PAW
    ↓
PAW Session
```

versus:

```text
Login
    ↓
PA Session
    ↓
Worker becomes necessary
    ↓
Separate Worker Session(s)
```

If a Worker is introduced after a PA Session has already been established without PAW initialization, the existing PA Session SHALL remain distinct.

The resulting Worker interaction SHALL use its applicable independent Session Type, such as AW or WAW.

Multiple Sessions MAY therefore remain active simultaneously.

---

## 10. Session and Communication Relationship

A Session and a Communication are related but distinct concepts.

A Session represents continuing interaction context.

A Communication represents a formally identifiable exchange with a distinct communicative purpose occurring within that context.

The conceptual relationship is:

```text
Session
    │
    ├── Communication
    ├── Communication
    └── Communication
```

A Communication SHALL belong to one Session.

A Session MAY contain multiple Communications.

Not every ordinary conversational exchange constitutes a formal Communication.

This distinction prevents the communication system from treating every individual sentence or message as a separately tracked communication object.

---

## 11. Communication

A **Communication** is a formally identifiable FIS-mediated exchange between Participants that has a distinct communicative purpose and may require defined handling, acknowledgement, outcome, or persistence.

Communication is therefore not synonymous with:

- a Session;
- a Message;
- a topic;
- or every conversational statement.

A Communication exists to represent a purposeful exchange that the FIS communication architecture needs to recognize.

---

## 12. Message

A **Message** is the actual information content transmitted as part of a Communication.

The conceptual relationship is:

```text
Session
    ↓
Communication
    ↓
Message(s)
```

A Communication MAY contain multiple Messages when its Communication Type requires an exchange.

The actual Message or payload SHALL remain distinct from communication metadata.

The communication metadata identifies the exchange.

The payload contains the transmitted content.

The exact metadata and payload format SHALL be established by later communication specifications and templates.

---

## 13. Communication Types

The foundational Communication Types are:

```text
Command
Query
Fetch
Reporting
Conversation
Handoff
Escalation
```

Communication Types describe the purpose and expected handling of a formal FIS-mediated exchange.

The list MAY be expanded by later approved FIS resources.

A later Communication Type MUST NOT silently redefine an existing Communication Type.

---

## 14. Command

A **Command** is a communication in which one Participant directs another Participant to perform an action, adopt a state, follow a directive, or execute a defined task.

Command is divided into two foundational subtypes:

```text
Command.Directive
Command.Task
```

### 14.1 Command.Directive

A Directive communicates an instruction whose required outcome is compliance, acknowledgement, state change, or continued adherence rather than completion of a separately defined task.

Examples include:

- adopting an approved rule;
- changing an operational state;
- following an established procedure;
- or applying an approved instruction.

A Directive normally requires a receipt or acknowledgement that the instruction has been received and recognized.

Receipt acknowledgement SHALL NOT be interpreted as task completion.

### 14.2 Command.Task

A Task Command directs a Participant to execute a defined task.

A Task Command normally requires:

```text
Command
    ↓
Receipt
    ↓
Execution
    ↓
Outcome
```

The outcome MAY indicate successful completion, partial completion, failure, blocking, or another approved state.

The detailed acknowledgement and outcome protocol SHALL be established later.

---

## 15. Query

A **Query** is a formal information-seeking Communication initiated by a specific question and intended to obtain an answer, clarification, or bounded set of related information.

A Query is intentionally not defined by a fixed number of Messages.

A Query remains a Query while its exchanges retain continuity of purpose around the original information request.

Follow-up questions MAY remain part of the same Query when they clarify or extend the original question without becoming an independent communicative purpose.

A Query SHOULD be treated as a Conversation when the interaction becomes substantially broader, open-ended, or independently purposeful rather than remaining a bounded information-seeking exchange.

The Assistant or applicable communication authority SHALL determine the transition according to later definitions and rules.

---

## 16. Fetch

A **Fetch** is a formal Communication requesting retrieval of specified information or data.

The fundamental distinction is:

```text
Query
    ↓
seeks an answer or clarification

Fetch
    ↓
requests retrieval of specified information
```

A Fetch does not inherently require a semantic acknowledgement from the recipient.

A technical delivery or receipt state MAY exist independently of a semantic acknowledgement.

The exact distinction between transport receipt and semantic acknowledgement SHALL be defined later.

---

## 17. Reporting

**Reporting** is a formal Communication in which a Participant proactively delivers information to another Participant without requiring a preceding information request.

The fundamental distinction is:

```text
Fetch
    ↓
information requested by recipient

Reporting
    ↓
information proactively supplied by sender
```

Reporting does not inherently require semantic acknowledgement.

A delivery state MAY still be maintained by the underlying communication mechanism.

---

## 18. Conversation

A **Conversation** is a formal FIS-mediated Communication involving extended, open-ended, broad, or otherwise non-specialized interaction between two or more Participants.

Conversation is intentionally broad.

It may include:

- discussion;
- analysis;
- clarification;
- idea development;
- multiple related topics;
- topic transitions;
- and extended exchanges that cannot reasonably be represented by a narrower Communication Type.

Conversation is not required to have a fixed topic, fixed length, or fixed number of Messages.

A direct Principal–Assistant conversation remains outside the FIS-mediated communication transport even though Conversation is a valid Communication Type in the general FIS communication model.

---

## 19. Handoff

A **Handoff** is a formal Communication through which responsibility, context, work, or an operational item is transferred from one Participant to another.

A Handoff may contain or initiate another Communication Type, such as a Command.Task.

The distinction is:

```text
Command
    ↓
"Perform this."

Handoff
    ↓
"This responsibility/context/work now moves to you."
```

The detailed Handoff payload and acknowledgement protocol SHALL be established later.

---

## 20. Escalation

An **Escalation** is a formal Communication through which an unresolved issue, exception, decision, or responsibility is transferred to a Participant with more appropriate authority, capability, or responsibility for resolution.

The distinction is:

```text
Handoff
    ↓
transfer of responsibility or context

Escalation
    ↓
transfer because the current level cannot appropriately resolve the matter
```

The detailed Escalation protocol SHALL be established later.

---

## 21. Communication Outcome

A formal Communication MAY produce an outcome.

The foundational outcome concept distinguishes successful and unsuccessful communication without yet fixing the complete state vocabulary.

Possible outcome concepts include:

```text
Successful
Partial
Failed
Blocked
Timeout
Unresolved
```

These are conceptual states only at this Foundation level.

The authoritative outcome vocabulary, transition rules, retry rules, and persistence behaviour SHALL be established by later resources.

---

## 22. Acknowledgement

An **Acknowledgement** is an explicit indication that a required communication state or event has been recognized by the receiving Participant.

Acknowledgement SHALL NOT automatically mean completion.

The foundational distinction is:

```text
Receipt
    ↓
"I received this."

Completion
    ↓
"I completed what this required."
```

A Communication Type MAY require:

- no semantic acknowledgement;
- receipt acknowledgement;
- completion acknowledgement;
- or another later-defined acknowledgement state.

The detailed acknowledgement protocol SHALL be defined separately.

---

## 23. Communication Failure and Retry

A Communication MAY fail to produce its required outcome.

The communication architecture SHALL support the conceptual existence of:

```text
Failure
Retry
Timeout
Blocking
Unresolved Outcome
```

A failed Communication MAY be retried when the applicable Communication Type and rules permit retry.

A retry SHALL remain associated with the original communicative intent and Session context.

A retry MUST NOT silently become an unrelated Communication.

The maximum retry count, retry timing, timeout behaviour, escalation thresholds, and Session-extension rules SHALL be established later.

---

## 24. Communication Identity

A Communication requires an identity distinct from the identity of the Session containing it.

The distinction is:

```text
Session ID
    ↓
identifies the continuing interaction context

Communication ID
    ↓
identifies one formal Communication
```

A Session MAY contain multiple Communications and therefore a Communication ID MUST NOT simply be treated as the Session ID.

The exact Communication ID structure, counter, encoding, uniqueness scope, and relationship to Session ID SHALL be established by later Definitions and Templates.

---

## 25. Communication Metadata and Payload

A formal Communication SHALL conceptually consist of:

```text
Communication Metadata
        +
Communication Payload
```

Metadata identifies and describes the exchange.

The payload contains the actual transmitted information.

The payload SHALL NOT be unnecessarily embedded within the structural metadata definition.

This separation permits:

- machine-readable communication metadata;
- independently structured payloads;
- natural-language messages;
- future non-text payloads;
- and later transport-independent implementations.

The exact metadata schema SHALL be established separately.

---

## 26. Participant-Facing Information

Communication metadata SHALL contain only information necessary or appropriate for the receiving Participant and applicable FIS processing.

A Participant does not need to be exposed to communication mechanics that it is not responsible for controlling.

For example, a Worker participating in a WAW Session does not need participant-facing metadata explaining that the Assistant mediates the communication.

The architectural rule is established by this Foundation.

Communication implementation details such as:

- transport mechanism;
- physical routing;
- storage backend;
- human transport operation;
- queue implementation;
- or intermediary mechanics

SHALL remain system-level information unless explicitly required by a later rule.

---

## 27. Mediated Worker-to-Worker Communication

When two Workers communicate through the FIS communication system:

```text
Worker A
    ↕
Worker B
```

the Assistant acts as the system-level mediator.

The Assistant's mediation does not make the Assistant a Participant of the WAW Session.

The Participants remain:

```text
Worker A
Worker B
```

This rule exists so that communication metadata represents the actual communicative relationship rather than the mechanics used to transport it.

---

## 28. Communication Logistics Boundary

This Foundation establishes the existence and conceptual role of FIS communication but does not establish how a Communication is transported, stored, retrieved, delivered, acknowledged, retried, or automated.

The logistics layer SHALL implement the communication architecture established by this Foundation without redefining its fundamental concepts.

`FIS-FOUND-006` establishes the foundational communication logistics layer, including the mechanisms by which formal FIS Communications are expected to move between Participants.

The current manual, triggered, API, MCP, database, or other transport mechanisms are implementation concerns and SHALL NOT be treated as foundational Communication Types or Session Types.

The exact logistics model remains outside this Foundation.

---

## 29. Communication and Session Independence

Session state and Communication state are distinct.

A Session MAY remain active while an individual Communication is:

```text
Pending
Processing
Completed
Failed
```

A Communication MAY therefore change state without automatically closing the Session.

Likewise, closing a Communication does not necessarily close its containing Session.

The exact Session and Communication state machines SHALL be established by later resources.

---

## 30. Communication Boundaries

A Communication begins when a formal FIS-mediated communicative purpose is established and the Communication is initiated according to its applicable rules.

A Communication ends when its communicative purpose has reached an applicable terminal state, such as:

```text
Completed
Failed
Blocked
Unresolved
```

or another approved terminal state.

The precise lifecycle rules SHALL be defined later.

A change of topic does not automatically require a new Session.

A change of communicative purpose MAY require a new Communication within the same Session.

---

## 31. Architectural Separation

FIS communication is intentionally separated into conceptual layers:

```text
FIS-FOUND-005
Communication Foundation
        ↓
Communication Definitions / Rules
        ↓
Communication Templates
        ↓
FIS-FOUND-006
Communication Logistics Foundation
        ↓
Communication Logic / Implementation
        ↓
Persistent Runtime State
```

This Foundation establishes the communication concepts and boundaries that the later logistics layer must implement.

The communication system SHALL NOT be designed by beginning with the capabilities of a particular storage or transport tool.

Implementation mechanisms SHALL implement approved communication architecture rather than define it.

---

## 32. Relationship to FIS-FOUND-002

`FIS-FOUND-002` establishes the Principal, Assistant, and Worker participant framework and identifies communication as controlled FIS architecture.

It also establishes that authority, communication permission, expertise, responsibility, execution capability, and information visibility are distinct concepts.

This Foundation extends that framework by establishing the fundamental communication model.

It does not redefine:

- Worker identity;
- Worker role;
- role specialization;
- authority;
- resource dependency;
- initialization;
- or participant governance.

Those remain governed by the applicable foundational resources.

---

## 33. Relationship to FIS-FOUND-003

`FIS-FOUND-003` governs official FIS documentation.

This document is a Foundation document and SHALL therefore comply with the official documentation lifecycle, metadata, versioning, drafting, locking, and Repository requirements established by `FIS-FOUND-003`.

No communication architecture rule established here changes the documentation rules of `FIS-FOUND-003`.

---

## 34. Relationship to FIS-FOUND-006

`FIS-FOUND-006` establishes the foundational logistics of FIS communication.

This Foundation establishes **what communication is** and the conceptual relationships that communication logistics must support.

The intended dependency is:

```text
FIS-FOUND-005
Communication Foundation
        ↓
FIS-FOUND-006
Communication Logistics Foundation
```

`FIS-FOUND-006` SHALL NOT redefine the fundamental communication concepts established here.

It SHALL define how those concepts are operationally transported, delivered, retrieved, acknowledged, tracked, or otherwise executed according to its own scope.

Formal FIS syntax and logic are not established by this relationship. Those belong to the later resource now designated for that purpose.

---

## 35. Relationship to FIS-FOUND-007

`FIS-FOUND-007` establishes Assistant operational responsibilities that may depend upon communication logistics and communication events.

The dependency direction is therefore:

```text
FIS-FOUND-005
Communication Foundation
        ↓
FIS-FOUND-006
Communication Logistics Foundation
        ↓
FIS-FOUND-007
Assistant Operational Foundation
```

`FIS-FOUND-007` SHALL NOT redefine the fundamental communication model established by this Foundation.

Its operational behaviour SHALL depend upon the applicable communication and logistics rules established by the preceding resources.

---

## 36. Foundation Boundary

This document deliberately does not define the complete implementation of FIS communication.

The following remain future work:

- communication package schema;
- Communication ID encoding;
- Session ID integration rules;
- acknowledgement protocol;
- delivery protocol;
- retry protocol;
- failure-state vocabulary;
- trigger words;
- trigger execution;
- communication storage;
- communication queue;
- transport implementation;
- API implementation;
- MCP implementation;
- database implementation;
- message routing;
- automated Worker communication;
- communication security;
- and complete communication state machines.

These subjects SHALL be established in the appropriate later resources.

The purpose of this Foundation is to establish the stable answer to:

> **What is communication inside FIS, why does it exist, who participates, and what fundamental forms can it take?**

---

## Changelog

### v1.0.0

- Finalized the FIS Communication Foundation after iterative architectural drafting.
- Established FIS-mediated communication as the formal mechanism for participant interaction where an appropriate direct participant channel does not exist.
- Explicitly excluded ordinary Principal–Assistant interaction from the FIS-mediated communication transport because the Principal and Assistant already have a direct interaction interface.
- Established the foundational Participant Types: Principal, Assistant, and Worker.
- Established Worker equality at the communication protocol level while preserving distinctions between communication capability, permission, authority, responsibility, and expertise.
- Established the Assistant as a distinct FIS participant role rather than a Worker.
- Established Session as a bounded period of active interaction between defined Participants.
- Established the Session Types PA, PW, AW, WAW, and PAW.
- Established PA as a recognized Session Type that does not require the FIS-mediated communication transport.
- Established PW as a formally recognized Session Type while leaving its current direct implementation limitations outside the Foundation.
- Established AW as the primary Assistant–Worker Session Type.
- Established WAW as Worker-to-Worker interaction mediated by the Assistant without making the Assistant a Participant.
- Established PAW as a Session Type in which Worker involvement is explicitly established at Session initialization.
- Established that later Worker involvement does not retroactively convert an existing PA Session into PAW.
- Established the distinction between Session, Communication, and Message.
- Established that a Session MAY contain multiple formal Communications while not every ordinary interaction constitutes a formal Communication.
- Established Communication as a formally identifiable FIS-mediated exchange with a distinct communicative purpose.
- Established the foundational Communication Types: Command, Query, Fetch, Reporting, Conversation, Handoff, and Escalation.
- Established Command subtypes: Command.Directive and Command.Task.
- Established intent continuity rather than a fixed message count as the boundary for Query, with broader or independently purposeful interaction potentially becoming Conversation.
- Established Fetch as specified information retrieval and Reporting as proactive information delivery.
- Established Conversation as an extended, open-ended, or broad formal FIS-mediated interaction.
- Established Handoff as transfer of responsibility, context, work, or an operational item.
- Established Escalation as transfer of an unresolved matter to a Participant with more appropriate authority, capability, or responsibility.
- Established acknowledgement as distinct from completion.
- Established foundational Communication outcome, failure, timeout, blocking, unresolved, and retry concepts without fixing their final state vocabulary or implementation.
- Established Communication identity as distinct from Session identity.
- Established separation of Communication Metadata from Communication Payload.
- Established participant-facing information boundaries so implementation mechanics are not unnecessarily exposed to Participants.
- Established the Assistant as the system-level mediator for WAW without adding the Assistant to the WAW participant set.
- Re-scoped FIS-FOUND-006 as the Communication Logistics Foundation responsible for operational transport, delivery, retrieval, acknowledgement, tracking, and execution of the communication architecture established here.
- Established the dependency direction FIS-FOUND-005 → FIS-FOUND-006 → FIS-FOUND-007.
- Explicitly kept transport mechanisms, triggers, queues, storage, APIs, MCP, database implementation, routing, and complete communication state machines outside this Foundation.
- Preserved implementation independence so later logistics mechanisms implement the approved communication architecture rather than define it.

