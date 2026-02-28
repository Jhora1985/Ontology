# Issue #5: A2A edge transport + AgentCard projection

## Intent
Introduce an A2A (agent-to-agent) edge transport channel and AgentCard projection model to support interoperability and semantic discovery, with SHACL validation for “A2A readiness”.

## Context
The ecosystem needed a way to represent agents that can be discovered and interacted with externally (beyond internal messaging such as Redis Streams). This work adds an interoperability transport abstraction and a semantic “AgentCard” style projection for discovery/matching.

## What Changed (Implementation Summary)
- Added A2A interoperability transport modeling:
  - beast:A2AChannel
- Added discovery/matching modeling constructs:
  - beast:AgentCardProjection
  - beast:A2ASkill
- Added SHACL shapes to validate A2A readiness (e.g., endpointUrl / agentCardUrl / identity fields as applicable)
- Added an example agent exposed via A2A

## Primary Review Cues (Fast Skim)
Please focus on:
- Ontology module(s) defining:
  - A2A transport channel (beast:A2AChannel)
  - AgentCard projection and skills (beast:AgentCardProjection, beast:A2ASkill)
- SHACL shapes validating required A2A fields
- Example TTL demonstrating an A2A-exposed agent

## Implementation Anchor
Primary commit implementing this work:

- fb7717d  
  "Add A2A edge transport channel + AgentCard projection + SHACL"

## Traceability Map
Issue → Concept → Commit → Files

This document exists to make review fast and to map Issue #5 to its implementation anchor.