**Filename**: `TESTING_SOP.md`
**Version**: `2.2.0`
**Objective**: To provide the AI Agent with mandatory rules for **physical structure, file formats, ID specifications, and metadata** for all testing activities.
**Core Directive**: When executing any testing-related task, you must parse and strictly adhere to all rules in this file.

---

## 1. Directory Structure Rules

### Rule: `tests` Directory Structure
- **CONTEXT**: Managing all test-related files.
- **STRUCTURE & DESCRIPTION**:
  - `cases/`: Contains all `.yaml` test case definitions.
    - `unit/`, `integration/`, `e2e/`, `performance/`
  - `factories/`: Contains test data generator code.
  - `fixtures/`: Contains static test data.
  - `helpers/`: Contains reusable test helper functions.
  - `config/`: Contains test-specific configuration files.
  - `docs/`: Contains high-level test strategy documents.
  - `reports/`: Contains test execution reports and logs.
  - `temp/`: Contains temporary files generated during tests (must be in `.gitignore`).
  - `README.md`: Explains how to run tests and the directory structure.

## 2. Test Case File Mapping Rules

### Rule: Unit Test File Mapping
- **ACTION**: Mirror the source file path.
- **EXAMPLE**: `src/services/auth.js` -> `tests/cases/unit/services/auth.yaml`

## 3. ID Generation Rules

### Rule: CaseID Format
- **TEMPLATE**: `{type}-{module}-{group_id}{sequence_id}`
- **COMPONENTS**:
  - `type`: `U` (Unit), `I` (Integration), `E` (E2E), `P` (Performance)
  - `module`: Uppercase abbreviation from `[DEV_DOC_SOP: ENUMS: Module Abbreviations]`
  - `group_id`: (String) `REGEX: ^[0-9A-Z]$`
  - `sequence_id`: (String) `REGEX: ^[0-9]{2}$`, `RANGE: 01-99`

## 4. Document Structure Rules

### Rule: YAML Document Structure
- **TARGET_FILE**: `*.yaml` in `tests/cases/`
- **DESCRIPTION**: This is the mandatory, multi-document structure for a test case file.
- **STRUCTURE**:
  - **File Header (Required, once at the top of the file, structure varies by type)**:
    - **IF in `unit/`**:
      - `TestFile`: (String) Relative path to the source file being tested.
    - **IF in `integration/`**:
      - `Feature`: (String) Name of the integrated feature or flow (e.g., "Authentication Flow").
    - **IF in `e2e/`**:
      - `Scenario`: (String) Name of the end-to-end user scenario (e.g., "New User Registration and First Purchase").
    - **IF in `performance/`**:
      - `Target`: (String) The specific endpoint or operation being tested (e.g., "API: POST /orders").
  - **Test Group (Required, one or more per file, each section separated by `---`)**:
    - `TestFunction`: (String) Name of the function/feature being tested.
    - `Cases`: (Array) A list of test case objects.
      - **Case Item (object within the `Cases` array)**:
        - **Required Fields**: `CaseID`, `Module`, `Description`, `Importance`, `Status`, `Precondition`, `Steps`, `ExpectedResult`.
        - **Optional Fields**: `Tags`, `SkipReason`.
- **DESIGN_GUIDE**: For the quality and design of the content within these fields, you must strictly follow **`[TEST_CASE_DESIGN_SOP.md]`**.

## 5. ENUMS (Enumerated Values)

### ENUMS: Importance Levels
- **VALUES**: `High`, `Medium`, `Low`
### ENUMS: Status Values
- **VALUES**: `Planned`, `InProgress`, `Implemented`, `Failed`, `Deprecated`, `Skipped`
### ENUMS: Functional & Type Tags
- **VALUES**:
  - `smoke`, `regression`, `security`
  - `positive`, `negative`, `boundary`, `error-handling`
  - **`performance`**: General performance measurement.
  - **`stress`**: Testing system limits and breaking points.
  - **`concurrency`**: Testing simultaneous access to shared resources.