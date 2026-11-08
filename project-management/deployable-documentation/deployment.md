# Deployment

**Source of truth:** here. <!-- The pipeline configuration is the executable truth; this says what it does and why. -->

## Environments

| Environment | Where | URL / endpoint | Deployed by | Data |
| --- | --- | --- | --- | --- |
| Local | developer machine | | `npm run dev` or equivalent | fixtures |
| Staging | | | pipeline on merge to main | anonymized copy / synthetic |
| Production | | | pipeline on tag / manual approval | real |

## What gets deployed

<!-- The artifact: container image, Worker bundle, package, installer. Where it is stored, how it is named and versioned, how long it is kept. -->

## How a deployment happens

<!-- Step by step, including approvals. Who may deploy to production. Deployment windows if any. -->

## Configuration and secrets

<!-- Every configuration value and secret the deployable needs, by name, with where it is set (never its value). What happens if one is missing. -->

| Name | Purpose | Set in | Rotated |
| --- | --- | --- | --- |

## Rollback

<!-- The exact procedure, how long it takes, and what it cannot undo (migrations, sent emails). Date it was last rehearsed. -->

## Infrastructure

<!-- Accounts, projects, DNS, certificates, and who owns them. Link to infrastructure-as-code if it exists. -->
