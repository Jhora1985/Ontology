# Issue #7: SHACL rule fix + dcterms alignment

## Intent

Correct a SHACL rule construct issue and align `dcterms:created` datatype usage to ensure validation behavior and metadata semantics remain consistent across the ontology.

## Context

As SHACL constraints and metadata fields matured, a mismatch in rule construction and/or datatype expectations created validation friction and inconsistent interpretation of `dcterms:created`. This change fixes the SHACL construct and standardizes datatype alignment.

## What Changed (Implementation Summary)

Implemented in commit:

`c79cec4f7fb38829660570e8bf1b624aabcd15bf`

This commit introduces:

- Correction to the affected SHACL rule construct
- Alignment of `dcterms:created` datatype usage for consistency

## Primary Review Cues (Fast Skim)

Please review commit:

`c79cec4f7fb38829660570e8bf1b624aabcd15bf`

Focus areas:

- The corrected SHACL rule logic and expected validation behavior
- Any updates related to `dcterms:created` typing and downstream consistency

## Implementation Anchor

Primary commit implementing this work:

- c79cec4f7fb38829660570e8bf1b624aabcd15bf  
  "Fix SHACL rule construct and align dcterms:created datatype"

## Traceability Map

| Concept                           | Commit                                      |
|-----------------------------------|---------------------------------------------|
| SHACL rule construct correction   | c79cec4f7fb38829660570e8bf1b624aabcd15bf    |
| `dcterms:created` datatype align. | c79cec4f7fb38829660570e8bf1b624aabcd15bf    |

This document links the conceptual Issue directly to its immutable implementation commit.