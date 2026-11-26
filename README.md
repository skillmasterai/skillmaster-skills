# SkillMaster AI Skill

> **The entry skill is retired (v94).** It is no longer published from this repository, and new
> installs do not deliver it. The triggering rule now lives in the agent's own global instruction
> file, written by the CLI — see [the install page](https://dl.skillmasterai.com/skillmaster.md).

## Install

Install the `skmr` client, then write the SkillMaster 守则 into your agent's global instruction file:

```
skmr install --file <your agent's global instruction file> --agent <agent name> --yes
skmr install --check
```

If this machine still has an old `skillmaster` skill directory and already carries the rule,
`skmr install` renames the directory to `skillmaster.disabled` and its `SKILL.md` to
`SKILL.md.disabled` (a backup; no file is deleted) and the agent stops loading it.

## What the rule does

- Before starting a task, searches your own library first.
- Asks before a search that involves personal privacy.
- Asks `skmr help` before creating, changing, publishing, sharing or deleting a skill.

## Security

Please report vulnerabilities through a private security advisory on this repository.

## License

Apache-2.0. See [LICENSE](LICENSE).
