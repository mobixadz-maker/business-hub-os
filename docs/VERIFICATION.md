# Verification Record — Sprint 8 baseline

This record distinguishes checks run against the local working copy from checks
run by GitHub Actions. It is not a claim that CI has run on this pull request.

## Local working-copy checks

The following checks were run against the Sprint 8 working directory:

- `python -m pytest -q`: **26 passed**.
- `python -m compileall -q apps core migrations tests`: passed.
- Cumulative Sprint 4 → Sprint 8 patch dry-run against the Sprint 4 archive:
  `patch -p1 --dry-run`: passed.

## Repository import status

The repository currently contains the project README, the cumulative patch
artifact, and import/verification documentation. The complete application
source tree has **not** yet been expanded into this repository.

The cumulative patch is a delta and requires the matching Sprint 4 source
baseline. Do not merge this draft until the source tree is imported, the patch
is applied to that tree, and repository CI passes.

## Security boundaries

- Never commit real `.env` files, API keys, private keys, credentials, customer
  records, or local database files.
- Keep `.env.example` limited to placeholder values.
- AI provider adapters in this baseline are offline/mock adapters; no live
  provider connectivity is claimed.
- Approval of a consequential action is not itself execution of an external
  side effect.
