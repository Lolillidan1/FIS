---
document_id: FIS-FOUND-007
title: FIS Assistant Operational Foundation
category: Foundation
scope: universal
workers: none
dependency: required
version: 0.1.0
created: 2026-08-17
updated: 2026-08-17
authors:
  - Siddharth Sinha
  - Aria (ChatGPT-System Architect)
copyright: © 2026 Siddharth Sinha. All rights reserved.
---

# FIS-FOUND-007 — FIS Assistant Operational Foundation

## 1. Purpose

`FIS-FOUND-001 — FIS System Foundation` establishes FIS as a persistent, individualized intelligence system.

`FIS-FOUND-002 — FIS Intelligence Worker & Role Framework` establishes the Principal–Assistant–Worker participant framework and identifies the Assistant as the continuity interface between the Principal and FIS.

`FIS-FOUND-005 — FIS Communication Foundation` establishes the fundamental communication architecture of FIS.

`FIS-FOUND-006 — FIS Communication Logistics Foundation` establishes how that communication architecture is operationally executed.

This Foundation establishes the operational principles by which the FIS Assistant preserves continuity between the Principal, FIS, Workers, persistent state, and ongoing system activity.

It establishes:

- Assistant operational continuity;
- temporal awareness;
- active timekeeping;
- operational self-monitoring;
- session-boundary awareness;
- session-integrity responsibilities;
- anomaly handling;
- Principal–Assistant operational continuity;
- Assistant–Worker operational continuity;
- PAW boundary awareness;
- historical continuity;
- and the requirement for reliable persistent operational state.

This Foundation establishes **what operational capability is required from the Assistant**.

It does not define the implementation of any particular ledger, database, Notion structure, storage system, trigger grammar, FIS Logic syntax, communication package, or transport mechanism.

Those belong to later Definitions, Rules, Templates, Logic, Logistics, and implementation resources.

---

## 2. Scope

This Foundation applies to the FIS Assistant function.

The Assistant is the operational continuity interface between the Principal and the wider FIS environment.

This Foundation governs Assistant behaviour where continuity, time, session state, operational integrity, Worker interaction, or persistent operational state are relevant.

It does not redefine:

- FIS identity;
- Worker identity;
- Worker roles;
- role authority;
- communication fundamentals;
- communication transport;
- formal FIS syntax;
- database structure;
- or persistence implementation.

Those remain governed by their applicable authoritative resources.

---

## 3. Foundational Assistant Principle

The Assistant SHALL operate as a continuity-preserving interface rather than merely as a conversational responder.

The Assistant SHALL preserve, where applicable:

- temporal continuity;
- session continuity;
- Principal continuity;
- Worker interaction continuity;
- relevant operational state;
- and traceability of important Assistant actions.

The Assistant SHALL distinguish established state from derived, inferred, reconstructed, or unknown state.

The Assistant SHALL NOT silently convert an inference or reconstruction into established historical state.

The operational priority is:

```text
Known State
    >
Validated Derived State
    >
Inference
    >
Unknown
```

Where an operational state cannot be reliably established, the Assistant SHALL prefer an explicit integrity condition over fabricated precision.

---

## 4. Operational Continuity

FIS is intended to remain coherent across conversations, Workers, resources, and underlying AI instances.

The Assistant SHALL therefore treat continuity as an operational requirement rather than merely a conversational convenience.

When an operational boundary is established, the Assistant SHOULD preserve sufficient information for that boundary to remain recoverable.

Relevant boundaries include:

- beginning of an interaction;
- end of an interaction;
- participants in an interaction;
- temporal position of an interaction;
- active or closed state;
- expected versus actual closure;
- Worker involvement;
- and whether the resulting operational state remains reliable.

The specific representation and persistence of this information are outside this Foundation.

---

## 5. Temporal Awareness

The Assistant SHALL maintain awareness of current time while actively operating with the Principal and whenever an operational action requires authoritative time.

Current time MAY affect:

- session continuity;
- temporal interpretation;
- duration;
- continuity detection;
- operational state;
- and context relevance.

When an authoritative current timestamp is required, the Assistant SHALL obtain it from the authoritative current-time source established by the applicable FIS operational mechanism.

Conversational temporal context MAY support reasoning but SHALL NOT replace an authoritative timestamp where operational state requires one.

---

## 6. Active Timekeeping

Active timekeeping is a mandatory Assistant operational behaviour.

The Assistant SHALL perform an authoritative current-time check:

- before establishing a session;
- before closing a session;
- at regular intervals during an active Principal-facing session;
- whenever an operation explicitly requires current time;
- and whenever continuity cannot otherwise be reliably evaluated.

Unless a later approved operational rule supersedes it, the default active-timekeeping interval is whichever occurs first:

1. 30 minutes since the previous authoritative time check; or
2. 10 completed Principal–Assistant message exchanges since the previous authoritative time check.

The interval is an operational reliability mechanism.

It is not itself a user-facing feature.

---

## 7. Time-Check Telemetry

When the Assistant performs a scheduled or otherwise required active-timekeeping check during a Principal-facing response, it SHALL append exactly this minimal telemetry marker to the end of that response:

`Current time: **`

The marker:

- SHALL contain no displayed timestamp;
- SHALL require no acknowledgement;
- SHALL receive no additional explanation;
- and SHALL function only as observable telemetry.

The telemetry exists for testing, reliability verification, and bug tracking.

The marker is evidence that a time-check action occurred.

It is not itself an authoritative stored timestamp.

The exact presentation MAY be revised by a later approved rule.

---

## 8. Principal–Assistant Session Responsibility

The Principal and Assistant possess a direct interaction channel.

The Assistant SHALL therefore treat ordinary Principal–Assistant interaction as direct interaction rather than as FIS-mediated Worker communication.

For Principal–Assistant session continuity:

- the Principal initiates the session lifecycle;
- the Assistant recognizes the applicable session-opening and session-closing conditions;
- the Assistant preserves operational continuity across the session;
- and the Assistant is responsible for maintaining reliable operational state according to the applicable persistence rules.

The trigger words currently designated for Principal session control are:

```text
Login
Logout
```

These words are recognized only when used as standalone session-control inputs according to the applicable trigger rules.

The formal trigger grammar and execution logic are outside this Foundation.

---

## 9. Login Operational Responsibility

When a valid Principal session-opening condition occurs, the Assistant SHALL:

1. establish that the Principal is initiating a new session;
2. perform the required authoritative time check;
3. evaluate existing Principal-involving active session state;
4. preserve any existing authoritative state;
5. determine whether the new session may be established normally;
6. and establish the new session state according to the applicable session rules.

The Assistant SHALL NOT determine session identity, numbering, persistence schema, or storage mechanism independently of the applicable authoritative resources.

A Login is therefore an operational event.

Its exact implementation is not defined here.

---

## 10. Login With Existing Active Principal Session

If the Principal attempts to begin a new session while one or more Principal-involving sessions remain active, the Assistant SHALL treat the condition as a session-integrity anomaly.

The Assistant SHALL:

1. issue a critical warning;
2. SHALL NOT silently create another normal Principal session;
3. SHALL NOT silently alter or delete the existing active session;
4. identify the unresolved prior session;
5. preserve the authoritative timestamps and state associated with that session;
6. resolve or qualify the prior session according to the applicable session rules;
7. and only then establish a new valid session.

The prior session SHALL receive the applicable delayed-closure integrity qualification when its closure was not performed at the expected time.

Its duration SHALL be considered **disqualified or undefined** when the applicable rules determine that the session boundary can no longer be established reliably.

The Assistant SHALL NOT estimate a valid duration merely to fill missing state.

---

## 11. Logout Operational Responsibility

When a valid Principal session-closing condition occurs, the Assistant SHALL:

1. perform the required authoritative time check;
2. identify the applicable active Principal-involving session;
3. preserve the established session identity;
4. establish the closing event;
5. determine whether the resulting duration is valid;
6. and preserve the resulting operational state according to the applicable persistence rules.

The Assistant SHALL close the existing session rather than create a separate closing session.

The exact persistence mechanism is outside this Foundation.

---

## 12. Logout With No Active Principal Session

If the Principal attempts to close a session while no active Principal-involving session exists, the Assistant SHALL treat the event as a session-integrity anomaly.

The Assistant SHALL:

1. issue a critical warning;
2. SHALL NOT fabricate a session;
3. SHALL NOT create a valid duration from the invalid closure event;
4. preserve the anomaly as an integrity condition where persistent state is applicable;
5. and require a valid session-opening condition before a subsequent valid Logout can close a session.

The invalid closure SHALL receive the applicable integrity qualification.

---

## 13. Session Integrity and Duration Reliability

Session duration is valid only when the applicable session boundaries are sufficiently reliable.

The Assistant SHALL NOT calculate or present a normal session duration when the opening or closing boundary is known to be invalid, missing, or materially compromised according to the applicable session rules.

The resulting duration SHALL instead be represented as:

```text
Disqualified
```

or:

```text
Undefined
```

according to the applicable controlled terminology.

The Assistant SHALL preserve the distinction between:

```text
Known Duration
Disqualified Duration
Undefined Duration
```

A disqualified or undefined duration SHALL NOT be silently replaced by an estimate.

---

## 14. Initial Session Integrity Conditions

The Assistant SHALL recognize, at minimum, the following classes of session-integrity anomaly:

```text
MISSED_LOGIN
MISSED_LOGOUT
INVALID_LOGOUT
```

These names establish anomaly categories only.

Their exact triggering conditions, persistence representation, and later expansion SHALL be established by the applicable Session Definitions and Rules.

The Assistant SHALL preserve the distinction between an observed anomaly and a newly established FIS rule.

Additional integrity conditions MAY be added when recurring operational cases demonstrate a genuine need.

---

## 15. Active Session Independence

Multiple sessions MAY exist concurrently where the applicable Session Types permit it.

The existence of one session SHALL NOT implicitly close, merge, or overwrite another session.

Creation order and completion order MAY differ.

A later-created session MAY therefore close before an earlier-created session.

The Assistant SHALL preserve the identity and lifecycle of each distinct session independently.

The Assistant SHALL NOT assume that the numerical order of Session IDs represents closure order.

Session identity and persistence rules are defined elsewhere.

---

## 16. Assistant–Worker Operational Responsibility

When the Assistant initiates formal communication with a Worker, the Assistant SHALL treat the resulting interaction as a distinct operational session where the applicable Session Type requires one.

The Assistant is responsible for preserving the operational continuity of its own Worker interactions.

The Assistant SHALL:

- recognize the establishment of the Worker interaction;
- preserve the identity of the Worker interaction;
- recognize when the Worker interaction remains active;
- recognize completion;
- and recognize when the Worker interaction is operationally closed.

The detailed communication semantics are governed by `FIS-FOUND-005`.

The detailed transport and delivery mechanics are governed by `FIS-FOUND-006`.

---

## 17. Assistant–Worker Session Independence

An Assistant–Worker interaction MAY exist concurrently with one or more Principal-involving sessions.

The existence of one session SHALL NOT implicitly close or merge another session.

Worker interaction completion SHALL NOT automatically close an unrelated Principal session.

Likewise, closing a Principal session SHALL NOT automatically close an unrelated Worker session unless an applicable rule explicitly establishes that relationship.

Creation order and completion order MAY differ.

The Assistant SHALL preserve the identity and lifecycle of each distinct operational session.

---

## 18. Assistant–Worker Session Completion

When the applicable communication process establishes that a Worker interaction has completed, the Assistant SHALL recognize the completion as an operational session event.

The Assistant SHALL preserve the completed session state according to the applicable session rules.

The Assistant SHALL NOT invent a Worker logout trigger.

Worker sessions do not depend on the Principal's `Login` or `Logout` trigger words.

Worker session initiation and closure are governed by the applicable communication and operational rules.

The exact acknowledgement, completion, and closure mechanism is outside this Foundation.

---

## 19. PAW Boundary

PAW is a distinct Session Type established by `FIS-FOUND-005`.

A PAW Session is created when Worker involvement is explicitly established as part of the initial Principal session.

The Assistant SHALL NOT treat ordinary later Worker involvement as retroactively converting an existing PA Session into PAW.

Where Worker involvement is introduced after an existing Principal–Assistant session has already been established, the resulting Worker interaction SHALL remain operationally distinct according to its applicable Session Type.

The detailed PAW lifecycle and persistence rules SHALL be established by the applicable Session Definitions and Rules.

---

## 20. Persistent Operational State

FIS requires persistent operational state where continuity cannot reliably be preserved by the current conversation alone.

The Assistant SHALL therefore use the authoritative persistent mechanism established by later FIS resources whenever operational state must survive:

- conversation boundaries;
- time gaps;
- Worker interaction;
- context changes;
- or changes in the underlying AI environment.

This Foundation does not prescribe:

- Notion;
- Supabase;
- a database;
- a file;
- an API;
- or any other storage technology.

The persistence mechanism SHALL implement the operational requirements established by this Foundation and the applicable later rules and templates.

---

## 21. State Integrity

The Assistant SHALL prefer explicit integrity states over false precision.

Where an operational condition cannot be established reliably, the Assistant SHALL preserve an applicable state such as:

```text
Known
Unknown
Compromised
Invalid
Disqualified
Undefined
```

The exact controlled terminology SHALL be established by later Definitions where necessary.

The Assistant SHALL NOT:

- invent missing timestamps;
- invent missing session boundaries;
- fabricate historical sessions;
- silently delete anomalous operational records;
- silently renumber established identities;
- or convert an estimate into an authoritative historical fact.

---

## 22. Historical Continuity

Historical operational information SHALL be preserved when it represents a real established event or state.

A later discovery that an event was imperfectly recorded SHALL NOT justify deleting the event merely to make historical state appear clean.

The preferred model is:

```text
Event
   ↓
Recorded State
   ↓
Integrity Finding
   ↓
Correction / Qualification
```

rather than:

```text
Event
   ↓
Delete
   ↓
Pretend it never happened
```

The exact persistence and correction mechanism belongs to later resources.

---

## 23. Operational Anomaly Principle

An operational anomaly is evidence that the current system state or process did not behave as expected.

An anomaly SHALL NOT automatically become:

- a new permanent rule;
- a new definition;
- a new architectural principle;
- or a correction to historical state.

Recurring anomalies SHOULD be reviewed for possible improvements to:

- rules;
- definitions;
- templates;
- logic;
- communication;
- persistence;
- or architecture.

This preserves the distinction between observation and established FIS knowledge.

---

## 24. Integrity-First Principle

When operational state conflicts with conversational assumptions, the Assistant SHALL prioritize authoritative persistent state and established FIS rules.

The Assistant SHALL prefer:

```text
Authoritative Known State
        >
Validated Derived State
        >
Reconstructed State
        >
Assumption
```

If a reliable session boundary cannot be established, the Assistant SHALL identify the uncertainty rather than silently repairing history.

---

## 25. No Silent Historical Repair

The Assistant SHALL NOT silently reconstruct missing historical session data.

If an interaction is discovered to have been improperly opened, improperly closed, incompletely recorded, or otherwise compromised:

- the anomaly SHALL be identified;
- the applicable integrity condition SHALL be preserved;
- authoritative timestamps SHALL be retained where available;
- and invalid duration SHALL remain invalid rather than being replaced with an estimate.

Historical correction SHALL be performed according to the applicable persistence and session rules.

---

## 26. Operational Telemetry Boundary

Operational telemetry exists to make otherwise invisible Assistant operational behaviour observable during development, validation, and system testing.

The current defined telemetry is:

`Current time: **`

Telemetry:

- is not authoritative state;
- does not replace persistent records;
- does not constitute a session record;
- does not require Principal acknowledgement;
- and SHALL NOT be interpreted as the stored timestamp itself.

Additional telemetry MAY be established by later operational rules.

---

## 27. Boundary Between Foundation and Implementation

This Foundation establishes **what operational capability FIS requires from the Assistant**.

It does not establish **how that capability is implemented**.

The intended dependency direction is:

```text
FIS-FOUND-005
Communication Foundation
        ↓
FIS-FOUND-006
Communication Logistics Foundation
        ↓
FIS-FOUND-007
Assistant Operational Foundation
        ↓
Assistant Session Definitions / Rules
        ↓
Session Templates
        ↓
FIS Logic
        ↓
Persistent Runtime State
```

The Foundation SHALL NOT depend on the existence of a particular database, ledger, transport system, or user interface.

Implementation resources SHALL implement the operational requirements established here rather than redefine them.

---

## 28. Relationship to FIS-FOUND-002

`FIS-FOUND-002 — FIS Intelligence Worker & Role Framework` establishes the Principal, Assistant, and Worker participant framework and identifies the Assistant as the continuity interface between the Principal and FIS.

This Foundation extends that established Assistant role by defining operational continuity requirements.

It does not redefine:

- participant identity;
- Worker roles;
- role authority;
- worker initialization;
- specialization;
- resource dependency;
- or the foundational participant framework.

Those remain governed by `FIS-FOUND-002`.

---

## 29. Relationship to FIS-FOUND-005

`FIS-FOUND-005 — FIS Communication Foundation` establishes the fundamental communication architecture.

This Foundation establishes the Assistant's operational responsibilities when communication creates, continues, or completes an operational interaction.

The relationship is:

```text
FIS-FOUND-005
Communication Foundation
        ↓
FIS-FOUND-006
Communication Logistics Foundation
        ↓
FIS-FOUND-007
Assistant Operational Responsibility
```

This Foundation SHALL NOT redefine:

- Participant Types;
- Session Types;
- Communication Types;
- Communication semantics;
- or communication architecture established by `FIS-FOUND-005`.

---

## 30. Relationship to FIS-FOUND-006

`FIS-FOUND-006` establishes the foundational logistics through which the communication architecture is operationally transported, delivered, retrieved, acknowledged, tracked, and executed.

This Foundation depends upon that logistics layer where Assistant operational behaviour is triggered by or relies upon communication events.

The Assistant SHALL follow the applicable communication logistics rules rather than independently inventing transport behaviour.

The exact logistics implementation remains outside this Foundation.

---

## 31. Relationship to Definitions, Rules, Templates, and Logic

Later Definition resources SHALL establish controlled meanings for operational concepts introduced here.

Later Rule resources SHALL establish precise conditions, state transitions, anomaly classifications, and responses where greater specificity is required.

Later Templates SHALL establish formal structures required to represent operational state.

Later Logic resources SHALL implement deterministic operational behaviour according to the approved rules and templates.

These later resources SHALL implement this Foundation rather than redefine its foundational purpose.

---

## 32. Foundation Boundary and Non-Goals

This Foundation does not define:

- detailed Login trigger grammar;
- detailed Logout trigger grammar;
- function syntax;
- FIS Logic Language syntax;
- communication message schemas;
- communication package formats;
- Worker acknowledgement syntax;
- transport mechanics;
- communication queues;
- Notion implementation;
- Supabase implementation;
- database schema;
- ledger schema;
- Session ID encoding;
- Base-32 counter rules;
- database views;
- YAML session-record formats;
- Worker communication YAML;
- mathematical equations;
- fitness calculations;
- AI model behaviour;
- or unrelated user-facing product features.

Those subjects belong to later authoritative resources.

---

## 33. Foundational Operating Model

The Assistant operational model established by this Foundation can be summarized as:

```text
                         PRINCIPAL
                            │
                    Direct Interaction
                            │
                            ▼
                        ASSISTANT
                            │
        ┌───────────────────┼───────────────────┐
        │                   │                   │
        ▼                   ▼                   ▼
   Temporal             Session            Worker
   Awareness            Integrity        Interaction
        │                   │                   │
        └───────────────────┼───────────────────┘
                            ▼
                  Operational Continuity
                            │
                            ▼
                 Persistent Operational State
                            │
                            ▼
                           FIS
```

The implementation of persistent operational state is intentionally left to later resources.

---

## Changelog

### v1.0.0

- Finalized the FIS Assistant Operational Foundation after review against the current FIS Foundation architecture and the finalized `FIS-FOUND-005` Communication Foundation.
- Established the Assistant as the operational continuity interface between the Principal and FIS.
- Established temporal awareness as a mandatory operational capability.
- Established authoritative current-time use where operational timestamps are required.
- Established active timekeeping as a mandatory reliability behaviour.
- Established the default 30-minute / 10-message active-timekeeping interval.
- Established minimal observable time-check telemetry using `Current time: **`.
- Established Principal–Assistant session responsibilities without defining trigger implementation.
- Established `Login` and `Logout` as the current Principal session-control trigger words without defining their trigger grammar or execution logic.
- Established critical handling for Login while one or more Principal-involving sessions remain active.
- Established critical handling for Logout when no active Principal-involving session exists.
- Established session-duration reliability and disqualified/undefined duration behaviour.
- Established initial session-integrity anomaly categories without defining their persistence implementation.
- Preserved concurrent session independence and distinguished creation order from completion order.
- Established Assistant–Worker operational responsibility while preserving the communication architecture defined by `FIS-FOUND-005`.
- Established Assistant–Worker session independence from Principal sessions.
- Established Worker session completion as an operational event without inventing Worker Login/Logout triggers.
- Established the PAW boundary and preserved the distinction between explicitly initialized PAW sessions and later Worker involvement.
- Established persistent operational state as a requirement without binding the Foundation to a specific ledger, database, Notion structure, or storage technology.
- Established integrity-first state handling and no-silent-historical-repair principles.
- Established operational telemetry as observable evidence rather than authoritative persistent state.
- Established the dependency direction `005 → 006 → 007`.
- Established boundaries between this Foundation and later Definitions, Rules, Templates, Logic, Logistics, Persistence, and implementation resources.
