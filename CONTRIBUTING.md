# AI Agent Contribution & Development Guide
**Core_Directive**: Act as an expert software engineer. Your mandatory workflow is to **Decompose, then Execute** for every task.

## Mandatory Workflow

### Step 1: Decompose Task
- **PROCESS**: Your first action is to break down the high-level task into a sequential checklist of engineering actions.
- **EXAMPLE_TASK**: "Add a new `discountCode` field to the order creation API and ensure it's fully tested."
- **EXAMPLE_DECOMPOSITION**:
  1.  Update API documentation (`openapi.yaml`).
  2.  Implement business logic in application code.
  3.  Create test file structure and naming.
  4.  Design test cases (positive, negative, boundary).
  5.  Write test cases into `.yaml` format.

### Step 2: Execute Checklist using SOPs
- **PROCESS**: As you complete each item in your decomposed checklist, consult the following reference to load the correct SOP file from the `_guidelines/` directory.

## SOP Mapping Reference

- **IF_ACTION_INVOLVES**: "Designing project-level documents (requirements, APIs, etc.)"
  - **THEN_CONSULT_SOP**: `_guidelines/DEV_DOC_SOP.md`
  - **EXAMPLE**: For Checklist item #1

- **IF_ACTION_INVOLVES**: "Creating test file structure, naming, or IDs"
  - **THEN_CONSULT_SOP**: `_guidelines/TESTING_SOP.md`
  - **EXAMPLE**: For Checklist item #3

- **IF_ACTION_INVOLVES**: "Designing WHAT to test (the test strategy: positive, negative, boundary)"
  - **THEN_CONSULT_SOP**: `_guidelines/TEST_CASE_DESIGN_SOP.md`
  - **EXAMPLE**: For Checklist item #4

- **IF_ACTION_INVOLVES**: "Writing test case content into the final `.yaml` format"
  - **THEN_CONSULT_SOP**: `_guidelines/TESTING_SOP.md` (for field structure)
  - **EXAMPLE**: For Checklist item #5

- **IF_ACTION_INVOLVES**: "Modifying the test runner or execution framework itself"
  - **THEN_CONSULT_SOP**: `_guidelines/TEST_CODE_IMPLEMENTATION_SOP.md`
  - **EXAMPLE**: For advanced tasks only.