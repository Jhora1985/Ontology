# Issue #11: Specialty + Disagreement ontology extensions

## Intent
Introduce structured ontology support for specialty agents and explicit modeling of disagreement between specialty outputs.

## Context
As the ecosystem expanded to include specialty beasts (agents with domain-specific strengths), we needed a way to represent:

- specialty roles and domain focus
- conflicting outputs between specialty agents
- structured disagreement states tied to the same subject/claim
- signals such as trust, confidence, and supporting evidence

This work formalizes disagreement as a first-class modeling construct.

## What Changed (Implementation Summary)
- Added specialty ontology extensions
- Introduced disagreement modeling constructs
- Linked disagreement instances to:
  - participating specialty agents
  - conflicting assertions/recommendations
  - subject/claim under evaluation
- Provided example TTL demonstrating specialty + disagreement scenarios

## Primary Review Cues (Fast Skim)
Please focus on:
- Ontology extension module(s) defining specialty constructs
- Disagreement modeling class(es) and relationships
- How conflicting assertions are represented
- Example TTL demonstrating disagreement scenarios
- Any SHACL shapes enforcing minimum structure (if present)

## Implementation Anchor
Primary commit implementing this work:

- 7b8d6d7  
  "Add specialty and disagreement ontology extensions with examples"

## Traceability Map
Issue → Concept → Commit → Files

This document exists to make review fast and to map Issue #11 to its implementation anchor.