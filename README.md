# Code Ownership Coach

An open Agent Skill that helps developers understand code written with coding agents.

It keeps routine work out of the way, briefly explains important or risky implementation decisions as they happen, and runs a short understanding check before the final handoff.

## What it does

- Explains new, non-obvious, risky, or difficult parts of a change.
- Skips boilerplate, formatting, imports, and other routine work.
- Keeps explanations short and tied to the files being changed.
- Asks two to four questions based on the final diff.
- Explains unclear concepts and retries them with a different question.
- Accepts answers in the developer's own words without scores or shaming.

## What it does not do

- Block Git pushes or merges.
- Add a CI ownership gate.
- Store answers, attempts, or scores.
- Require an MCP server or external service.

## Install

### With the GitHub CLI skill installer

Install for all Codex projects:

```bash
gh skill install salmazz/code-ownership-coach code-ownership-coach \
  --agent codex --scope user
```

Install for all Claude Code projects:

```bash
gh skill install salmazz/code-ownership-coach code-ownership-coach \
  --agent claude-code --scope user
```

The installer also supports other compatible coding agents. Run `gh skill install --help` to list the available agent targets and scopes.

Start a new agent session after installation.

### Manual installation

Clone the repository:

```bash
git clone https://github.com/salmazz/code-ownership-coach.git
```

For Codex, copy the skill to either `.agents/skills/` in a project or `~/.agents/skills/` for all projects:

```bash
cp -R code-ownership-coach/skills/code-ownership-coach ~/.agents/skills/
```

For Claude Code, copy it to either `.claude/skills/` in a project or `~/.claude/skills/` for all projects:

```bash
cp -R code-ownership-coach/skills/code-ownership-coach ~/.claude/skills/
```

## Use

Invoke it explicitly while testing:

```text
Use the $code-ownership-coach skill while implementing this task: ...
```

Compatible agents may also select it automatically for implementation, refactoring, debugging, migration, and other code-changing tasks.

## License

MIT
