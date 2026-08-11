---

document_id: FIS-FOUND-003
title: Documentation Specification
category: Foundation
scope: universal
workers: none
dependency: none
version: 0.3.0
created: 2026-08-08
updated: 2026-08-11
authors:

* Siddharth Sinha
* Aria (ChatGPT-System Architect)
  copyright: © 2026 Siddharth Sinha. All rights reserved.

---

# FIS-FOUND-003 — Documentation Specification

## 1. Purpose

This document defines the official documentation standards for the Fitness Intelligence System (FIS).

Its purpose is to ensure that every official document inside the FIS Repository remains consistent, readable, maintainable, traceable, and suitable for both human understanding and AI interpretation.

This specification governs how official FIS documents are:

* structured;
* identified;
* classified;
* versioned;
* stored;
* revised;
* referenced;
* and validated for documentation compliance.

It does not define the technical content of individual documents.

Any documentation rule introduced during the development of FIS MUST be formally established in this document before it becomes a Repository-wide documentation rule.

This document therefore acts as the **documentation constitution of the FIS Repository**.

---

## 2. Scope

This specification applies to **every official document inside the FIS Repository**.

A file or document outside the Repository is outside the scope of this specification unless it is subsequently brought into the Repository as an official FIS document.

Examples of materials that may exist outside the Repository include:

* project-management files;
* filing-system management files;
* temporary working notes;
* drafting material;
* conversation exports;
* experimental material not yet approved;
* and other special project-control files.

These materials are not required to follow this specification while they remain outside the Repository.

The Repository therefore defines the boundary between:

```text
Outside Repository
        ↓
Special / Working / External Project Material

Inside Repository
        ↓
Official FIS Documentation
        ↓
MUST comply with FIS-FOUND-003
```

---

## 3. File and Document

FIS distinguishes between a **file** and a **document**.

A **file** refers to the complete filesystem or repository object.

A file includes:

* its filename;
* file type;
* location;
* filesystem properties;
* and any other properties associated with the physical or digital file object.

Example:

```text
FIS-FOUND-003.md
```

A **document** refers to the content represented by that file.

The document itself is identified without its file type:

```text
FIS-FOUND-003
```

Therefore:

* filesystem references MAY use the complete filename and file type;
* Git references MAY use the complete filename and file type where appropriate;
* filing-system references MAY use the complete filename and file type;
* database or filesystem references MAY use the complete filename and file type;
* document metadata MUST use the document identifier without a file type;
* internal references to a document SHOULD use its document identifier rather than its file type.

The file type MUST NOT be included in `document_id`.

For the current FIS documentation system, official repository documents use:

```text
.md
```

as their file type.

---

## 4. Normative Language

The following terms have the following meanings throughout this specification:

| Term           | Meaning               |
| -------------- | --------------------- |
| **MUST**       | Mandatory requirement |
| **MUST NOT**   | Prohibited            |
| **SHOULD**     | Strong recommendation |
| **SHOULD NOT** | Generally avoided     |
| **MAY**        | Optional              |

Unless otherwise stated, all requirements within this document MUST be interpreted according to these definitions.

---

## 5. Documentation Philosophy

The primary purpose of documentation is to preserve knowledge.

Every official document MUST prioritize:

1. Clarity
2. Accuracy
3. Consistency
4. Maintainability
5. Traceability

Human readability MUST remain important.

Machine readability MUST NOT be achieved by introducing unnecessary complexity or redundant representations.

Documentation SHOULD preserve the meaning and intent of the information rather than merely satisfying a formatting structure.

Documentation SHOULD distinguish clearly between:

* established information;
* proposed information;
* unresolved information;
* decisions;
* observations;
* and external evidence.

---

## 6. File Format

All official Repository documentation MUST:

* use Markdown;
* use UTF-8 encoding;
* use Unix (`LF`) line endings;
* remain compatible with Visual Studio Code (VS Code);
* and use the `.md` file type.

Markdown extensions SHOULD be avoided unless officially adopted by FIS.

The `.md` file type belongs to the file.

It MUST NOT appear inside the document's `document_id`.

---

## 7. Document Structure

Every official document MUST follow this structure:

1. YAML Metadata
2. Document Title
3. Document Body
4. Changelog

The order of these primary components MUST NOT be changed.

The YAML Metadata is the single authoritative metadata layer for the document.

The Document Title identifies the document for human readers.

The Document Body contains the substantive content of the document.

The Changelog records the finalized history of the document and SHALL be placed at the end of the document.

No separate metadata copy is required outside the YAML.

Additional sections MAY be included within the Document Body where appropriate.

---

## 8. YAML Metadata

Every official document MUST include YAML front matter at the beginning of the file.

The YAML metadata MUST be the first content in the file.

The canonical YAML structure is:

```yaml
---
document_id:
title:
category:
scope:
workers:
dependency:
version:
created:
updated:
authors:
copyright:
---
```

Every official document MUST use this exact field order.

**YAML field order is absolute.**

An existing YAML field MUST NOT be moved to another position because of:

* personal formatting preference;
* document-specific convenience;
* semantic preference;
* software preference;
* or any other reason.

The same YAML field MUST have the same:

* name;
* meaning;
* position;
* and general formatting

across all official documents.

Every currently defined YAML field is mandatory.

When a field has no applicable value, the field MUST still be present and use its defined null value.

The current null value for fields without an applicable association or dependency is:

```yaml
none
```

A field MUST NOT be silently omitted merely because it has no applicable value.

---

### 8.1 Document ID

`document_id` is the canonical identifier of the document.

It MUST:

* match the document name;
* match the active filename stem;
* exclude the file type;
* remain unique within the Repository;
* remain stable across revisions;
* and never contain a version number.

Example:

```yaml
document_id: FIS-FOUND-003
```

The corresponding active file is:

```text
FIS-FOUND-003.md
```

The document name, filename stem, and `document_id` MUST always match.

The file type belongs to the file and MUST NOT be included in the document identifier.

---

### 8.2 Title

`title` identifies the human-readable title of the document.

It MAY be more descriptive than the `document_id`.

The YAML `title` MUST match the document's H1 title.

Example:

```yaml
title: Documentation Specification
```

corresponds to:

```markdown
# FIS-FOUND-003 — Documentation Specification
```

The document identifier MAY appear as part of the H1 for identification, while the YAML `title` represents the document's human-readable title.

---

### 8.3 Category

`category` identifies what kind of document the content is within FIS.

Category is a **document classification**, not a file classification.

The category describes the function or position of the document's content within FIS.

Current established categories are:

* `Foundation`
* `Definitions`
* `Templates`

Additional categories MAY be introduced as FIS develops.

A new category MUST first be formally introduced in `FIS-FOUND-003` before it is used by official Repository documents.

The category registry is therefore controlled by this specification.

Examples of future categories MAY include:

* `Reports`
* `Data`
* `Specifications`
* `Research`
* `Analysis`

These are examples only until formally established in this specification.

A category MUST NOT become an official FIS document category merely because a document uses it.

---

### 8.4 Scope

`scope` identifies the worker-access relationship of the document.

The permitted values are:

```text
general
universal
restricted
```

`general` means the document is not tied to any specific worker.

`universal` means the document applies to FIS generally according to its content and authority. It MAY additionally identify workers that are dependent upon or specifically associated with the document.

`restricted` means the document is locked to the workers identified in `workers`, unless another higher-authority FIS mechanism explicitly permits access.

Scope MUST be interpreted independently from document category and authority.

---

### 8.5 Workers

`workers` identifies the FIS workers associated with the document.

Every worker value MUST be a canonical FIS Role ID.

Example:

```yaml
workers:
  - FIS-ROLE-TRAINING
  - FIS-ROLE-SLEEP
```

A document MAY identify one worker or multiple workers.

When no worker is associated with the document:

```yaml
workers: none
```

A worker association does not by itself determine whether a document is universal or restricted.

That is determined by `scope`.

For example:

```yaml
scope: universal
workers:
  - FIS-ROLE-TRAINING
  - FIS-ROLE-SLEEP
dependency: required
```

means:

* the document remains universal;
* it is not restricted to those workers;
* and those workers are explicitly associated with or dependent upon the document.

By contrast:

```yaml
scope: restricted
workers:
  - FIS-ROLE-ANALYST
  - FIS-ROLE-BEHAVIOUR
dependency: required
```

means the document is restricted to those workers.

A restricted document MUST NOT use:

```yaml
workers: none
```

---

### 8.6 Dependency

`dependency` identifies whether the document is a dependency for the workers identified in `workers`.

The permitted values are:

```text
none
optional
required
```

`none` means the document does not constitute a required or optional worker dependency.

`optional` means the document may support, improve, or extend the operation of the associated worker or workers, but its absence does not prevent their operation.

`required` means the associated worker or workers depend upon the document for the role or operation for which the document is designated.

When:

```yaml
workers: none
```

the document MUST use:

```yaml
dependency: none
```

`dependency` does not define:

* document authority;
* document category;
* document ownership;
* document scope;
* or worker authority.

It exists only to describe the dependency relationship between the document and its associated workers.

A document may therefore be:

```yaml
scope: universal
workers: none
dependency: none
```

or:

```yaml
scope: universal
workers:
  - FIS-ROLE-TRAINING
dependency: required
```

or:

```yaml
scope: restricted
workers:
  - FIS-ROLE-ANALYST
dependency: required
```

according to the intended relationship.

---

### 8.7 Version

`version` identifies the current version of the document.

Every official Repository document has one active version.

The version MUST follow Semantic Versioning:

```text
MAJOR.MINOR.PATCH
```

The meaning of MAJOR, MINOR, and PATCH is defined in Section 21.

The active filename MUST NOT contain the version number.

The version exists inside the document metadata so that the document carries its own version identity.

---

### 8.8 Created

`created` identifies the date on which the document was first established.

The original creation date MUST remain unchanged through later revisions.

---

### 8.9 Updated

`updated` identifies the date on which the current version was finalized and locked.

It MUST be updated whenever a new version is finalized.

---

### 8.10 Authors

`authors` identifies the authors responsible for the document.

For the current FIS documentation model, the primary authors are:

```yaml
authors:
  - Siddharth Sinha
  - Aria (ChatGPT-System Architect)
```

Both authors SHOULD be listed where the document is jointly developed.

FIS does not use a separate `contributors` field in its current documentation model.

---

### 8.11 Copyright

`copyright` identifies the copyright statement applicable to the document.

---

### 8.12 Metadata Consistency

The YAML metadata is the authoritative metadata source of the document.

Equivalent metadata represented elsewhere within an official document MUST match the YAML values.

The document title MUST match `title`.

The active filename MUST match `document_id` with `.md` appended.

The active filename MUST NOT contain `version`.

If a conflict exists between YAML metadata and another representation within the document, the document is non-compliant and MUST be corrected before it is locked.

No secondary metadata representation may silently override YAML.

---

## 9. Additional YAML Metadata

Additional YAML fields MAY be required as FIS develops.

However:

> **No new YAML field becomes an official FIS metadata field merely because it appears in a document.**

When a new YAML field is required:

1. the field MUST first be introduced in `FIS-FOUND-003`;
2. its purpose and meaning MUST be defined;
3. its required or optional status MUST be established;
4. its position in the canonical YAML order MUST be established;
5. its null value, if applicable, MUST be established;
6. and existing official documents MUST subsequently be updated to comply where applicable.

This document is the authoritative registry for FIS document metadata.

Additional fields SHALL be indexed according to their defined position in the canonical YAML structure.

The introduction of a new YAML field MAY require a version change to this specification according to the significance of the change to FIS as a whole.

A new YAML field MUST NOT be introduced directly into another official document and treated as valid before being established here.

---

## 10. Worker Association and Document Scope

Official documents MAY have a relationship with one or more FIS workers.

Worker association is represented using the worker's canonical Role ID.

The Role ID is the worker marker.

Worker scope and dependency are defined exclusively through YAML metadata.

They MUST NOT be inferred from:

* filenames;
* document titles;
* changelog entries;
* descriptive rationale;
* folder names;
* or other document prose.

The canonical worker-related metadata is:

```yaml
scope:
workers:
dependency:
```

---

### 10.1 General Documents

A document with:

```yaml
scope: general
workers: none
dependency: none
```

is not tied to any specific worker.

It may be used according to:

* its content;
* its authority;
* its category;
* and applicable FIS rules.

It does not designate any worker as a dependent or restricted recipient.

This is the appropriate state when a document is neither a universal FIS document nor restricted to specific workers.

---

### 10.2 Universal Documents

A document with:

```yaml
scope: universal
```

is a universal FIS document.

A universal document applies to FIS generally according to its content and authority.

A universal document MAY also identify specific workers:

```yaml
scope: universal
workers:
  - FIS-ROLE-TRAINING
  - FIS-ROLE-SLEEP
dependency: required
```

This means:

* the document remains universal;
* it is not restricted to those workers;
* and the listed workers are explicitly associated with or dependent upon the document.

Worker association does not change the universal status of the document.

A universal document may therefore function as a system-wide law while also identifying workers for whom it is specifically relevant or required.

A universal document with no worker association MUST use:

```yaml
scope: universal
workers: none
dependency: none
```

---

### 10.3 Restricted Documents

A document with:

```yaml
scope: restricted
```

is locked to the workers identified in `workers`.

Example:

```yaml
scope: restricted
workers:
  - FIS-ROLE-ANALYST
  - FIS-ROLE-BEHAVIOUR
dependency: required
```

The document is intended only for the listed workers unless another higher-authority FIS mechanism explicitly permits access.

A restricted document MUST contain at least one worker Role ID.

A restricted document MUST NOT use:

```yaml
workers: none
```

A restricted document MUST NOT be treated as a universal FIS rule.

---

### 10.4 Multiple Worker Associations

A document MAY be associated with multiple workers.

The workers listed in `workers` MUST be identified by canonical Role ID.

A worker association does not create duplicate documents.

One document may therefore serve multiple workers while remaining a single Repository artifact.

---

### 10.5 Worker-Generated Documents

A document MAY be generated by one worker and intended for use by another worker.

The worker that creates the document and the worker or workers intended to use it are separate concepts.

The `workers` field identifies the workers to which the document is associated or restricted according to `scope`.

The generating worker does not automatically become the sole owner or intended consumer of the document.

For example:

```yaml
scope: restricted
workers:
  - FIS-ROLE-ANALYST
dependency: required
```

may represent a report generated by another worker and locked for use by the Fundamental Analyst.

A worker-generated document MAY therefore be produced by one worker while being formally restricted to another worker or group of workers.

A future metadata field MAY be introduced if FIS requires formal provenance information for generated documents.

---

## 11. Headings

Every document MUST contain exactly one H1 heading.

The H1 SHOULD be the document title and MUST correspond to the YAML `title`.

Heading hierarchy MUST follow Markdown standards.

Subsections MUST use descending heading levels.

Heading levels SHOULD NOT be skipped.

---

## 12. Paragraphs

Paragraphs SHOULD remain concise.

Each paragraph SHOULD communicate one primary idea.

Long walls of text SHOULD be avoided.

---

## 13. Lists

Bulleted lists MUST be used for unordered information.

Numbered lists MUST be used only where sequence or priority is significant.

Nested lists SHOULD be minimized.

---

## 14. Tables

Tables SHOULD be used when presenting structured comparisons.

Tables SHOULD remain simple and readable.

Complex tables SHOULD be divided into multiple smaller tables whenever practical.

---

## 15. Code Blocks

Code blocks MUST be used for:

* terminal commands;
* configuration files;
* directory structures;
* code examples;
* YAML examples;
* and other content where literal formatting is important.

Whenever possible, the appropriate language identifier SHOULD be specified.

---

## 16. Quotes

Block quotes SHOULD be reserved for:

* guiding principles;
* important definitions;
* official statements;
* and direct quotations.

Quotes SHOULD NOT replace explanatory text.

---

## 17. Naming Convention

The active filename MUST exactly match the `document_id` with the `.md` file type appended.

Example:

```text
document_id: FIS-FOUND-003
filename:    FIS-FOUND-003.md
```

The following are prohibited as active filenames:

```text
FIS-FOUND-003-v0.3.0.md
FIS-FOUND-003-0.3.0.md
FIS-FOUND-003-final.md
FIS-FOUND-003-final-v2.md
```

The document name and active filename MUST never contain a version number.

A document's version MUST exist inside its YAML metadata.

This is an unbreakable naming rule.

When a new version becomes active:

1. the current active file retains the same filename;
2. its internal `version` is updated;
3. the previous locked version is moved to the Archive;
4. the archived file MAY have its version included in its filename for historical identification;
5. the new active file is saved under the unchanged document name;
6. and the new version is committed through Git.

The active document name MUST never change because of versioning.

---

## 18. Writing Style

Documentation MUST:

* be objective;
* avoid unnecessary opinion;
* avoid conversational language;
* avoid ambiguity;
* avoid unexplained abbreviations;
* use terminology consistently;
* and distinguish established information from proposed or unresolved information.

Definitions MUST remain consistent throughout the Repository.

---

## 19. Versioning

All official documents MUST follow Semantic Versioning:

```text
MAJOR.MINOR.PATCH
```

Version changes are determined by the significance of the change to the FIS system as a whole.

Versioning is a deliberate architectural decision.

It is not an automatic measure of the number of edited lines.

### PATCH

A PATCH version is appropriate for changes that do not materially alter the document's meaning or FIS behaviour.

Examples include:

* typo corrections;
* spelling corrections;
* minor textual corrections;
* non-substantive corrections.

### MINOR

A MINOR version is appropriate for backward-compatible changes that introduce or alter a limited part of FIS documentation or system behaviour without constituting a fundamental overhaul.

Examples MAY include:

* formatting rules;
* YAML indexing changes;
* new minor metadata;
* minor state tracking;
* additional non-breaking documentation rules;
* or other limited architectural refinements.

### MAJOR

A MAJOR version is appropriate when the document undergoes a fundamental overhaul or introduces changes that materially redefine the system or the document's foundational purpose.

Examples MAY include:

* a fundamental redesign of the documentation architecture;
* a major change to the document's foundational purpose;
* or a system-wide documentation change that materially alters how FIS operates.

The exact significance of a change is determined by its effect on FIS as a whole.

---

## 20. Drafting, Locking, and Publication

FIS documentation is drafted and finalized before entering the official Repository.

The workflow is:

```text
Drafting
   ↓
Review
   ↓
Finalization
   ↓
Lock
   ↓
Save to Repository
   ↓
Git Commit
```

A document is **locked** when its current version has been finalized and approved for entry into the Repository.

A locked document is considered final for that version.

There is no partial or "half-finished" official version.

The active Repository version is therefore always a finalized version.

A document MUST NOT be edited directly after it has been locked and committed.

If a change is required after locking:

1. the required changes are developed as a new draft;
2. the new version number is determined;
3. the revised document is finalized;
4. the new version is locked;
5. the active Repository file is replaced;
6. the previous version is moved to Archive;
7. and the new version is committed through Git.

Multiple changes MAY be developed together before the new version is finalized.

The version is assigned to the complete finalized revision, not to each individual edit made during drafting.

---

## 21. Repository Rule

The FIS Repository is the canonical source of truth for all official FIS documentation.

Every official document inside the Repository MUST comply with this specification.

The Repository is the boundary of official FIS documentation.

Material that has not been formally approved and locked MUST remain outside the Repository.

Drafts, working notes, discussions, and unfinished documents MUST remain outside the Repository until formally approved and locked.

Files stored outside the Repository are not governed by this specification unless they are explicitly brought into the Repository as official FIS documents.

Project Resources MAY serve as synchronized AI-readable representations of relevant project knowledge and MUST remain consistent with the official Repository contents when they represent Repository documents.

---

## 22. Archive

The Archive is a historical storage layer outside the active FIS document environment.

Archived files are retained for historical traceability but are not part of the active document set.

Archive contents MUST NOT be treated as current FIS authority unless a human system operator explicitly retrieves and reintroduces them for review.

The active FIS filing system SHOULD NOT present Archive contents as part of the normal document or resource view.

Git provides the primary historical traceability for document evolution.

Archive filenames MAY contain version information because archived files are historical records rather than active documents.

The Archive is therefore analogous to a secured historical locker:

```text
Active Repository
      ↓
Current authoritative document

Archive
      ↓
Historical locked versions
      ↓
Not active authority
```

The Archive does not form part of the active FIS documentation environment.

---

## 23. References

External references SHOULD:

* identify the original source;
* remain verifiable;
* clearly distinguish official documentation from interpretation;
* and be cited in a manner that allows the source to be recovered.

Scientific references SHOULD identify their source whenever practical.

Internal FIS references SHOULD use the document identifier and title where useful.

File types SHOULD NOT be included when referring to the document itself.

Filesystem paths MAY include file types when the filesystem object is specifically being referenced.

Example of an internal document reference:

```text
FIS-FOUND-003 — Documentation Specification
```

Example of a filesystem reference:

```text
FIS-FOUND-003.md
```

The distinction between these forms MUST be preserved.

---

## 24. Traceability

Every important definition, rule, specification, and recommendation SHOULD be traceable to one or more of the following:

* official documentation;
* scientific evidence;
* documented observation;
* approved FIS decision;
* or another explicitly identified authoritative source.

A reference SHOULD make clear whether it identifies:

* a document;
* a file;
* an external source;
* an observation;
* or an approved decision.

Internal references SHOULD use canonical document identifiers.

Historical version tracing is primarily handled through Git and the Archive rather than through active document naming.

---

## 25. Specification Authority

This specification is the authoritative documentation standard for the FIS Repository.

Any documentation rule introduced elsewhere MUST be treated as proposed until it is incorporated into this specification.

Once a documentation rule is established here, the Repository MUST be updated so that official documents comply with it.

No other document may silently redefine the documentation system.

If another document requires a documentation behaviour that conflicts with this specification, the conflict MUST be resolved by revising the appropriate authoritative specification before the conflicting behaviour becomes a Repository-wide rule.

This document governs itself.

Therefore, revisions to `FIS-FOUND-003` MUST follow the documentation rules established here, except where the revision is explicitly establishing or correcting those rules.

---

## 26. Specification Compliance

Every official Repository document MUST comply with this specification.

Compliance includes, at minimum:

* correct YAML structure;
* exact canonical YAML field order;
* valid document ID;
* document ID matching the active filename stem;
* correct category;
* valid scope;
* valid worker associations;
* valid dependency state;
* valid versioning;
* correct authorship;
* correct title;
* exactly one H1 matching the YAML title;
* correct Markdown structure;
* valid active filename;
* no version number in the active filename;
* correct drafting and locking procedure;
* and compliance with Repository and Archive rules.

A document that fails any mandatory requirement is not compliant and MUST be corrected before being locked into the Repository.

---

## Changelog

### v0.3.0

* Reworked the document metadata architecture.
* Removed `repository_version`.
* Removed `contributors` and established shared `authors`.
* Established the canonical YAML field order.
* Established `document_id` as the document name without a file type.
* Established the active filename as `document_id.md`.
* Established that active filenames MUST never contain version numbers.
* Established `category` as a classification of document content within FIS.
* Established `scope`, `workers`, and `dependency` as canonical YAML metadata.
* Established `general`, `universal`, and `restricted` document scope.
* Established canonical worker association through FIS Role IDs.
* Established universal documents that may identify dependent workers.
* Established worker-restricted documents.
* Established worker-generated documents intended for other workers.
* Established a single YAML metadata source of truth.
* Removed redundant secondary metadata representations.
* Established the Document Title immediately after YAML metadata.
* Moved the Changelog to the end of the document.
* Established the Repository as the complete scope of official FIS documentation.
* Established the locked-version workflow for Repository documents.
* Established that active filenames remain stable across revisions.
* Established that archived versions MAY carry version information for historical tracing.
* Clarified Semantic Versioning as a deliberate system-impact decision.
* Clarified the distinction between drafting, locking, Repository storage, Git commit, and Archive.
* Established that Archive contents are outside active FIS visibility and are not current authority.
* Established that every new documentation rule and YAML field MUST first be defined in this specification.

### v0.2.2

* Worker Marker Rule added.
* YAML format fixes.
* Localization bug fixes.

### v0.2.1

* Comment block moved.

### v0.2.0

* Purpose updated.
* YAML rules updated.
* Changelog rule added.
