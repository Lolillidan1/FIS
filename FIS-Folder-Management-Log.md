# FIS Folder Management Log

## Document Description

The **FIS Folder Management Log** is the structural linker for the Fitness Intelligence System repository.

It defines the current folder hierarchy and identifies the files contained within each folder.

Its purpose is to provide a single, human-readable map connecting the FIS filing system with the actual repository structure and, where applicable, the corresponding Project Resources.

This document SHALL describe the **filing structure only**.

It SHALL NOT duplicate the contents, definitions, rules, or detailed descriptions of individual files.

The filename recorded here SHALL be the exact filename used in the repository.

For active files, the filename SHALL correspond to the file identifier and naming convention defined within the file itself, or to the file title where no separate identifier is used.

Files located within `Archives` represent historical repository states and SHALL NOT be treated as active resources.

---

## Current Record

**Git Commit:** "Folder Management Update"

**Updated:** 10 Aug 2026

---

# Repository Structure

Fitness Intelligence System/
│
├── README.md
├── FIS Vision.md
├── FIS-Folder-Management-Log.md                     [This File]
├── .gitignore
│
├── Repository/                                      [Primary FIS documentation repository]
│   │
│   ├── 00_Foundations/                              [Foundational documents defining FIS principles, identity, and fundamental rules]
│   │   ├── FIS-FOUND-001.md  
│   │   ├── FIS_FOUND-002.md    
│   │   ├── FIS_FOUND-003.md      
│   │   ├── FIS_FOUND-004.md              
│   │   └── FIS-FOUND-005.md
│   │
│   ├── 01_Definitions/                              [Definitions and controlled terminology used throughout FIS]
│   │
│   ├── 02_Specifications/                           [Formal specifications defining FIS systems, components, processes, or behaviours]
│   │
│   ├── 03_Templates/                                [Reusable templates for creating standardized FIS documents and records]
│   │   └── FIS-TPL-ROLE-INIT
│   │   
│   ├── 04_Data-Library/                             [Structured datasets and reference libraries providing reusable information for FIS analysis, interpretation, and planning]
│   │
│   ├── 05_Analysis/                                 [Analytical work, analytical outputs, and derived interpretations]
│   │
│   ├── 06_Research/                                 [Research material, findings, and research-derived documentation]
│   │   └── Fitness Intelligence System Standards.md
│   │
│   ├── 07_Experiments/                              [Controlled experiments, trials, and experimental system work]
│   │
│   ├── 08_Resources/                                [Supporting resources used by FIS that do not belong to another defined repository category]
│   │
│   ├── 09_Archives/                                 [Historical files retained for traceability but no longer considered active][This section will not be updated for tracking]
│   │
│   └── 10_Validation/                               [Validation protocols and validation-related material]
│       └── AI-Resource-Validation-Protocol.md
│
└── Assets/                                          [Supporting project assets outside the primary documentation repository]

Archived files are retained for historical and Git-traceability purposes and SHALL NOT be treated as current FIS resources.

---

# Structural Update

The current record corresponds to the Git commit identified above.

When the repository structure changes, this document SHALL be updated to represent the new structure.

The previous version SHALL be moved to the designated `Archives` location before the updated version becomes the active Folder Management Log.

---

# End of Folder Management Log