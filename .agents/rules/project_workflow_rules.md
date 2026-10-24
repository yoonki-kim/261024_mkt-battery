# Rule: Project Workflow, Git Policy & Work History Continuity

## 1. Git Commit Policy
- **Strict Rule**: Do NOT run `git commit` or `git push` autonomously.
- Git commits and pushes must **ONLY be executed when explicitly requested by the USER**.
- Keep changes in the working tree until the user issues a commit instruction.

## 2. Work History & Session Continuity
- **Mandatory Starting Step**:
  - Whenever starting a new session or resuming work, the agent must **first read the latest work history file** in `docs/` matching `docs/*work_history.md` (e.g. `docs/261024_work_history.md`).
  - Reconstruct the full context, previous achievements, component specs, and next tasks from this history before proceeding.
- **Reverse Chronological Logging with Timestamps**:
  - Log entries must record both **Date and Time (`YYYY-MM-DD HH:MM`)**.
  - **Always insert new log entries at the TOP (reverse chronological order)** so that the most recent work history is immediately visible without scrolling to the bottom.
- **Log Updates**:
  - After completing major milestones or tasks, update the work history file with timestamped entries, progress logs, and updated next steps.

## 3. Document Revision History Preservation (Individual Document Rule)
- **Do Not Overwrite/Delete Previous Revisions**:
  - Whenever updating any technical specification or document, do NOT delete or replace previous revision entries with a single "last modified" line.
  - Maintain a dedicated **`## 개정 이력 (Revision History)`** section at the bottom of the document.
  - Record the version number (v1.0, v1.1, v1.2, etc.), timestamp (`YYYY-MM-DD HH:MM`), and detailed modification rationale in **reverse chronological order (newest on top)**, preserving all historical change logs.

## 4. File Naming Convention
- All newly created documentation, specs, and source files must start with the `YYMMDD_` prefix (e.g., `261024_<filename>.<ext>`), with exceptions only for conventional files like `README.md`, `.gitignore`, etc.
