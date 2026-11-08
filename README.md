# Processes

Things I make for software development processes in general: conventions, agent skills, templates and tools that are not tied to any one system. Most of them exist because most of the builders on my teams are now agents, and an agent follows a process only if the process is written down where the agent will read it. The reasoning behind them is in the Processes train on icelander.net: <https://icelander.net/v1/processes>.

## Layout

```
Agents/
  Skills/        agent skills: how an agent does one particular job in a repository
                 (architecture diagrams per folder, knowledge-driven development)
```

Each directory has its own `README.md` saying what is in it and how to use it.

## Related repositories

- [knowledge-driven-development](https://github.com/david-brandt-the-icelander/knowledge-driven-development): the canonical statement of the convention where the documents describing a system are its backlog, and every statement carries a mark saying whether it is true yet. Repositories link to it rather than restating it; the skill here does the same.

## Using these

Copy what you need into your own repository and adjust the paths the files mention. Where a thing here is referenced rather than copied, link to it, so that there is one copy to drift.
