# Halvend Forge Works — Supplier Portal

## Repository Status

**🚧 Coming soon — not yet released**

This repository will contain the supplier-facing portal for Halvend Forge
Works. What is present today is the initial project scaffold: the application
shell, API skeleton, infrastructure definitions and contract tests have been
laid down so that implementation can start, but the portal is not available to
suppliers and has not been released for production use.

A preview address exists for internal reviewers only and must not be circulated
to suppliers: https://preview.halvendforge.dev

## Overview

The finished portal will let Halvend suppliers download statements, view
open invoices, upload compliance documents and retrieve remittance advice
without contacting the purchasing desk.

## Stack

- React + TypeScript single page application (`apps/web`)
- FastAPI service (`services/api`)
- PostgreSQL for transactional data
- Terraform-managed infrastructure (`infra/terraform`)
- Contract tests under `tests/contract`

## Local development

```
python -m venv .venv
source .venv/bin/activate
pip install -r services/api/requirements.txt
uvicorn services.api.app:app --reload
```

The web client can be started with `npm install && npm start` from `apps/web`.

## Repository layout

```
apps/web/src        React application
services/api        FastAPI service and routes
infra/terraform     infrastructure definitions
tests/contract      API contract tests
docs                architecture and operating notes
config              environment configuration
```

## Roadmap

1. Complete supplier authentication integration.
2. Complete the statement export and remittance download flows.
3. Pass the external security review.
4. Production release (date to be confirmed by the platform team).

## Contribution

Create a feature branch, run `pytest tests/contract` and `npm test` before
opening a pull request.  Changes to infrastructure require a platform review.
