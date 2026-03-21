# Repository Guidelines

## Project Structure & Module Organization
This repository is primarily documentation plus a lightweight operations dashboard. `employee/` contains the individual AI employee role files such as `employee/operations_manager.md` and `employee/product_manager.md`. `OFFICE_OPS/` contains the shared operations hub: `employees/ROSTER.md`, `coordination/COORDINATION_MATRIX.md`, and supporting folders for `projects/`, `quality/`, `reporting/`, `resources/`, `training/`, `processes/`, and `incidents/`. The dashboard lives in `OFFICE_OPS/dashboard.html`, with a simple local server in `OFFICE_OPS/server.py`. Spreadsheet scorecards are kept at the repository root as `.xlsx` files.

## Build, Test, and Development Commands
There is no package-based build system in this workspace. Use:

```bash
python3 OFFICE_OPS/server.py
```

Starts a local server for `http://localhost:8000/dashboard.html`.

```bash
open OFFICE_OPS/dashboard.html
```

Opens the static dashboard directly; use this when live refresh is not needed.

```bash
python3 --version
```

Confirms Python 3 is available before running the dashboard server.

## Coding Style & Naming Conventions
Prefer Markdown for operational content and keep sections short, scannable, and action-oriented. Use sentence-case prose with clear headings and bullet lists for procedures. For new role files, follow the existing lowercase, underscore-separated pattern like `employee/customer_success_manager.md`. Python changes in `OFFICE_OPS/server.py` should follow PEP 8, 4-space indentation, and small, readable functions.

## Testing Guidelines
No automated test suite is currently present. For dashboard changes, verify manually by opening `OFFICE_OPS/dashboard.html` and, if relevant, reloading the server-backed version after editing source Markdown files. When changing data references, confirm the dashboard still renders roster, coordination, and project content without console errors.

## Commit & Pull Request Guidelines
This folder is not currently a Git checkout, so no local commit history is available to infer conventions. Use short, imperative commit subjects such as `Add reporting template` or `Update dashboard copy`. PRs should include a brief summary, affected paths, manual verification steps, and screenshots for `dashboard.html` changes.

## Security & Configuration Tips
Keep sensitive operational data out of committed Markdown and spreadsheets. `OFFICE_OPS/server.py` is a local-only helper; do not treat it as a production service without hardening.
