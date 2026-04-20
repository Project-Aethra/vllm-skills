# vllm-skills — CLAUDE.md

Claude Code skills for deploying and invoking vLLM on MagnonOS.
Part of MagnonOS Project-Aethra.

## Purpose

Modular, reusable agent skills for operating and invoking vLLM, following the Anthropics
skills template format. Each skill is a self-contained directory for a specific vLLM
operational task.

## Tech stack

- YAML / Markdown skill definitions (Claude Code skill format)
- Scripts for vLLM deployment and invocation

## Skills

See `skills/` directory for the full list of vLLM skills.

## Dev commands

```bash
# Copy skills to Claude Code skills directory
cp -r skills ~/.claude/skills/

# Validate skill structure
ls skills/*/SKILL.md
```

## Key conventions

- Skills follow the Anthropics `SKILL.md` specification.
- Each skill is fully self-contained in its own directory.
- vLLM endpoint configuration via environment variables — never hardcoded.
- Local model endpoint is the Nemotron vLLM instance on `hetzner-small`.

## What NOT to do

- Never commit vLLM API keys or inference server credentials.
- Never hardcode model names or server endpoints in skill implementations.
- Never use `ubuntu-latest` CI runners — always `magnon-enterprise-runners`.

## CI

All GitHub Actions workflow jobs use `runs-on: magnon-enterprise-runners`.
