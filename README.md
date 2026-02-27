# devkit

Product development toolkit for Claude Code. Validation, competitive analysis, and go-to-market skills for builders.

## Plugins

| Plugin | Description |
|--------|-------------|
| [**validation-skills**](plugins/validation-skills/README.md) | 11 product validation skills covering the full journey from idea to first paying customers — problem extraction, demand discovery, audience identification, positioning, pricing, smoke testing, distribution planning, go/no-go decisions, builder psychology, and market sizing |
| [**feature-teardown**](plugins/feature-teardown/README.md) | Feature-level competitive analysis — UX pattern teardowns, technical implementation research, cross-implementation pattern extraction, and prioritized build recommendations |

## Installation

Add the devkit marketplace to Claude Code:

```
/plugin marketplace add tylerpriest/devkit
```

Then install the plugins you want:

```
/plugin install validation-skills@devkit
/plugin install feature-teardown@devkit
```

## Repository Structure

```
devkit/
├── .claude-plugin/
│   └── marketplace.json            # Marketplace manifest
├── plugins/
│   ├── validation-skills/          # Product validation plugin (11 skills)
│   │   ├── .claude-plugin/
│   │   │   └── plugin.json
│   │   ├── skills/                 # 11 skill directories with SKILL.md + references
│   │   ├── tools/
│   │   │   └── REGISTRY.md         # MCP integration registry
│   │   └── README.md
│   └── feature-teardown/           # Competitive analysis plugin (1 skill)
│       ├── .claude-plugin/
│       │   └── plugin.json
│       ├── skills/
│       │   └── feature-teardown/   # 7-step methodology + 3 reference files
│       └── README.md
└── README.md
```

## License

MIT
