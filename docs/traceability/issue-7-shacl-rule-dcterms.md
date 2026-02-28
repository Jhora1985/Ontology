# Issue #7: SHACL rule fix + dcterms alignment

## Intent

Document the SHACL rule correction and `dcterms:created` datatype alignment previously implemented in the referenced commit, ensuring clear traceability between the conceptual issue and its concrete implementation.

## Context

As SHACL constraints and metadata fields matured, a mismatch in rule construction and datatype expectations created validation friction and inconsistent interpretation of `dcterms:created`. The referenced implementation commit resolves these issues.

## What Changed (Implementation Summary)

The referenced implementation commit:

`c79cec4f7fb38829660570e8bf1b624aabcd15bf`

Introduces:

- Correction to the affected SHACL rule construct
- Alignment of `dcterms:created` datatype usage for consistency

This PR adds traceability documentation only and does not modify ontology logic.

## Primary Review Cues (Fast Skim)

Please review implementation commit:

`c79cec4f7fb38829660570e8bf1b624aabcd15bf`

Focus areas:

- The corrected SHACL rule logic and resulting validation behavior
- Updates related to `dcterms:created` typing and downstream consistency

## Implementation Anchor

Primary commit implementing this work:

- c79cec4f7fb38829660570e8bf1b624aabcd15bf  
  "Fix SHACL rule construct and align dcterms:created datatype"

## Traceability Map

| Concept                             | Commit                                       |
|-------------------------------------|----------------------------------------------|
| SHACL rule construct correction     | c79cec4f7fb38829660570e8bf1b624aabcd15bf     |
| `dcterms:created` datatype alignment| c79cec4f7fb38829660570e8bf1b624aabcd15bf     |

This document links the conceptual Issue directly to its specific implementation commit reference.