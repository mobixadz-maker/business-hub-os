# Sprint 4–8 Import Guide

## What is in this branch

This branch contains the complete cumulative patch artifact:

- `artifacts/business-hub-os-sprint4-to-sprint8.patch`

The patch was retrieved from the project's saved Sprint 8 artifact and uploaded as UTF-8 text. Its GitHub blob was fetched again to verify the full 62,387-character content.

## Important: this is not yet a source-tree import

The patch is a delta from the existing Sprint 4 baseline. It is not a standalone source archive. The repository was initially empty, so the patch cannot be applied until the Sprint 4 baseline source tree is imported.

The patch must be applied to a clean copy of the matching Sprint 4 baseline, then tested before its resulting source files are committed here. Do not apply it to an unrelated codebase.

## Verified development evidence

On the existing local Sprint 8 working copy, the following checks were run:

- `python -m pytest -q`: 26 passed
- `python -m compileall -q apps core migrations tests`: passed
- Alembic upgrade through `0006_agent_memory` on SQLite: passed

These checks describe the local Sprint 8 working copy, not a CI run on this GitHub branch.

## Security exclusions

Do not commit local `.env` files, API credentials, customer records, or SQLite development databases. The local development database is intentionally excluded. Keep live provider calls disabled until secure credential management, permissions, budgets, and operational review are implemented.

## Next import steps

1. Import the exact Sprint 4 baseline source tree.
2. Apply the cumulative Sprint 4–8 patch.
3. Run the test suite and migrations in CI.
4. Review the generated diff for secrets and unintended local artifacts.
5. Only then propose the source-tree changes for merge to `main`.

No merge to `main` is authorized by this guide.
