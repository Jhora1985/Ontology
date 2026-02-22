# Issue #7: SHACL rule construct fix + dcterms:created datatype alignment

## Intent
Correct a SHACL rule construct and align the datatype of `dcterms:created` to ensure consistent validation behavior and semantic correctness across the ontology.

## Context
During ontology refinement, we identified:

- A SHACL rule construct that did not align with intended validation behavior.
- A datatype mismatch or inconsistency for `dcterms:created`.

These issues could cause validation ambiguity or unintended SHACL behavior.

## What Changed (Implementation Summary)
- Corrected SHACL rule construct logic to reflect intended constraint behavior.
- Aligned `dcterms:created` usage to the expected datatype.
- Ensured consistency across ontology and SHACL shapes.

## Primary Review Cues (Fast Skim)
Please focus on:

- SHACL rule definitions affected by this change
- Any constructs using `sh:rule` or related validation logic
- All occurrences of `dcterms:created` and its datatype declaration

## Implementation Anchor
Primary commit implementing this work:

- c79cec4  
  "Fix SHACL rule construct and align dcterms:created datatype"

## Traceability Map
Issue → Concept → Commit → Files

This document exists to provide a clear linkage between Issue #7 and its implementation anchor for rapid review.