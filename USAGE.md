# Beast Mode Ontology - Usage Guide

Quick reference guide for using the Beast Mode Core Ontology.

## Quick Start

### 1. Basic Agent Definition

```turtle
@prefix : <http://example.org/beast-mode#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

:my-agent a :Agent ;
  :name "My Agent" ;
  :description "Description of what this agent does" ;
  :status "active" ;
  :hasCapability :my-capability .
```

### 2. Basic Capability Definition

```turtle
:my-capability a :Capability ;
  :name "My Capability" ;
  :description "What this capability enables" ;
  :status "active" ;
  :enablesTask :my-task .
```

### 3. Basic Task Definition

```turtle
:my-task a :Task ;
  :name "My Task" ;
  :description "What this task does" ;
  :hasInput "Description of required input" ;
  :hasOutput "Description of produced output" ;
  :status "active" ;
  :requiresCapability :my-capability .
```

## Complete Example

```turtle
@prefix : <http://example.org/beast-mode#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

# Define Agent
:agent-001 a :Agent ;
  :id "agent-001" ;
  :name "Example Agent" ;
  :description "An example agent for demonstration" ;
  :status "active" ;
  :version "1.0.0" ;
  :createdAt "2024-01-01T00:00:00Z"^^xsd:dateTime ;
  :hasCapability :cap-001 .

# Define Capability
:cap-001 a :Capability ;
  :id "cap-001" ;
  :name "Example Capability" ;
  :description "An example capability" ;
  :status "active" ;
  :version "1.0.0" ;
  :createdAt "2024-01-01T00:00:00Z"^^xsd:dateTime ;
  :enablesTask :task-001 .

# Define Task
:task-001 a :Task ;
  :id "task-001" ;
  :name "Example Task" ;
  :description "An example task" ;
  :hasInput "Input description" ;
  :hasOutput "Output description" ;
  :status "active" ;
  :version "1.0.0" ;
  :createdAt "2024-01-01T00:00:00Z"^^xsd:dateTime ;
  :requiresCapability :cap-001 .
```

## Required vs Optional Properties

### Agent - Required
- `:name` (exactly 1)
- `:hasCapability` (at least 1)

### Agent - Optional
- `:description` (0 or 1)
- `:id` (0 or 1)
- `:version` (0 or 1)
- `:status` (0 or 1, must be: "active", "deprecated", "draft", or "archived")
- `:tags` (0 or 1)
- `:createdAt` (0 or 1)
- `:updatedAt` (0 or 1)

### Capability - Required
- `:name` (exactly 1)
- `:enablesTask` (at least 1)

### Capability - Optional
- Same as Agent optional properties

### Task - Required
- `:name` (exactly 1)
- `:hasInput` (exactly 1)
- `:hasOutput` (exactly 1)
- `:requiresCapability` (exactly 1)

### Task - Optional
- Same as Agent optional properties

## Status Values

The `:status` property accepts one of these values:
- `"active"` - Currently active and available
- `"deprecated"` - Still functional but being phased out
- `"draft"` - Work in progress, not yet ready
- `"archived"` - No longer in use but preserved

## Validation

The ontology includes SHACL constraints that will validate:
- Required properties are present
- Property cardinalities are respected
- Data types are correct
- Status values are from allowed enumeration

## Common Patterns

### Agent with Multiple Capabilities

```turtle
:agent a :Agent ;
  :name "Multi-Capability Agent" ;
  :hasCapability :cap1 , :cap2 , :cap3 .
```

### Capability Enabling Multiple Tasks

```turtle
:capability a :Capability ;
  :name "Multi-Task Capability" ;
  :enablesTask :task1 , :task2 , :task3 .
```

### Linking Agent to Tasks (Derived)

```turtle
# Agent can perform tasks through capabilities
:agent :performsTask :task1 , :task2 .
```

## Integration Tips

1. **Customize Namespace**: Update `@prefix :` to your domain
2. **Add Subclasses**: Extend with domain-specific subclasses
3. **Add Properties**: Include domain-specific properties as needed
4. **Update SHACL**: Add validation for new properties
5. **Version Control**: Use `:version` property to track ontology versions

## Tools

- **Apache Jena**: RDF processing and validation
- **pyshacl**: Python SHACL validation
- **Protégé**: Visual ontology editor
- **rdflib**: Python RDF library
- **TopBraid**: Commercial SHACL tools

## Questions?

See the main README.md for more details or check the example file `beast_mode_examples.ttl` for complete working examples.
