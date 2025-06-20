# project_design_guides

A simple rulebook for an AI agent to build high-quality, consistent software.

This repository provides a set of clear, machine-readable rules that guide an AI through common development tasks, from writing documentation to designing tests.

## The Guides

This project provides five core documents, designed to live in a `_guidelines` folder:

*   `CONTRIBUTING.md`: The main instruction manual for the AI.
*   `DEV_DOC_SOP.md`: Rules for documentation (APIs, requirements, etc.).
*   `TESTING_SOP.md`: Rules for test file structure and formatting.
*   `TEST_CASE_DESIGN_SOP.md`: Rules for *how* to design good tests.
*   `TEST_CODE_IMPLEMENTATION_SOP.md`: Rules for the test runner's output and logging.

## How to Use

Follow these three steps to integrate this rulebook into your own project:

**1. Add the Guides**

Clone this repository into a `_guidelines` directory in your project's root:

```bash
# Replace with your repository's URL
git clone https://github.com/Lancelotmay/project_design_guides.git _guidelines
```

**2. Ignore the Guides in Git**

Add `/_guidelines` to your project's root `.gitignore` file. This keeps its history separate from your project's.

```.gitignore
# .gitignore

/_guidelines
```

**3. Set the AI's Instructions**

Copy the main instruction file into your project's root. This is the first file the AI will read.

```bash
cp _guidelines/CONTRIBUTING.md ./CONTRIBUTING.md
```

Your project is now ready. The AI will use the `CONTRIBUTING.md` to understand its workflow and consult the rules in `_guidelines` for every task.

## How It Works

The `CONTRIBUTING.md` file instructs the AI to follow a simple, two-step engineering workflow:

1.  **Decompose Task**: Break any complex request into a simple checklist.
2.  **Execute using SOPs**: For each item on the checklist, consult the appropriate rulebook in `_guidelines`.

This ensures every action is deliberate and follows the project's standards.

## License

This project is licensed under the **GNU General Public License v3.0 (GPLv3)**. Please be aware of the terms of this license when integrating these guides into your own projects.