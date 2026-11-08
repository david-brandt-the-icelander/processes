# Agent skills

Skills that tell an agent how to do one particular job in a repository. Each skill is a folder with a `skill.md`: a short Markdown file whose front matter gives the skill's `name` and a one-line `description` an agent can match a task against, followed by a page of instructions. Where a skill produces a file, the folder also holds the JSON schema that file must follow and a complete, fictional example of a correctly filled-out one. Both Claude Code and Codex read this format.

## The skills

| Skill | Use it when | Produces |
| --- | --- | --- |
| [describe-component-diagram](describe-component-diagram/skill.md) | A folder is a cohesive capability, adapter, boundary or subsystem that belongs in a system component diagram | `<folder>/.dev/component-diagram.json` |
| [describe-class-diagram](describe-class-diagram/skill.md) | A folder declares more than one class (records, nested and partial classes counted; descendant folders not) | `<folder>/.dev/class-diagram.json` |
| [describe-state-diagram](describe-state-diagram/skill.md) | A folder implements a state machine; one file per machine, named after its class | `<folder>/.dev/<Identifier>.state-diagram.json` |
| [describe-deployment-diagram](describe-deployment-diagram/skill.md) | A folder contains an independently deployable executable, service, container or package | `<folder>/.dev/deployment-diagram.json` |
| [knowledge-driven-development](knowledge-driven-development/skill.md) | The repository follows [knowledge-driven development](https://github.com/david-brandt-the-icelander/knowledge-driven-development): planning a feature, moving a mark, reviewing a pull request, adopting the convention | Marked knowledge documents, change logs |

`validate_diagrams.py` checks the four diagram schemas and their examples, then every `.dev/*.json` diagram in the repository (skipping `.git`, `node_modules` and build output): schema validity, unique IDs, relationship endpoints, the folder each diagram claims, source paths that exist, and child-diagram references that point at a diagram of the right kind for the right folder. It needs the `jsonschema` package. Schema validation shows a diagram is well-formed, not that it is true; truth is checked by an agent reading the sources the diagram cites.

## The `.dev/` convention

Architecture is documented next to the code it describes. Every source folder with something architectural to say gets a `.dev/` directory holding JSON diagrams that follow the schemas here. Diagrams are drawn bottom up: a folder's component diagram lists its direct children and references their diagrams by repository-relative path, so the folder tree is the component tree. Each diagram records the source paths and symbols it was derived from, so a reviewer can verify it. Diagrams change in the same commit as the code and are deleted, not kept, when they stop applying. The rules in the skills are mostly about what not to draw: no invented transitions, servers or ports, no component per namespace, no method bodies, credentials or configuration values, and no running the application to document it.

## Installing in a repository

1. Copy the skill folders and `validate_diagrams.py` to `Meta/Agents/Skills/` in the target repository. The skills refer to that path; the validator finds the schemas next to itself and scans the whole repository for `.dev/*.json`.
2. Add to the top-level `AGENTS.md` a concise statement of when to use the skills, for example:

   ```markdown
   ## Architecture diagrams

   Architecture is documented per folder in `.dev/` directories as JSON diagrams, using the skills
   under `Meta/Agents/Skills/`. Use `describe-component-diagram` when a folder is a cohesive
   capability, adapter, boundary or subsystem; `describe-class-diagram` when a folder declares more
   than one class; `describe-state-diagram` when a folder implements a state machine, one file per
   machine named after its class; and `describe-deployment-diagram` when a folder contains an
   independently deployable executable, service, container or package. Read the relevant diagrams
   before changing a folder, update them in the same commit as the code, and run
   `python3 Meta/Agents/Skills/validate_diagrams.py` before finishing.
   ```

   For knowledge-driven development, add the block from that repository's `templates/agent-instructions.md`.
3. Make `CLAUDE.md` a pointer to `AGENTS.md`, so Claude and Codex read one set of instructions:

   ```markdown
   Read `AGENTS.md`. It is the single set of instructions for every agent working in this repository.
   ```

4. Run the validator from the repository root:

   ```bash
   python3 Meta/Agents/Skills/validate_diagrams.py
   ```

## Writing a new skill

One folder, one `skill.md`, one job. Say when to use it, what goes in, what stays out, and how to check the result. Where it produces a file, add `schema.json` and an `example.json` that says in its own description that it is fictional, so an agent does not take it as evidence about the system in front of it. Keep it to a page: skills are read on every task they apply to.
