# skill-distribution

An agent skill that knows how to publish and distribute other agent skills.

You wrote a `SKILL.md`. Now where does it go? There is no single place to upload a skill: some registries index GitHub, some take a CLI push, some are plugin directories with review, and some are paid marketplaces. This skill gives your agent the current rules for each and walks it through publishing.

## What it covers

| Channel | How a skill gets listed |
|---|---|
| GitHub | Push a public repo |
| skills.sh | Nothing to submit; listed once people install with `npx skills add` |
| agentskill.sh | Submit the repo or a SKILL.md link |
| ClawHub | `clawhub skill publish` |
| Hermes skills hub | Publish or tap a GitHub repo |
| Claude Code | Your own plugin marketplace, or Anthropic's directory |
| ChatGPT and Codex | Universal plugin directory |
| Gemini CLI | Extension in a public repo |
| Agensi, SkillHQ, MCP Market | Paid listings |

It also ships `scripts/check_skill.py`, which checks a skill folder against the rules registries share before you publish.

## Install

Any agent the skills CLI supports:

```bash
npx skills add Oxde/skills-distribution
```

Claude Code, as a plugin:

```bash
claude plugin marketplace add Oxde/skills-distribution
claude plugin install skill-distribution@oxde
```

By hand: copy `skills/skill-distribution/` into your agent's skills folder (`~/.claude/skills/`, `~/.agents/skills/`, and so on).

## Use

Ask your agent something like:

- "I wrote a skill, how do I publish it?"
- "Get this skill listed on skills.sh and ClawHub."
- "Turn my skill into a Claude Code plugin."

Or run the checker directly:

```bash
python skills/skill-distribution/scripts/check_skill.py path/to/your-skill
```

## How current is it

Registry rules change often. Everything was checked on the date in the skill's `metadata.verified` field, and `references/sources.md` lists what was read from primary docs and what could not be verified. The skill tells the agent to re-check a channel's docs before running a publish command.

## License

MIT-0
