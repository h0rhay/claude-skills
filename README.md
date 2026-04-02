# claude-skills

Custom skills for [Claude Code](https://claude.ai/code). Pick the ones you want.

## Install

### Option 1: Terminal (devs)

```bash
git clone https://github.com/h0rhay/claude-skills.git
cp -r claude-skills/skills/tokenwise ~/.claude/skills/
```

### Option 2: No terminal (non-devs)

1. Click the green **Code** button above → **Download ZIP**
2. Unzip it
3. Copy the `skills/tokenwise` folder (including the `references` subfolder) into `~/.claude/skills/`

Your folder should look like this:

```
~/.claude/skills/tokenwise/
├── SKILL.md
└── references/
    └── checkpoint-format.md
```

That's it. `/tokenwise` is now available in Claude Code.

### Update

```bash
cd claude-skills && git pull
cp -r skills/tokenwise ~/.claude/skills/
```

### Remove

```bash
rm -rf ~/.claude/skills/tokenwise
```

## Skills

### tokenwise

Token-efficient session manager. Keeps Claude concise, compresses context on demand, and saves session state to disk.

**Use when:** long Q&A sessions, research conversations, or any time you're burning through rate limits.

**How it works:**
1. Auto-activates and enforces short, direct responses
2. Say `checkpoint` or `compress` mid-session to save a context snapshot to `context-brief.md`
3. Paste the snapshot into a new chat to pick up where you left off

**Triggers:** `/tokenwise`, `lean mode`, `save tokens`, `checkpoint`, `compress`

## License

MIT
