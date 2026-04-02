# claude-skills

Custom skills for [Claude Code](https://claude.ai/code). Pick the ones you want.

## Install a skill

Copy the skill folder into your Claude skills directory:

```bash
# clone the repo
git clone https://github.com/h0rhay/claude-skills.git

# copy the skill you want
cp -r claude-skills/skills/tokenwise ~/.claude/skills/
```

That's it. The skill is now available as `/tokenwise` in Claude Code.

### Update a skill

```bash
cd claude-skills && git pull
cp -r skills/tokenwise ~/.claude/skills/
```

### Remove a skill

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
