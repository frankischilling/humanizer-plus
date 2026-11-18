# Install Humanizer Plus

The skill is named `humanizer`. If you already use upstream Humanizer, use a separate project or switch the installed copy so your agent can resolve the name.

## Skills CLI

```sh
npx skills add frankischilling/humanizer-plus
```

Add `--global` to install for your user account or `--agent codex` to select an agent. The CLI can also install for Claude Code, Cursor, and other supported agents. Use `--agent '*'` to select every supported agent.

## Claude Code plugin

```text
/plugin marketplace add frankischilling/humanizer-plus
/plugin install humanizer@humanizer
```

If your Claude Code version cannot load a skill from the plugin root, use the Skills CLI with `--agent claude-code`.

## Claude.ai and Claude Desktop

Download the repository as a ZIP from GitHub and upload it as a skill in Settings.

## pi

```sh
pi install git:github.com/frankischilling/humanizer-plus
```

Add `-l` to install it in the current project.

## Manual installation

Put the root [SKILL.md](../SKILL.md) in your agent's `humanizer` skill directory. Copy `docs/` beside it if you want the linked examples and source audit available locally.

## Use

Call `/humanizer` or ask your agent to use the skill. Paste the text, provide a file path, or ask for it as part of another writing task. A few paragraphs of your writing can help the skill match your phrasing and rhythm.

When editing a file, the skill reads the current file and reports its coverage. Ask for markup repairs, link changes, or source verification when those are part of the edit.
