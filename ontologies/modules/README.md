# Beast Mode Capabilities Module

This module defines how capabilities are modeled in Beast Mode as explicit, reusable declarations of what an agent can do.

## Overview

In Beast Mode, a capability represents a bounded skill or competence that an agent may possess.

Capabilities are not executions, functions, or workflows.  
They are declarations of potential.

This module exists to clearly separate:
- what an agent is capable of
- from when or how that capability is exercised

## Design Intent

Capabilities serve as the connective tissue between agents and tasks.

An agent declares capabilities.  
A capability enables tasks.  
A task represents a unit of work.

This separation allows systems to reason about suitability, alignment, and responsibility without invoking execution.

## What Capabilities Are and Are Not

Capabilities are:
- declarative descriptions of competence
- reusable across agents
- independent of execution timing

Capabilities are not:
- functions
- scripts
- workflows
- guarantees of execution

## Relationship to Tasks

Tasks define work with inputs and outputs.  
Capabilities define whether an agent is able to perform that work.

A task requires exactly one capability.  
A capability may enable multiple tasks.

## Extending the Module

To extend this module:
- define new capability types declaratively
- avoid embedding logic or execution semantics
- keep capability definitions reusable and bounded

## Status

This module is under active development and may evolve as additional capability patterns emerge.
