**Filename**: `TEST_CASE_DESIGN_SOP.md`
**Version**: `1.5.0`
**Objective**: To provide the AI Agent with **core strategies, design principles, and content standards** for authoring high-quality test cases.
**Core Directive**: Use this as the core guide for designing and authoring test case content.

---

## 1. Core Test Design Strategy

### Rule: Comprehensive Test Type Coverage
- **CONTEXT**: Test case set planning for a feature/function.
- **REQUIRED_TEST_TYPES_TO_CONSIDER**:
  - `Positive`, `Negative`, `Boundary`, `Error Handling`, `Security/Permission`
  - `Performance` (including `Stress` and `Concurrency` where applicable)

## 2. General Design Principles

### Principle: A.T.O.M.
- **RULE_NAME**: `Atomic_Thorough_Organized_Maintainable`
### Principle: Clarity Over Brevity
- **RULE_NAME**: `Clarity_Over_Brevity`

## 3. Content Implementation Guidelines

### Guideline: Arrange-Act-Assert (AAA) Pattern
- **MAPPING**: `Precondition` -> Arrange, `Steps` -> Act, `ExpectedResult` -> Assert.
### Guideline: Effective Tagging
- **REQUIREMENT**: `Tags` field must accurately reflect the test's intent, using values from `[TESTING_SOP: ENUMS]`. For a concurrency test, the tag **must** include `concurrency`.

## 4. Advanced Design & Refactoring

### Guideline: D.R.Y. via Helpers and Factories
- **ACTION**: Repetitive Logic -> `tests/helpers/`. Repetitive Data -> `tests/factories/`.

## 5. Special Scenarios

### Guideline: Handling Skipped Tests
- **REQUIREMENT**: If `Status` is `Skipped`, the `SkipReason` field is mandatory.