# SkillMaster AI Skill

> **The entry skill is retired (v94).** It is no longer published from this repository, and new
> installs do not deliver it. The triggering rule now lives in the agent's own global instruction
> file, written by the CLI — see [the install page](https://dl.skillmasterai.com/skillmaster.md).

## Install

Install the `skmr` client, then have your agent write the SkillMaster 守则 into its own global
instruction file, after you say where:

```
skmr self rule print                  # the rule text, verbatim
skmr self rule check <that path>      # 当前 / 旧版 / 被改过 / 读不到 / 没有 / 不管
```

The agent asks first and writes into **its own** file (Claude Code `~/.claude/CLAUDE.md`, Codex
`~/.codex/AGENTS.md`, WorkBuddy `MEMORY.md`, Cursor `~/.cursor/rules/*.mdc` with frontmatter). The
CLI itself never writes it and keeps no record. If this machine still has an old `skillmaster`
skill directory, remove it yourself; nothing deletes files for you.

## What the rule does

- Before starting a task, searches your own library first.
- Asks before a search that involves personal privacy.
- Asks `skmr help` before creating, changing, publishing, sharing or deleting a skill.

## Security

Please report vulnerabilities through a private security advisory on this repository.

## License

Apache-2.0. See [LICENSE](LICENSE).
