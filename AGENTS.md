# Repository Guidelines

## Project Structure & Module Organization
This repository is primarily operational documentation plus a single-file HTML dashboard. `employee/` contains the role-specific AI employee prompts such as `employee/operations_manager.md` and `employee/product_manager.md`. `OFFICE_OPS/` contains the shared operations hub: `employees/ROSTER.md`, `coordination/COORDINATION_MATRIX.md`, and supporting folders for `projects/`, `quality/`, `reporting/`, `resources/`, `training/`, `processes/`, and `incidents/`. `skills/` contains reusable office workflows in `SKILL.md` format, such as `skills/daily-triage/SKILL.md` and `skills/office-manager-router/SKILL.md`. `docs/` contains project-facing instruction docs for external AI workspaces such as ChatGPT and Claude. The dashboard lives in `OFFICE_OPS/dashboard.html` and should be opened directly in a browser; no local server is required.

## Build, Test, and Development Commands
There is no package-based build system or local server workflow in this workspace. Open the dashboard directly by double-clicking `OFFICE_OPS/dashboard.html` or running:

```bash
open OFFICE_OPS/dashboard.html
```

## Coding Style & Naming Conventions
Prefer Markdown for operational content and keep sections short, scannable, and action-oriented. Use sentence-case prose with clear headings and bullet lists for procedures. For new role files, follow the existing lowercase, underscore-separated pattern like `employee/customer_success_manager.md`. For new skill folders, use lowercase hyphenated names like `skills/office-manager-router/`. Keep instruction docs in `docs/` concise and copy-paste friendly for external AI tools.

## Testing Guidelines
No automated test suite is currently present. For dashboard changes, verify manually by opening `OFFICE_OPS/dashboard.html` in a browser without starting a Python server or any other local server. When changing data references in the HTML, confirm the dashboard still renders roster, coordination, and project content without console errors. For documentation or skill changes, sanity-check file paths, referenced role names, and referenced shared documents such as `ROSTER.md` and `COORDINATION_MATRIX.md`.

## Commit & Pull Request Guidelines
Use short, imperative commit subjects such as `Add office manager router skill` or `Update ChatGPT project instructions`. PRs should include a brief summary, affected paths, manual verification steps, and screenshots for `dashboard.html` changes. If the change affects role routing, coordination logic, or external AI workspace instructions, mention which files were updated and how they stay aligned.

## Security & Configuration Tips
Keep sensitive operational data out of committed Markdown and spreadsheets. Treat uploaded-project instruction docs as public-facing prompts unless you explicitly intend otherwise, and do not place secrets, private customer data, or internal credentials in `docs/`, `skills/`, or role files.
