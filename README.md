# Skills Registry

Repository of skills for AI coding agents managed by [dirx](https://github.com/diegorramos/dirx).

## Purpose

This registry is a **pure catalog of skills**. It contains no agent-specific information. All agent knowledge (paths, transforms, frontmatter) lives exclusively in [dirx](https://github.com/diegorramos/dirx).

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

Each skill is agent-agnostic and follows this structure:

```
skills/<category>/<skill-name>/
├── SKILL.md            # universal skill content
└── references/         # optional linked files
    ├── file1.md
    └── file2.md
```

- **SKILL.md** — The skill content with YAML frontmatter (name, description). Works with any agent.
- **references/** — Optional supporting files linked from SKILL.md.

## registry.json

The registry metadata file lists all available skills:

```json
{
  "repository": "diegorramos/skills-registry",
  "branch": "main",
  "skills": [
    {
      "name": "spdd-canvas",
      "version": "1.0.0",
      "description": "Generate a complete REASONS Canvas from the latest analysis",
      "category": "development",
      "tags": ["spdd", "canvas", "reasons", "prompt"],
      "authors": ["diegorx"]
    }
  ]
}
```

No agent-specific fields. dirx handles all agent transformation.

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
| teach | development | Teach the user a new skill or concept, within this workspace. |

## Adding a Skill

1. Create a directory under the appropriate category: `skills/<category>/<skill-name>/`
2. Add `SKILL.md` with YAML frontmatter (`name`, `description`) and the skill content
3. Optionally add `references/` folder with linked supporting files
4. Update `registry.json` with the new skill entry (name, version, description, category, tags, authors)

No agent-specific files needed. dirx transforms SKILL.md for each agent automatically.

## Usage with dirx

```bash
# List all skills
dirx list

# Search skills
dirx search spdd

# Install interactively (select category, skills, agents, scope)
dirx install

# Install a specific skill
dirx install spdd-canvas
```

## License

MIT
