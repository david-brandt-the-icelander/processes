# Architecture

**Source of truth:** here. <!-- or: the .dev/ diagrams per folder; this file is the overview and the decisions. -->

## In one paragraph

<!-- What it is, what it talks to, where the state lives. A newcomer should know after this paragraph whether they are looking at a web app, a batch job or a library. -->

## Context

<!-- The deployable as one box, every external system it talks to, and the direction of each arrow. A diagram (JSON under .dev/, Mermaid, or an image with its source checked in) plus a table of the integrations: system, protocol, who owns it, what breaks if it is down. -->

## Components

<!-- The main parts inside the box and what each is responsible for. Link to the per-folder diagrams if the repository keeps them. -->

## Data

<!-- Where state lives, what the main entities are, what is personal data, how it is backed up. Schema lives with the code; this says what the schema is for. -->

## Key decisions

<!-- One entry per decision that would surprise a newcomer or be expensive to reverse. Dated. The format of an architecture decision record is fine; the point is the "why" and the alternatives rejected. -->

### <!-- YYYY-MM-DD: Decision title -->

**Context.** <!-- -->
**Decision.** <!-- -->
**Alternatives.** <!-- -->
**Consequences.** <!-- -->

## Known debt

<!-- What is wrong with the architecture as built, and what it costs to leave it. Where the repository keeps .dev/ records, each item is a tech-debt record in the folder it concerns, and this list links to it. -->
