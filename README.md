# Skills Registry

Repository of skills for AI coding agents managed by [dirx](https://github.com/diegorramos/dirx).

## Structure

```
skills/
├── development/     # Business logic, architecture, patterns
├── ui/              # Frontend, components, design systems
├── devops/          # CI/CD, deploy, infrastructure
├── security/        # Auditing, OWASP, secure coding
├── testing/         # TDD, BDD, performance tests
├── documentation/   # Docs, READMEs, ADRs
├── data/            # Pipelines, ETL, queries
└── ai-ml/           # Prompts, fine-tuning, evals
```

## Skill Format

Each skill follows the universal format:

```
skills/<category>/<skill-name>/
├── manifest.json       # metadata, agents, version
├── SKILL.md            # universal skill content
└── adapters/           # agent-specific files
    ├── opencode/SKILL.md
    ├── devin/SKILL.md
    └── claude/commands/<name>.md
```

## Available Skills

| Skill | Category | Description |
|-------|----------|-------------|
| sdd-workflow | development | Full SDD cycle: clarify requirements -> spec -> design -> task breakdown |
| spdd-analyze | development | Analyze requirements and scan codebase to surface domain concepts, risks, and design direction |
| spdd-canvas | development | Generate a complete REASONS Canvas from the latest analysis |
| spdd-generate | development | Implement code using strict TDD (Red -> Green -> Refactor) per Canvas Operations |
| spdd-perftest | testing | Generate performance tests from the Canvas Safeguards and Requirements |
| spdd-review | development | Review the current implementation against the REASONS Canvas |
| spdd-risk-review | development | Validate that all risks are mitigated before any code is written |
| spdd-story | development | Break requirements or tasks into INVEST-compliant user stories |
| spdd-sync | development | Sync code changes back to the REASONS Canvas |
| spdd-test | testing | Derive functional test scenarios from the Canvas for TDD implementation |
| spdd-update | development | Update the REASONS Canvas when requirements change (prompt-first rule) |

## Adding a Skill

1. Create a directory under the appropriate category
2. Add `manifest.json` with metadata
3. Add `SKILL.md` with the universal skill content
4. Add agent-specific adapters in `adapters/` folder
5. Update `registry.json` with the new skill

## Usage with dirx

```bash
# List all skills
dirx list

# Search skills
dirx search spdd

# Install a skill
dirx install spdd-canvas
```

## License

MIT
