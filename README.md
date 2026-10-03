# omp-graft

Bridge between [Graft](https://github.com/trailhq/Graft) and
[OMP](https://github.com/canva/omp): a per-repo **context graph** as an agent
skill + tools.

Graft keeps a `graft/` directory per repo — tree-sitter wiring cards (every
symbol, its file:line span, who calls what) plus, after `graft build --deep`,
LLM-written markdown nodes. This extension surfaces that graph to the agent as
tools and installs the skill that teaches it when the graph beats grep/glob/
LSP — and when it doesn't.

## Install

```sh
# Graft CLI must be installed first: https://github.com/trailhq/Graft
cp extensions/graft.ts ~/.omp/agent/extensions/
mkdir -p ~/.omp/agent/skills/graft
cp skills/graft/SKILL.md ~/.omp/agent/skills/graft/
```

## What the agent gets

- tools to query the repo's wiring: who calls this symbol, where is it
  defined, what's the blast radius of a change
- the skill's decision table: graph for orientation / API surfaces / impact
  analysis; grep/LSP for everything else

## License

MIT
