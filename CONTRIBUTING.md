# Contributing

Thanks for helping improve `openclaw-multi-agent-wizard`.

## Before You Start

- Read [README.md](./README.md) for the project scope and beginner-focused positioning.
- Read [SKILL.md](./SKILL.md) before changing wizard behavior.
- Prefer small, focused pull requests.

## Contribution Principles

- Keep the beginner experience first.
- Prefer safe defaults over advanced automation.
- Avoid surprising edits to existing OpenClaw setups.
- Use plain language and low-jargon explanations.
- Treat Feishu onboarding as a guided workflow, not assumed knowledge.

## Repository Areas

- `SKILL.md`: main behavior and guardrails
- `references/`: supporting guidance and dialogue design
- `scripts/`: helper scripts for deterministic output
- `.github/`: issue templates, PR template, and workflow automation

## Making Changes

1. Describe the problem clearly.
2. Keep scope tight.
3. Update docs when behavior changes.
4. Add or adjust validation when scripts change.

## Validation

At minimum, run the checks that match your change:

```bash
python -m compileall scripts
```

If you have the local validator available, also run:

```bash
python /path/to/quick_validate.py /path/to/openclaw-multi-agent-wizard
```

## Pull Requests

- Explain what changed and why.
- Call out any beginner-experience tradeoffs.
- Mention whether Feishu setup wording, routing guidance, or generated files changed.
- Include command output or screenshots when they help reviewers.

## Good First Contributions

- clarify README wording
- improve beginner-facing examples
- tighten Feishu setup instructions
- expand templates for generated starter profiles
- improve script validation and error messages
