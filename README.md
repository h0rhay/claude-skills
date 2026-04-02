# claude-skills

[![MIT License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)

Personal Claude Code skills plugin — token-efficient workflows and development best practices.

## Install

**Plugin install (recommended):**
```bash
claude plugin install h0rhay/claude-skills
```

**With `--plugin-dir` flag:**
```bash
claude --plugin-dir /path/to/claude-skills
```

**Manual copy:**
Copy any skill folder from `skills/` into `~/.claude/skills/`.

## Skills

### `/h0rhay:tokenwise`

Token-efficient session manager for long discovery conversations. Enforces concise responses, prevents context bloat, and saves compressed session state on demand.

**Triggers:** `lean mode`, `save tokens`, `checkpoint`, `compress`, `/h0rhay:tokenwise`

**What it does:**
- Enforces short, front-loaded answers from the first message
- Generates compressed context checkpoints on demand (`"checkpoint"` or `"compress"`)
- Saves checkpoints to `context-brief.md` in your working directory
- Resumes from a pasted context block in a fresh session

## Adding to a project

Create a `.claude/settings.json` in your project root and reference the plugin:

```json
{
  "plugins": ["h0rhay/claude-skills"]
}
```

Or install globally so all projects can use the skills:

```bash
claude plugin install h0rhay/claude-skills --global
```

## License

MIT — see [LICENSE](LICENSE).
