# Non-functional requirements

**Source of truth:** here.

<!-- How well it has to work. Every row is a number or a yes/no, with how it is measured and whether it is currently met. Vague rows ("fast", "secure") are deleted or made specific. Status is met, not met, or not checked. -->

| Area | Requirement | Measured by | Status |
| --- | --- | --- | --- |
| Availability | <!-- e.g. 99.5% monthly, measured at the public endpoint --> | <!-- the probe or dashboard --> | met / not met / not checked |
| Latency | <!-- e.g. p95 under 300 ms for reads --> | | |
| Throughput / capacity | <!-- e.g. 50 requests/s sustained, 10× for an hour --> | | |
| Data durability | <!-- e.g. no loss of a committed write; backups daily, restore tested quarterly --> | | |
| Recovery | <!-- RTO and RPO --> | | |
| Security | <!-- authentication method, authorization model, secrets handling, dependency scanning --> | | |
| Privacy | <!-- personal data held, lawful basis, retention period, deletion path --> | | |
| Compliance | <!-- standards or regulations that apply, and the evidence --> | | |
| Accessibility | <!-- e.g. WCAG 2.2 AA for the web UI --> | | |
| Localization | <!-- languages, locales, time zones --> | | |
| Cost | <!-- monthly ceiling, and what happens when it is reached --> | | |
| Supportability | <!-- supported browsers, platforms, API versions; deprecation policy --> | | |
| Maintainability | <!-- test coverage floor, build time ceiling, dependency update cadence --> | | |

## Trade-offs

<!-- Where one row was traded against another, and who agreed. -->
