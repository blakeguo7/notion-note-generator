# Notion Note Generator

[English](README.md) | 简体中文

一个 [Agent Skill](https://agentskills.io/home)，可将网站、课件、PDF 和文档整理成有来源依据的 Notion 学习笔记。

它围绕连贯的理解过程组织内容：从学习者已有的知识出发，说明概念如何衔接，通过有意义的例子解释机制，并让重要结论能够追溯到原始材料。

## 能做什么

- 先阅读实际材料，再规划笔记，并说明未读或无法访问的部分。
- 根据学习者的基础，讲清机制、前置知识和概念之间的关系。
- 保留标准英文技术术语，在有助于理解时提供双语解释。
- 将较大的主题组织成完整的教学页面，并提供简洁的导航。
- 按用户要求创建或更新 Notion 页面，保留无关内容和已有子页面链接。
- 写入后重新读取页面及其父页面，核对内容和位置。

也可以只生成草稿或提纲，不修改 Notion。

## 使用条件

- 支持 [Agent Skills 格式](https://agentskills.io/specification)的工具。
- 能够读取所提供材料的工具。课件和 PDF 可能需要同时检查提取出的文字和页面图像。
- 如需写入 Notion，必须有已连接且有权访问目标页面的工具，支持读取、创建、更新和核验页面。

`SKILL.md` 和 `references/` 中的核心说明不依赖特定产品。安装位置、调用方式和 Notion 连接方式取决于所使用的工具。`agents/openai.yaml` 提供可选的 Codex 专用元数据（Metadata），其他工具无需读取它也能使用核心说明；其中的依赖声明本身不会完成 Notion 连接或授权。

## 安装

1. 下载或克隆（Clone）本仓库（Repository），将文件夹命名为 `notion-note-generator`。
2. 使用所选工具提供的 skill 导入功能，或将文件夹放入其文档指定的位置。保留 `SKILL.md` 和 `references/` 的相对位置，也可以保留可选的 `agents/` 文件夹。
3. 如需创建或更新页面，连接该工具的 Notion 功能。

```sh
git clone https://github.com/blakeguo7/notion-note-generator.git
```

如果已经安装过这个 skill，替换前先比较两个版本。

<details>
<summary>Codex 安装示例</summary>

个人使用时，将文件夹放在：

```text
~/.agents/skills/notion-note-generator/
```

仅在某个项目内使用时，将文件夹放在：

```text
<project>/.agents/skills/notion-note-generator/
```

其中 `<project>` 替换为实际项目路径。Codex 会自动发现 skill 的变化；如果没有出现，可以重启 Codex。

也可以让内置的 `$skill-installer` 从本仓库的 GitHub 链接安装。请说明 `SKILL.md` 位于仓库根目录（Root Directory），skill 名称为 `notion-note-generator`。

```text
$skill-installer
请从 https://github.com/blakeguo7/notion-note-generator 安装这个 skill。
SKILL.md 位于仓库根目录，请使用 notion-note-generator 作为 skill 名称。
```

安装位置和支持的元数据可参考官方 [Codex skills 文档](https://developers.openai.com/codex/skills)。

</details>

## 使用示例

通过所选工具支持的方式选择或启用 `notion-note-generator`，提供资料、学习目标、当前基础和期望语言；需要写入 Notion 时，再提供目标页面。下面的示例使用自然语言，各工具也可能提供 skill 选择菜单或专门的调用语法。

**创建学习笔记**

```text
请使用 notion-note-generator skill。
请根据附件中的课件，教我理解 GPU memory hierarchy 如何影响程序执行。
我会基础 Python，但刚开始学习 GPU 编程。
请用中文写笔记，保留标准英文技术术语，并在这个 Notion 页面下创建笔记：
<Notion 父页面链接>。
```

**完善已有笔记**

```text
请使用 notion-note-generator skill。
请根据这些官方文档链接，完善 <Notion 页面链接> 中的解释和例子。
保留无关内容和已有子页面，并指出现有笔记与资料之间的差异。
```

**先生成草稿**

```text
请使用 notion-note-generator skill。
根据这份 PDF，为初学者整理一份中文学习笔记草稿，保留标准英文术语，
讲清概念之间的关系并标注来源页码。先返回草稿，不要修改 Notion。
```

## 文件说明

| 文件 | 用途 |
| --- | --- |
| [SKILL.md](SKILL.md) | skill 的适用范围、写作标准和工作流程 |
| [references/note-design.md](references/note-design.md) | 教学结构、例子、术语和质量检查 |
| [references/notion-writing.md](references/notion-writing.md) | 目标页面检查、局部更新和写入后核验 |
| [agents/openai.yaml](agents/openai.yaml) | 可选的 Codex 专用展示元数据、默认提示词（Prompt）和 Notion 工具依赖 |

## 适用范围

适合学习、综合整理和保存知识材料。不用于会议纪要、任务跟踪或一般 Notion 管理。

实际效果取决于可用的资料读取工具和 Notion 连接。无法访问某个来源或目标页面时，skill 会说明限制，并在有帮助时保留草稿。

## 许可证（License）

采用 [MIT License](LICENSE)。
