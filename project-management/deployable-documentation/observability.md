# Observability

**Source of truth:** here. <!-- Alert definitions in code are the executable truth; this says what exists and why. -->

## Health

<!-- The health endpoint or probe, what it checks, and who polls it. -->

## Logs

<!-- What is logged, in what format, where it goes, how long it is kept, what must never be logged (secrets, personal data). How to find the logs for one request. -->

## Metrics

<!-- The metrics that matter, where they are shown, and what normal looks like. Link to the dashboard. -->

| Metric | Meaning | Normal | Dashboard |
| --- | --- | --- | --- |

## Traces

<!-- If distributed tracing exists: what is traced, where to look. If not, say so. -->

## Alerts

<!-- Every alert: condition, severity, who it pages, and the runbook in operations.md it points at. An alert without a runbook is noise. -->

| Alert | Condition | Severity | Pages | Runbook |
| --- | --- | --- | --- | --- |

## What is not observed

<!-- The honest list, each a ⚠️: silent failures that would not be noticed, and how they would eventually be found. -->
