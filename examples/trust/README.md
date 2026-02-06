# Trust Example

This example demonstrates the **Trust extension** for Beast Mode.

## What it shows
- A fully core-valid Agent, Capability, and Task
- A TrustAssertion scoped to a specific task
- Separation of **capability** ("can do") from **trust** ("allowed to do")

## Ontologies involved
To validate or reason over this example, load:
- beast_mode_ontology.ttl (core)
- ontologies/extensions/beast_trust_ext.ttl
- examples/trust/trust_example.ttl

## Notes
Trust is modeled as an extension, not core, so that organizations can define their own trust policies without changing the base ontology.