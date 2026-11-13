# Agent instructions

This repository holds conventions, templates and tools for software development processes that are not tied to any one system. Start with [README.md](README.md); each directory has its own `README.md` saying what is in it and how to use it. Other repositories copy or link to what is here, so a file that moves or is renamed breaks links elsewhere: read the folder's `.dev/contracts.json` before moving anything.

## Architecture diagrams and knowledge files

Each maintained folder documents itself in a `.dev/` directory next to it, as JSON following the skills in `Meta/Agents/Skills/` and the knowledge catalogue in `Meta/Agents/Knowledge/` (human-assisted software development). Read a folder's `.dev` files before changing it. `populate-dev` decides what a folder needs.

The folders here hold Markdown documents and templates, not code, so the only diagram is the root's:

- `describe-component-diagram`: the repository root, whose parts are `project-management`, `Meta/Agents` and the human-assisted-software-development repository they relate to. Give another folder one only when it becomes a cohesive capability, adapter, boundary or subsystem.
- `describe-class-diagram`, `describe-state-diagram`, `describe-deployment-diagram`: no folder. Use them if a folder comes to declare more than one class (the class diagram), implement a state machine (one `<Identifier>.state-diagram.json` per machine, named after its class) or hold something deployed on its own (the deployment diagram).

No folder has a behavior view (`describe-use-case`, `describe-user-journey`, `describe-capability`, `describe-feature`, `describe-operation`), because no code is behind them; do not turn the documents' prose into diagrams or views. What the folders get is knowledge files, written with `describe-knowledge`:

- the root: `folder`, `vision`, `references` and `decisions`, beside its component diagram;
- `project-management`: `folder`;
- `project-management/deployable-documentation`: `folder`, `glossary`, `contracts`, `references`, `decisions` and `backlog`.

Wanted work is a `backlog` item in the folder that will own it, and a question only the owner can answer is a `decisions` record with `status: open`. Every actor a use case, journey or diagram names would have a file in `Actors/` at the repository root, written with `describe-actor`; none does today, so there is no `Actors/`. Update the `.dev` files in the same commit as the documents they describe, and delete one that stops applying. Before finishing, run both validators from the repository root, with the `jsonschema` package installed:

```bash
python3 Meta/Agents/Skills/validate_diagrams.py
python3 Meta/Agents/Knowledge/validate_knowledge.py
```

The skills and the catalogue come from <https://github.com/david-brandt-the-icelander/human-assisted-software-development> (`Agents/Skills` and `Agents/Knowledge`). Change them there and copy them here, so there is one version.
