# Mermaid Plugin for Claude Code

A Claude Code plugin for generating [Mermaid](https://mermaid.js.org/) diagrams. Supports 23 diagram types including flowcharts, sequence diagrams, class diagrams, ER diagrams, Gantt charts, and more.

## Installation

### Share with a team via `extraKnownMarketplaces` (recommended for teams)

Add this to your project's `.claude/settings.json` to make the plugin discoverable for everyone who works in the repository:

```json
{
  "extraKnownMarketplaces": {
    "mermaid": {
      "source": {
        "source": "github",
        "repo": "thdk/mermaid-skill"
      }
    }
  }
}
```

Each team member then installs it once:

```
/plugin install mermaid@mermaid
```

To enable it automatically for all team members without a manual install step, also add:

```json
{
  "extraKnownMarketplaces": {
    "mermaid": {
      "source": {
        "source": "github",
        "repo": "thdk/mermaid-skill"
      }
    }
  },
  "enabledPlugins": {
    "mermaid@mermaid": true
  }
}
```

### As a plugin (personal use)

Load for a single session:

```bash
claude --plugin-dir ./mermaid-skill
```

Install permanently at user scope:

```bash
claude plugin install mermaid
```

### As a standalone skill (legacy)

Copy the skill folder directly into your project's `.claude/` directory:

```bash
git clone https://github.com/thdk/mermaid-skill.git
cp -r mermaid-skill/skills/generate /path/to/your/project/.claude/skills/
```

## Usage

When installed as a plugin, invoke the skill with:

```
/mermaid:generate create a flowchart for user login process
/mermaid:generate draw a sequence diagram for API authentication
/mermaid:generate ER diagram for an e-commerce database
```

## Supported Diagrams

| Category | Diagram Types |
|----------|---------------|
| Flow & Process | Flowchart, State Diagram, User Journey |
| Structural | Class Diagram, ER Diagram, C4 Diagram, Architecture Diagram |
| Temporal | Sequence Diagram, Gantt Chart, Timeline, Git Graph |
| Data Visualization | Pie Chart, XY Chart, Sankey Diagram, Quadrant Chart, Radar Chart, Treemap |
| Organization | Mindmap, Kanban, Block Diagram, Requirement Diagram |
| Technical | Packet Diagram, ZenUML |

## Project Structure

```
mermaid-skill/
├── .claude-plugin/
│   ├── plugin.json        # Plugin manifest
│   └── marketplace.json   # Marketplace catalog (enables extraKnownMarketplaces)
└── skills/
    └── generate/
        ├── SKILL.md           # Skill definition and instructions
        └── references/        # Mermaid syntax documentation
            ├── flowchart.md
            ├── sequenceDiagram.md
            ├── classDiagram.md
            └── ...
```

## Documentation Sync

This plugin includes a GitHub Action that automatically syncs documentation from the official [mermaid-js/mermaid](https://github.com/mermaid-js/mermaid) repository weekly.

## License

[MIT](LICENSE)
