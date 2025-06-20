**Filename**: `TEST_CODE_IMPLEMENTATION_SOP.md`
**Version**: `1.2.0`
**Objective**: This SOP defines the mandatory rules for **test execution output, exception handling, and logging** that the automated testing framework's code implementation must follow when executing `.yaml` test cases.

**Core Directive**: The automation script or framework responsible for test execution must strictly conform its behavior and output to this SOP.

---

## 1. Test Execution & Output Rules

### Rule: Test Case Result Visibility
- **CONTEXT**: Console output reporting.
- **REQUIREMENTS**:
  - **Unified Format**: Output must follow a consistent format.
  - **Explicit Status**: Status must be explicitly marked using `[PASS]`, `[FAIL]`, `[ERROR]`, `[SKIP]`.
  - **Structured Output**: Output must be structured to present information clearly.
- **OUTPUT_TEMPLATES**:
  - **`[PASS]/[FAIL]` Template**:
    ```
    [STATUS] - {CaseID}: {Case Description}
    ├─ Expected: {Brief expected result}
    └─ Actual: {Brief actual result}
    ```
  - **`[ERROR]` Template**:
    ```
    [ERROR] - {CaseID}: {Case Description}
    ├─ Description: An unexpected error occurred during test execution.
    └─ Exception: {Exception Type}: {Exception Message}
    ```
  - **`[SKIP]` Template**:
    ```
    [SKIP] - {CaseID}: {Case Description}
    └─ Reason: {From the SkipReason field in the YAML file}
    ```

## 2. Logging Rules

### Rule: Generate Detailed Log Files
- **CONTEXT**: Storing detailed execution information.
- **REQUIREMENTS**:
  - **One log file per test run**.
  - **Timestamped filename**.
  - **Store in `tests/reports/`**.
- **FILENAME_TEMPLATE**: `test-run_{YYYY-MM-DD_HH-MM-SS}.log`

### Rule: Log File Content Structure
- **CONTEXT**: Format definition for generated log files.
- **REQUIREMENT**: Must be a detailed, step-by-step transcript.
- **CONTENT_STRUCTURE**:
  1.  **Run Header**: `Test Run Started`, `Operating System`, `Runtime Version`.
  2.  **Test Suite Section**: `[SUITE START] - File: {filepath}`.
  3.  **Test Case Section**:
      - `[CASE START] - {CaseID}: {Description}`
      - `[Arrange] - Precondition: {details}`
      - `[Act] - Step: {details}`
      - `[Act Log] - {internal logs}`
      - `[Assert] - Verifying: {outcome}`
      - `[Assert Log] - {comparison details}`
      - `[RESULT] - {PASS/FAIL/ERROR/SKIP}: {reason}`
      - `[CASE END] - Duration: {duration}`
      - **Note**: For `SKIP` results, `Arrange`, `Act`, and `Assert` blocks will be omitted.
  4.  **Run Summary**: `Test Run Finished`, `Total Duration`, `Statistics`.

## 3. Post-Execution Analysis Support

### Rule: Link Console Output to Log File
- **CONTEXT**: Enabling easy navigation from console to detailed log.
- **REQUIREMENT**: The full path to the detailed log file must be printed at the end of the console run summary.
- **CONSOLE_SUMMARY_TEMPLATE**:
  ```
  ================== Test Run Summary ==================
  Total Tests: {count}
  Passed:      {count}
  Failed:      {count}
  Errors:      {count}
  Skipped:     {count}
  
  For detailed logs, see: {full_log_file_path}
  ======================================================
  ```