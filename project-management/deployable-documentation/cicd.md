# CI/CD

**Source of truth:** the pipeline files at <!-- path -->. This file says what they do and what they protect.

## On every pull request

<!-- In order: lint, build, unit tests, integration tests, security scans, documentation checks, diagram validation. For each: what fails the check, roughly how long it takes. -->

| Stage | Command | Fails when | Time |
| --- | --- | --- | --- |

## On merge to main

<!-- What is built, published or deployed automatically, and to where. -->

## On release

<!-- How a release is cut (tag, version bump, changelog), what runs, and what needs a human approval. -->

## Branch protection

<!-- Required checks, required reviewers, who can bypass and when they have. -->

## What the pipeline does not check

<!-- Honest list: manual tests, performance, the things that need production data. Each stays on this list until it is automated or accepted. -->

## Secrets the pipeline holds

<!-- By name and purpose, where they live, who can read them. -->
