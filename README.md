# Construct3-New-Project

**English** | [中文](README_CN.md)

An empty [Construct 3](https://editor.construct.net/) ([affiliate link](https://www.construct.net/a/260259?t=construct3)) folder project for starting a game outside the editor.

The folder contains `project.c3proj`, an empty layout and event sheet, a timeline, a flowchart and the default icons. `savedWithRelease` in `project.c3proj` records the editor release that saved it.

## Open in Construct 3

Download or clone this repository, then open the folder in Construct 3 with **Menu > Project > Open > Open project folder**. Save a copy for each game.

## Create a project with an agent

Install Git and Python 3.10 or later. From the folder where you keep repositories, clone [Construct3-Agent-Skills](https://github.com/XHXIAIEIN/Construct3-Agent-Skills), which holds the skill, prompts and project tools:

```bash
git clone https://github.com/XHXIAIEIN/Construct3-Agent-Skills
```

Create a game and install its skill:

```bash
python Construct3-Agent-Skills/scripts/bootstrap.py --project MyGame
```

`MyGame` is created beside the skills repository from its bundled empty project. The command also clones the manual, official examples and Addon SDK beside it when missing. It installs the skill in the game's `.agents/skills/` and writes `AGENTS.md` and the `CLAUDE.md` import.

To use this repository's folder as the template, clone it beside the skills repository and pass `--template`:

```bash
git clone https://github.com/XHXIAIEIN/Construct3-New-Project
python Construct3-Agent-Skills/scripts/bootstrap.py --project MyOtherGame --template Construct3-New-Project
```

For an existing folder project, install the skill with:

```bash
python Construct3-Agent-Skills/plugin/skills/construct3-agent-plugin/scripts/install.py --project MyGame
```

Add `--into .claude/skills` for Claude Code or `--into .trae/skills` for TRAE. Claude Code can also use the [Construct 3 plugin](https://github.com/XHXIAIEIN/Construct3-Agent-Skills#the-claude-code-plugin).

Tell the agent to read the game's `AGENTS.md` and installed `SKILL.md` before editing. Check the files, then open and preview the game in the editor:

```bash
python MyGame/.agents/skills/construct3-agent-plugin/scripts/check_project.py --project MyGame
python MyGame/.agents/skills/construct3-agent-plugin/scripts/open_in_editor.py --project MyGame --preview
```

These commands use the default skill location. For another location, use the path printed by `install.py`.

## Related repositories

- [Construct3-Agent-Skills](https://github.com/XHXIAIEIN/Construct3-Agent-Skills) holds the skill, prompts, project tools and Claude Code plugin.
- [Construct3-RAG](https://github.com/XHXIAIEIN/Construct3-RAG) maintains the schemas, editor texts and other data bundled with the skill, including an empty project under `data/c3-new-project/`.

`llm-context.md` is the editor's guide to the project folder format. Follow the installed skill for event sheet editing and verification.
