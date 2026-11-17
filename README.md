# Business Hub OS

An agentic operating system for an ecommerce business, built around controlled autonomy, auditable workflows, and human approval for consequential actions.

## Current baseline

The development baseline is Sprint 8:
- FastAPI backend and initial Next.js web application
- Authentication, role-based access control, tasks, approvals, and audit events
- Agent runs with deny-by-default tool permissions and idempotency
- Workflow orchestration with approval gates
- Provider-neutral AI runtime with offline mock adapters and budget controls
- Shared/private agent memory with bounded, untrusted context injection

## Safety boundaries

- No API keys, passwords, customer records, or local database files belong in this public repository.
- Live model-provider calls are disabled in the current baseline.
- Financial transfers, refunds, paid campaign publishing, and other consequential external actions require human approval.
- Approval does not itself execute an external side effect.
- Agents cannot grant themselves permissions.

## Development

See the sprint notes and patch artifacts on the feature branch for the current implementation baseline. Run backend tests with:

```bash
python -m pytest -q
```

Apply database migrations with:

```bash
alembic upgrade head
```

Never commit a real `.env` file or secrets. Use `.env.example` only as a template.

## Roadmap

1. Agent collaboration and independent review committee
2. Durable workflow execution and retries
3. Live provider adapters behind explicit configuration and budgets
4. Ecommerce integrations with scoped permissions
5. Observability, deployment hardening, and production readiness

This project is under active development and is not production-ready.
