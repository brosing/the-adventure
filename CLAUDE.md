# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Crucial AI Workflow Rule

### Planning and Model Switching Stop Rule
- **Rule**: Whenever you are in **Planning Mode** and finish creating or updating the `implementation_plan.md` (or equivalent), **you must stop execution immediately**.
- **Execution Details**:
  - Do NOT ask for the user's feedback.
  - Do NOT ask what to do next.
  - Do NOT prompt the user to proceed.
  - Simply output a brief statement (e.g., "Plan is ready. Stopping for model switch.") and stop calling tools to yield your turn. This allows the user to easily switch models.