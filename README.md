# TTC Delay Analysis

Where, when, and why do TTC delays concentrate, and what predicts a major
delay? This project combines a reproducible R pipeline with versioned SQL
aggregation in PostgreSQL.

The analysis is built from the City of Toronto's open TTC delay datasets for
subway, bus, and streetcar service. Raw data is downloaded from the City's
CKAN API and is not committed to the repository.

**Status:** work in progress. The final README, findings, and report are
written after the pipeline has run.

## Layout

```
R/              numbered pipeline scripts, 00_config.R through 08_findings.R
scripts/        run_all.R entry point
sql/            schema, staging, analytical views, data-quality checks
docs/           dataset research, pre-registered plan, methods, findings
outputs/        generated figures and tables (committed)
reports/        stakeholder report source and rendered HTML
tests/testthat/ pipeline assertions
```

## Run

```bash
docker compose up -d postgres
make deps
make pipeline
```

The local database defaults to port 5434 so it does not collide with other
projects on 5432. Override with `TTC_DB_*` environment variables if needed.

## Licence

Code is MIT licensed. The underlying data is published by the City of Toronto
under the Open Government Licence - Toronto.
