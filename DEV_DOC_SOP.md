### File 1 (v2.2.1): Development Documentation SOP (Compacted)
**Filename**: `DEV_DOC_SOP.md`
**Version**: `2.2.1`
**Objective**: To provide the AI Agent with mandatory rules for creating and maintaining all **development-related documentation**.
**Core Directive**: When executing tasks related to project design, requirements, APIs, or source code documentation, you must parse and strictly adhere to all rules in this file.

---

## 1. Directory Structure Rules

### Rule: `docs` Directory Structure
- **CONTEXT**: Managing all design, requirements, and API related documents.
- **STRUCTURE & DESCRIPTION**:
  - `docs/`: Root for all documentation.
  - `requirements/`: Contains product/technical requirements, use cases, and the project glossary.
    - `use-cases/`: Contains detailed Use Case documents (`.md`).
    - `glossary.md`: Defines key business and technical terms.
  - `api/`: Contains the API contract (`openapi.yaml`).
  - `third-party/`: Contains docs for external dependencies.
  - `adr/`: Contains Architecture Decision Records.

## 2. Document Content & Structure Rules

### Rule: `product-requirements.md` Required Sections
- **REQUIRED_SECTIONS**: `Project Background`, `User Stories`, `Functional Requirements`, `Business Rules`, `User Experience`

### Rule: `technical-specifications.md` Required Sections
- **REQUIRED_SECTIONS**: `System Architecture`, `Data Design`, `API Design`, `Non-Functional Requirements`, `Deployment Plan`

### Rule: Use Case Document (`use-cases/*.md`)
- **CONTEXT**: Describing a user-system interaction.
- **REQUIRED_SECTIONS**: `Use Case Name & ID`, `Actors`, `Preconditions`, `Main Success Scenario`, `Extensions`

### Rule: Architecture Decision Record (`adr/*.md`)
- **CONTEXT**: Documenting a significant architectural decision.
- **FILENAME_FORMAT**: `NNN-short-description.md`
- **REQUIRED_SECTIONS**: `Title`, `Status`, `Context`, `Decision`, `Consequences`

### Rule: `openapi.yaml` Requirements
- **REQUIREMENTS**: OpenAPI 3.0, Complete definitions, Examples, Error codes

### Rule: Code Comment (JSDoc) Format
- **FORMAT**: `/** ... */`

## 3. ENUMS (Enumerated Values)

### ENUMS: Module Abbreviations
- **DESCRIPTION**: For use in logs, internal docs, and test case IDs.
- **VALUES**: `AUTH`, `USER`, `PAY`, `ORDER`, `ADMIN`, `API`, `DB`, `CACHE`, `EMAIL`, `FILE`, `LOG`, `CONFIG`

### ENUMS: Priority Levels
- **CONTEXT**: For User Stories / Functional Requirements.
- **VALUES**: `Critical`, `High`, `Medium`, `Low`