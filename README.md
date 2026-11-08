# Stack Finder

A Claude Code plugin with one agent, **`stack-finder`**, that checks before you build:
it searches a curated catalog of 1,400+ open-source libraries **and complete ready-made apps**
and tells you whether to reuse something, or not to build the thing at all.

## Install

In Claude Code:

```
/plugin marketplace add ThallyssonKlein/ToolsPlugin
/plugin install stack-finder@tools-plugin
```

## Use

Claude calls the agent on its own before starting new features. You can also ask directly:

```
use the stack-finder agent: I need to add PDF invoice generation to this app
```

It replies with a verdict: **don't build (use an existing app)**, **use a library**,
**consider**, or **build it**. It lists the matching repos and gives you one next step.

The agent is read-only. It uses `Read`, `Grep`, and `Glob`, and only looks at your project's
manifest files (`package.json`, `go.mod`, ...) to check stack compatibility.

## Catalog

`data/catalog.csv` has the columns `Name,Category,Description,URL`. To add an entry, append a row,
bump `version` in `.claude-plugin/plugin.json`, and push. Users pick up the change with
`/plugin marketplace update tools-plugin`.

## License

MIT
