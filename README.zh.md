> **注意：** 本仓库包含 Anthropic 为 Claude 实现的 skills 集合。有关 Agent Skills 标准的信息，请参阅 [agentskills.io](http://agentskills.io)。

[![skills.sh](https://skills.sh/b/anthropics/skills)](https://skills.sh/anthropics/skills)

# Skills

Skills 是包含指令、脚本和资源的文件夹，Claude 可以动态加载它们以提升在特定任务上的表现。Skills 教会 Claude 如何以可重复的方式完成特定任务，无论是按照贵公司的品牌规范创建文档、使用贵组织的特定工作流分析数据，还是自动化个人事务。

更多信息，请参阅：
- [什么是 skills？](https://support.claude.com/en/articles/12512176-what-are-skills)
- [在 Claude 中使用 skills](https://support.claude.com/en/articles/12512180-using-skills-in-claude)
- [如何创建自定义 skills](https://support.claude.com/en/articles/12512198-creating-custom-skills)
- [使用 Agent Skills 为真实世界中的智能体赋能](https://anthropic.com/engineering/equipping-agents-for-the-real-world-with-agent-skills)

# 关于本仓库

本仓库包含展示 Claude skills 系统可能性的各种 skills。这些 skills 涵盖创意应用（艺术、音乐、设计）、技术任务（测试 Web 应用、生成 MCP 服务器）以及企业工作流（沟通、品牌推广等）。

每个 skill 都是独立的文件夹，其中包含一个 `SKILL.md` 文件，该文件含有 Claude 使用的指令和元数据。浏览这些 skills，可以为自己的 skill 寻找灵感，或了解不同的模式和方法。

本仓库中的许多 skills 都是开源的（Apache 2.0）。我们还收录了支撑 [Claude 文档能力](https://www.anthropic.com/news/create-files) 的文档创建与编辑 skills，分别位于 [`skills/docx`](./skills/docx)、[`skills/pdf`](./skills/pdf)、[`skills/pptx`](./skills/pptx) 和 [`skills/xlsx`](./skills/xlsx) 子文件夹中。这些是源代码可用（source-available）而非开源的，但我们希望将它们作为更复杂 skill 的参考分享给开发者，这些 skill 正在生产级 AI 应用中实际使用。

## 免责声明

**这些 skills 仅用于演示和教育目的。** 虽然 Claude 中可能提供其中部分能力，但你从 Claude 获得的实现和行为可能与这些 skills 中展示的存在差异。这些 skills 旨在说明模式和可能性。在依赖它们完成关键任务之前，请始终在你自己环境中进行充分测试。

# Skill 集合

- [./skills](./skills)：创意与设计、开发与技术、企业与通信以及文档处理相关的 skill 示例
- [./spec](./spec)：Agent Skills 规范
- [./template](./template)：skill 模板

# 在 Claude Code、Claude.ai 和 API 中试用

## Claude Code

你可以在 Claude Code 中运行以下命令，将本仓库注册为 Claude Code 插件市场：

```
/plugin marketplace add anthropics/skills
```

然后，若要安装特定的 skill 集合：
1. 选择 `Browse and install plugins`
2. 选择 `anthropic-agent-skills`
3. 选择 `document-skills` 或 `example-skills`
4. 选择 `Install now`

或者，通过以下命令直接安装任一插件：

```
/plugin install document-skills@anthropic-agent-skills
/plugin install example-skills@anthropic-agent-skills
```

安装插件后，只需提及即可使用该 skill。例如，如果你从市场安装了 `document-skills` 插件，可以向 Claude Code 发出类似这样的请求："使用 PDF skill 从 `path/to/some-file.pdf` 中提取表单字段"。

## Claude.ai

这些示例 skills 在 Claude.ai 的付费套餐中已经全部可用。

若要使用本仓库中的任何 skill 或上传自定义 skill，请按照 [在 Claude 中使用 skills](https://support.claude.com/en/articles/12512180-using-skills-in-claude#h_a4222fa77b) 中的说明进行操作。

## Claude API

你可以通过 Claude API 使用 Anthropic 预构建的 skills，并上传自定义 skill。详见 [Skills API 快速入门](https://docs.claude.com/en/api/skills-guide#creating-a-skill)。

# 创建一个基础 Skill

创建 skill 非常简单 —— 只需一个包含 `SKILL.md` 文件的文件夹，其中含有 YAML frontmatter 和指令。你可以使用本仓库中的 **template-skill** 作为起点：

```markdown
---
name: my-skill-name
description: 清晰描述此 skill 的功能以及何时使用它
---

# My Skill Name

[在此添加 Claude 在此 skill 处于激活状态时将遵循的指令]

## 示例
- 示例用法 1
- 示例用法 2

## 指南
- 指南 1
- 指南 2
```

frontmatter 只需要两个字段：
- `name` - 你的 skill 的唯一标识符（小写，用连字符分隔）
- `description` - 完整描述该 skill 的功能以及何时使用它

下方的 markdown 内容包含 Claude 将遵循的指令、示例和指南。更多详情，请参阅 [如何创建自定义 skills](https://support.claude.com/en/articles/12512198-creating-custom-skills)。

# 合作伙伴 Skills

Skills 是教会 Claude 如何更好地使用特定软件的好方法。当我们看到合作伙伴贡献的优秀示例 skill 时，可能会在此重点展示：

- **Notion** - [Claude 专用 Notion Skills](https://www.notion.so/notiondevs/Notion-Skills-for-Claude-28da4445d27180c7af1df7d8615723d0)
