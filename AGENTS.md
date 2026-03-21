# Repository Guidelines

## Project Structure & Module Organization
This repository is primarily documentation plus a single-file HTML operations dashboard. `employee/` contains the individual AI employee role files such as `employee/operations_manager.md` and `employee/product_manager.md`. `OFFICE_OPS/` contains the shared operations hub: `employees/ROSTER.md`, `coordination/COORDINATION_MATRIX.md`, and supporting folders for `projects/`, `quality/`, `reporting/`, `resources/`, `training/`, `processes/`, and `incidents/`. The dashboard lives in `OFFICE_OPS/dashboard.html` — open it directly in any browser, no server required.

## Build, Test, and Development Commands
There is no package-based build system or local server workflow in this workspace. Open the dashboard directly by double-clicking `OFFICE_OPS/dashboard.html` or running:

```bash
open OFFICE_OPS/dashboard.html
```

## Coding Style & Naming Conventions
Prefer Markdown for operational content and keep sections short, scannable, and action-oriented. Use sentence-case prose with clear headings and bullet lists for procedures. For new role files, follow the existing lowercase, underscore-separated pattern like `employee/customer_success_manager.md`.

## Testing Guidelines
No automated test suite is currently present. For dashboard changes, verify manually by opening `OFFICE_OPS/dashboard.html` in a browser without starting a Python server or any other local server. When changing data references in the HTML, confirm the dashboard still renders roster, coordination, and project content without console errors.

## Commit & Pull Request Guidelines
This folder is not currently a Git checkout, so no local commit history is available to infer conventions. Use short, imperative commit subjects such as `Add reporting template` or `Update dashboard copy`. PRs should include a brief summary, affected paths, manual verification steps, and screenshots for `dashboard.html` changes.

## Security & Configuration Tips
Keep sensitive operational data out of committed Markdown and spreadsheets.
