# Issue #1: Core capability inference

## Intent
Formalize the core ontology pattern that allows an Agent’s effective capabilities to be derived from the tasks it supports (capability inference chain), reducing duplicated assertions and preventing drift between Task requirements and Agent capabilities.

## Context
During early development of the Beast Mode core ontology, we introduced a structured pattern to formalize:

- Capability assets
- The Agent → Task → Capability inference chain
- Discovery constraints associated with capability reasoning

This issue provides traceability between the conceptual discussion and the concrete implementation.

## What Changed (Implementation Summary)
- Core ontology updated to formalize:
  - Capability asset modeling
  - Inference chain semantics
  - Discovery-related constraints
- SHACL constraints aligned to support validation of the inference pattern
- Example usage added where applicable

## Primary Review Cues (Fast Skim)
For implementation details, please review:

- Core ontology definitions governing Agent–Task–Capability relationships
- SHACL shapes that validate the inference chain and required properties
- Any example TTL demonstrating the inference behavior

## Implementation Anchor
Primary commit implementing this work:

- ceebfa4  
  "Core ontology: formalize capability assets, inference chain, and discovery constraints"

## Traceability Map
Issue → Concept → Commit → Files

This document exists solely to make review faster and to clearly map Issue #1 to its implementation anchor.