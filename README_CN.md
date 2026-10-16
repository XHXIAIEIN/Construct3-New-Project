# Construct3-New-Project

[English](README.md) | **中文**

这是一个空白的 [Construct 3](https://editor.construct.net/)（[推广链接](https://www.construct.net/a/260259?t=construct3)）文件夹项目，用于在编辑器外创建游戏项目。

文件夹包含 `project.c3proj`、空白布局和事件表、时间轴、流程图及默认图标。`project.c3proj` 中的 `savedWithRelease` 记录了保存它的编辑器版本。

## 在 Construct 3 中打开

下载或克隆本仓库，然后在 Construct 3 中选择 **菜单 > 项目 > 打开 > 打开项目文件夹**。为每个游戏另存一份项目。

## 让智能体创建项目

安装 Git 和 Python 3.10 或更高版本。在存放仓库的文件夹中，克隆 [Construct3-Agent-Skills](https://github.com/XHXIAIEIN/Construct3-Agent-Skills)。它提供技能、提示词和项目工具：

```bash
git clone https://github.com/XHXIAIEIN/Construct3-Agent-Skills
```

创建游戏项目并安装技能：

```bash
python Construct3-Agent-Skills/scripts/bootstrap.py --project MyGame
```

命令会在技能仓库旁创建 `MyGame`，使用技能自带的空白项目作为模板。缺少手册、官方示例或 Addon SDK 仓库时，也会将它们克隆到旁边。技能安装在游戏的 `.agents/skills/` 中，同时写入 `AGENTS.md` 和导入它的 `CLAUDE.md`。

要使用本仓库的文件夹作为模板，将它克隆到技能仓库旁，并传入 `--template`：

```bash
git clone https://github.com/XHXIAIEIN/Construct3-New-Project
python Construct3-Agent-Skills/scripts/bootstrap.py --project MyOtherGame --template Construct3-New-Project
```

为已有的文件夹项目安装技能：

```bash
python Construct3-Agent-Skills/plugin/skills/construct3-agent-plugin/scripts/install.py --project MyGame
```

Claude Code 加上 `--into .claude/skills`，TRAE 加上 `--into .trae/skills`。Claude Code 也可以使用 [Construct 3 plugin](https://github.com/XHXIAIEIN/Construct3-Agent-Skills/blob/main/README_CN.md#claude-code-plugin)。

让智能体在修改前阅读游戏的 `AGENTS.md` 和安装后的 `SKILL.md`。先检查文件，再在编辑器中打开并预览游戏：

```bash
python MyGame/.agents/skills/construct3-agent-plugin/scripts/check_project.py --project MyGame
python MyGame/.agents/skills/construct3-agent-plugin/scripts/open_in_editor.py --project MyGame --preview
```

这些命令使用默认技能安装位置。安装在其他位置时，使用 `install.py` 输出的路径。

## 相关仓库

- [Construct3-Agent-Skills](https://github.com/XHXIAIEIN/Construct3-Agent-Skills) 提供技能、提示词、项目工具和 Claude Code plugin。
- [Construct3-RAG](https://github.com/XHXIAIEIN/Construct3-RAG) 维护技能打包使用的定义、编辑器文本等数据，其中包括 `data/c3-new-project/` 下的空白项目。

`llm-context.md` 是编辑器提供的项目文件夹格式说明。事件表的编辑和验证遵循安装后的技能。
