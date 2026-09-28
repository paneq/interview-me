# interview-me

A Claude Code skill for scoping work before any of it is done. The agent interviews you one decision
at a time, with its recommended answer for each, looks facts up itself instead of asking you, and
keeps a living document of facts, decisions and open questions until you agree you share an
understanding.

## Install

As a plugin:

```bash
claude plugin marketplace add paneq/interview-me
claude plugin install interview-me@paneq
```

Or as a personal skill:

```bash
mkdir -p ~/.claude/skills/interview-me
curl -fsSL https://raw.githubusercontent.com/paneq/interview-me/main/skills/interview-me/SKILL.md \
  -o ~/.claude/skills/interview-me/SKILL.md
```

## Use

Say "interview me about …" or "let's scope this", or run the skill directly: `/interview-me:interview-me`
when installed as a plugin, `/interview-me` as a personal skill.

The "Presenting context" section borrows its visual forms from humanlayer's
[show-me](https://github.com/humanlayer/skills/tree/main/plugins/show-me) skill.

## License

[MIT](LICENSE)
