# SkillMaster AI Skill

The agent skill that makes SkillMaster AI the first place an agent looks: before starting a task, search the library for an existing way to do it.

## Install

### Claude Code

```
/plugin marketplace add skillmasterai/skillmaster-skills
/plugin install skillmaster@skillmaster
```

### Other agents

```
npx skills add skillmasterai/skillmaster-skills
```

The skill is a single `SKILL.md`. It needs the `skmr` command-line client to search, load and publish skills. Install `skmr` from the official download page before using it:

https://dl.skillmasterai.com/skillmaster.md

## What the skill does

- Searches your own library first; the public library only when you ask for it.
- Loads a skill before changing it.
- Plans multi-step work as `intent → subtask → skill` before acting.

## Security

Please report vulnerabilities through a private security advisory on this repository.

## License

Apache-2.0. See [LICENSE](LICENSE).
