# Deployable documentation

Twelve Markdown files that every deployable carries, in a `Documentation/` directory under the deployable's root folder. If one of them is missing, nobody has written down the thing it covers, and the project is running on somebody's memory.

A **deployable** is a thing that gets deployed as a unit: a service, a Worker, an app, a scheduled job, a library that is published as a package. A **repository** is where source is kept. Often the two are the same thing and `Documentation/` sits at the top of the repository. In a monorepo, each deployable gets its own `Documentation/` under its own root, and the repository's top level keeps only what is shared.

Each file is either **the source of truth** for its subject or **a pointer to it** (the business plan is often a document elsewhere; the on-call rota usually lives in the paging tool). A pointer file still says, in a paragraph, what the reader will find there and why it matters to this deployable, so that the link going dead is noticed. The first line after the title of every template records which of the two it is.

| File | Answers |
| --- | --- |
| [business-plan.md](business-plan.md) | Why this exists, who pays for it, and when it should be shut down |
| [stakeholders.md](stakeholders.md) | Who cares, who decides, and who gets to say no |
| [risk-assessment.md](risk-assessment.md) | What could go wrong, how badly, and what is being done about it |
| [requirements.md](requirements.md) | What it does, as capabilities and features, with their marks |
| [non-functional-requirements.md](non-functional-requirements.md) | How well it has to do it: performance, availability, security, cost, compliance |
| [architecture.md](architecture.md) | How it is built, its boundaries, and the decisions that got it here |
| [deployment.md](deployment.md) | Where it runs, how it gets there, and how to roll it back |
| [cicd.md](cicd.md) | What the pipeline does, what blocks a merge, and what blocks a release |
| [development.md](development.md) | How to get it running on a laptop and how a change gets in |
| [operations.md](operations.md) | How it is run day to day: runbooks, routine tasks, incident handling |
| [observability.md](observability.md) | What it reports about itself, where that goes, and what wakes somebody up |
| [contacts.md](contacts.md) | Who to call, about what, and how |

## Using the templates

1. Copy this directory to `<deployable root>/Documentation/` and delete this `README.md`.
2. Fill in each file, or replace its body with a pointer and a paragraph. Delete the HTML comments as you go; they are instructions to the writer, not content.
3. Keep the files in the same commits as the changes they describe. A file nobody has touched since the first commit is a file nobody reads.
4. If the repository follows [human-assisted software development](https://github.com/david-brandt-the-icelander/human-assisted-software-development), its capabilities, features, use cases, intended work and technical debt are described in the `.dev/` folders next to the code, and `requirements.md` and `architecture.md` point at them rather than repeating them.

Add to the repository's `AGENTS.md`:

```markdown
## Documentation

Every deployable carries `Documentation/` with the twelve files described at
https://github.com/david-brandt-the-icelander/processes/tree/main/project-management/deployable-documentation.
Read the relevant ones before changing the deployable, and update them in the same commit as the change.
A change that adds a dependency, a port, a secret, an alert or an external contact is not finished until
the file that lists those says so.
```
