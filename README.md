# OpenClaw Multi-Agent Wizard

[中文说明](./README.zh-CN.md)

![GitHub Release](https://img.shields.io/github/v/release/majiabin2020/openclaw-multi-agent-wizard)
![GitHub License](https://img.shields.io/github/license/majiabin2020/openclaw-multi-agent-wizard)
![GitHub Actions Workflow Status](https://img.shields.io/github/actions/workflow/status/majiabin2020/openclaw-multi-agent-wizard/validate.yml?branch=main)

A beginner-friendly OpenClaw skill for Codex that guides users through multi-agent setup step by step, with safe defaults, simple explanations, and Feishu-focused onboarding.

![OpenClaw Multi-Agent Wizard preview](./assets/repo-preview.svg)

## Why This Repository Exists

Most multi-agent setup guides assume the user already understands agent IDs, bindings, routing, group mapping, and channel integration details.

This skill takes the opposite approach:

- start from a beginner-friendly question
- recommend the safest mode first
- generate starter agent profile files automatically
- explain each setup step in plain language
- verify before calling the setup complete

## What It Helps You Do

- choose a beginner-friendly multi-agent mode
- create one or more OpenClaw agents
- generate starter profile files for each agent
- connect Feishu bots step by step
- configure safe routing defaults
- summarize the final setup in simple language

## Supported Modes

### 1. Multi-bot, multi-agent

One bot maps to one agent.

Examples:

- work bot -> work assistant
- life bot -> life assistant

This is the recommended default for beginners.

### 2. Single-bot, multi-agent

One Feishu bot is shared, while different Feishu groups map to different agents.

Examples:

- product group -> product assistant
- engineering group -> engineering assistant

V1 supports group-based routing only for this mode.

### 3. A2A collaboration

One main agent responds publicly while one or more worker agents help in the background.

Examples:

- main assistant replies in Feishu
- data assistant gathers numbers
- writing assistant polishes the final answer

## What Gets Generated

For each new agent workspace, the helper scripts can generate:

- `IDENTITY.md`
- `SOUL.md`
- `AGENTS.md`
- `MEMORY.md`
- `TOOLS.md`
- `USER.md`

This gives each agent a lightweight starter identity, role boundary, collaboration shape, and user-facing purpose.

## Feishu Focus

This repository currently prioritizes Feishu because it is a practical onboarding path for beginner OpenClaw users.

The setup flow is intentionally broken into small steps:

1. create a Feishu app
2. enable bot capability
3. copy `App ID` and `App Secret`
4. finish event subscription
5. connect OpenClaw
6. bind the bot or group routing
7. verify the result

## Project Principles

- preflight first
- one small step at a time
- safe defaults over advanced options
- minimal config edits
- verify before claiming success
- optimize for beginner success, not maximum feature coverage

## Current Boundaries

- single-bot multi-agent supports Feishu group routing only
- private-chat routing is treated as advanced
- advanced runtime orchestration is explained carefully, not enabled by default
- same-group public multi-agent chatter is treated as experimental

## Directory Structure

```text
openclaw-multi-agent-wizard/
|-- SKILL.md
|-- README.md
|-- README.zh-CN.md
|-- LICENSE
|-- CONTRIBUTING.md
|-- CODE_OF_CONDUCT.md
|-- CONTRIBUTORS.md
|-- agents/
|   `-- openai.yaml
|-- assets/
|   |-- icon-small.svg
|   |-- icon-large.svg
|   `-- repo-preview.svg
|-- references/
|   |-- a2a-mode.md
|   |-- advanced-mode.md
|   |-- command-branches.md
|   |-- dialogue-scripts.md
|   |-- feishu-setup.md
|   |-- final-summary.md
|   |-- migration-existing-setup.md
|   |-- modes.md
|   |-- persona-templates.md
|   |-- preflight.md
|   |-- quick-start.md
|   |-- routing-basic.md
|   `-- troubleshooting.md
`-- scripts/
    |-- generate_agent_ids.py
    |-- render_setup_summary.py
    |-- suggest_persona_kind.py
    |-- write_identity_template.py
    `-- write_starter_profile.py
```

## Key Files

- [SKILL.md](./SKILL.md): main skill behavior and guardrails
- [agents/openai.yaml](./agents/openai.yaml): UI metadata
- [references/quick-start.md](./references/quick-start.md): compact mental model
- [references/feishu-setup.md](./references/feishu-setup.md): Feishu onboarding flow
- [references/persona-templates.md](./references/persona-templates.md): starter profile guidance
- [references/a2a-mode.md](./references/a2a-mode.md): A2A collaboration notes
- [scripts/write_starter_profile.py](./scripts/write_starter_profile.py): starter profile bundle generator

## Installation

Place this skill where Codex can discover local skills.

Typical local skill location:

```text
$CODEX_HOME/skills/openclaw-multi-agent-wizard
```

If `CODEX_HOME` is not set, a common default is:

```text
~/.codex/skills/openclaw-multi-agent-wizard
```

## Validation

Basic script validation:

```bash
python -m compileall scripts
```

If the local skill validator is available:

```bash
python /path/to/quick_validate.py /path/to/openclaw-multi-agent-wizard
```

## Roadmap Ideas

- add onboarding paths beyond Feishu
- improve migration support for existing OpenClaw setups
- add deeper persona refinement for generated agents
- expand worker role categories for A2A collaboration

## Community

- [Contributing](./CONTRIBUTING.md)
- [Code of Conduct](./CODE_OF_CONDUCT.md)
- [Contributors](./CONTRIBUTORS.md)

## License

Released under the [MIT License](./LICENSE).
