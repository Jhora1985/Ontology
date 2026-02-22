# Issue #1: Core capability inference

## Intent
Formalize a capability inference pattern that ensures Agent capability assertions remain consistent with Task requirements.

## Core Structure vs Inference

- Core ontological structure: **Agent → Capability → Task**
- Inference / validation pattern: if an Agent is modeled as supporting a Task, and that Task requires a Capability, then the Agent can be inferred or validated to have that Capability.

The fundamental structure flows from Agent to Capability to Task.  
The Task-based reasoning path is a validation/inference mechanism, not the primary ontological chain.

## Context
As the Beast Mode ontology evolved, we formalized:

- Capability assets
- Agent–Capability–Task relationships
- Constraints ensuring consistency between declared Task support and Capability assertions

This prevents semantic drift between Task modeling and Agent capability claims.

## What Changed (Implementation Summary)
- Core ontology updated to formalize:
  - Capability asset modeling
  - Agent–Capability–Task structural relationships
  - Validation/inference alignment
- SHACL constraints aligned to support consistent capability attribution
- Example usage added where applicable

## Primary Review Cues (Fast Skim)

Please review:

- Core ontology definitions governing Agent–Capability–Task relationships
- SHACL shapes validating structural consistency
- Example TTL demonstrating capability alignment

## Implementation Anchor

Primary commit implementing this work:

- ceebfa4  
  "Core ontology: formalize capability assets, inference chain, and discovery constraints"

## Traceability Map

Issue → Concept → Commit → Files

This document exists to provide clear linkage between the conceptual issue and its concrete implementation anchor for rapid review.