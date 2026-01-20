# Beast Mode Core Ontology

A core ontology defining the fundamental entities and relationships in the Beast Mode system, with comprehensive SHACL constraints for data validation.

## Overview

Beast Mode is a system for modeling autonomous agents, their capabilities, and the tasks they can perform. This ontology provides the foundational structure for understanding how agents operate within the Beast Mode framework.

The ontology is implemented in **Turtle (TTL)** format with **SHACL (Shapes Constraint Language)** validation constraints, making it suitable for use in semantic web applications, knowledge graphs, and RDF-based systems.

## Core Entities

### Agent
An autonomous or semi-autonomous actor in Beast Mode. Agents possess capabilities that enable them to perform various tasks.

**Required Properties:**
- `name` (string): Human-readable name
- `hasCapability` (Capability): At least one capability (one-to-many)

**Optional Properties:**
- `description` (string): Detailed description
- `id` (string): Unique identifier
- `version` (string): Version identifier
- `status` (string): Status (active, deprecated, draft, archived)
- `tags` (string): Tags or keywords
- `createdAt` (dateTime): Creation timestamp
- `updatedAt` (dateTime): Last update timestamp

### Capability
A bounded skill that an agent can perform. Capabilities serve as the bridge between agents and the tasks they can execute.

**Required Properties:**
- `name` (string): Human-readable name
- `enablesTask` (Task): At least one enabled task (one-to-many)

**Optional Properties:**
- `description` (string): Detailed description
- `id` (string): Unique identifier
- `version` (string): Version identifier
- `status` (string): Status (active, deprecated, draft, archived)
- `tags` (string): Tags or keywords
- `createdAt` (dateTime): Creation timestamp
- `updatedAt` (dateTime): Last update timestamp

### Task
A unit of work with a clear input and output. Tasks represent the atomic operations that agents can perform through their capabilities.

**Required Properties:**
- `name` (string): Human-readable name
- `hasInput` (string): Description of required input
- `hasOutput` (string): Description of produced output
- `requiresCapability` (Capability): Exactly one required capability

**Optional Properties:**
- `description` (string): Detailed description
- `id` (string): Unique identifier
- `version` (string): Version identifier
- `status` (string): Status (active, deprecated, draft, archived)
- `tags` (string): Tags or keywords
- `createdAt` (dateTime): Creation timestamp
- `updatedAt` (dateTime): Last update timestamp

## Relationships

- **Agent → Capability** (`hasCapability`): One-to-many relationship
- **Capability → Task** (`enablesTask`): One-to-many relationship
- **Task → Capability** (`requiresCapability`): Many-to-one relationship (inverse of enablesTask)
- **Agent → Task** (`performsTask`): Derived relationship through capabilities

## Structure

```
Agent
  └── hasCapability → Capability
        └── enablesTask → Task
              └── requiresCapability → Capability (inverse)
```

## Files

- `beast_mode_ontology.ttl` - Core ontology with SHACL constraints (main file)
- `beast_mode_examples.ttl` - Example instances demonstrating usage
- `beast_mode_core.md` - Original markdown definitions (legacy)
- `README.md` - This file

## Usage

### Loading the Ontology

The ontology can be loaded into any RDF-compatible system:

```bash
# Using Apache Jena
riot --validate beast_mode_ontology.ttl

# Using rdflib (Python)
from rdflib import Graph
g = Graph()
g.parse("beast_mode_ontology.ttl", format="turtle")
```

### Validating Data with SHACL

The ontology includes SHACL shapes for data validation:

```python
# Example using pyshacl
import pyshacl
shapes_graph = Graph().parse("beast_mode_ontology.ttl", format="turtle")
data_graph = Graph().parse("beast_mode_examples.ttl", format="turtle")
results = pyshacl.validate(data_graph, shacl_graph=shapes_graph)
```

### Namespace

The ontology uses the namespace: `http://example.org/beast-mode#`

You can customize this by updating the `@prefix :` declaration in the TTL file.

## SHACL Constraints

The ontology includes comprehensive SHACL validation constraints:

1. **Node Shapes**: Validation rules for each class (Agent, Capability, Task)
2. **Property Shapes**: Constraints on relationships and datatype properties
3. **Cardinality Constraints**: Minimum/maximum counts for properties
4. **Data Type Validation**: Ensures correct data types (string, dateTime)
5. **Value Constraints**: Status values must be from allowed enumeration

## Example Instances

See `beast_mode_examples.ttl` for complete examples including:
- Code Review Agent with multiple capabilities
- Data Processing Agent
- Various tasks demonstrating the Agent → Capability → Task pattern

## Extending the Ontology

To extend this ontology for your specific use case:

1. **Add new classes**: Define subclasses or new classes as needed
2. **Add properties**: Extend with domain-specific properties
3. **Update SHACL shapes**: Add validation constraints for new properties
4. **Customize namespace**: Update the namespace URI to your domain

## Contributing

Contributions are welcome! Please feel free to submit issues or pull requests.

## License

[Add your license here]
