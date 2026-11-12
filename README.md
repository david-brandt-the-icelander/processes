# Processes

Things I make for software development processes in general: conventions, agent skills, templates and tools that are not tied to any one system. Most of them exist because most of the builders on my teams are now agents, and an agent follows a process only if the process is written down where the agent will read it. The reasoning behind them is in the Processes train on icelander.net: <https://icelander.net/v1/processes>.

## Layout

```
project-management/      conventions for running a project: the twelve documents every
                         deployable carries in its Documentation/ directory, as templates
Meta/Agents/             the skills and knowledge catalogue the .dev/ folders follow, copied
                         from human-assisted-software-development
```

Each directory has its own `README.md` saying what is in it and how to use it. Each maintained folder also has a `.dev/` directory describing it for agents: what it is for, the terms it uses, what other repositories rely on, the decisions taken and waiting, and the work wanted. [AGENTS.md](AGENTS.md) says how they are kept.

## Related repositories

- [human-assisted-software-development](https://github.com/david-brandt-the-icelander/human-assisted-software-development): human-assisted software development (HASD), including the agent skills for the `.dev/` diagrams and behavior views, and the catalogue of knowledge files. This repository's `Meta/Agents/` is a copy of them.
- [cyberspace-explorer](https://github.com/david-brandt-the-icelander/cyberspace-explorer): the Cyberspace explorer, a page that draws a repository's `.dev/` folders.
- [knowledge-driven-development](https://github.com/david-brandt-the-icelander/knowledge-driven-development): an earlier experiment, superseded by human-assisted software development. Repositories that adopted it can keep following it there.

## Using these

Copy what you need into your own repository and adjust the paths the files mention. Where a thing here is referenced rather than copied, link to it, so that there is one copy to drift.
