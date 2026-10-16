# todaysummary

A Codex skill that summarizes the questions, change requests, and feedback you submitted today, with message counts grouped by topic.

一个用于汇总当天 Codex 提问、修改要求和补充反馈的技能，按主题统计消息数量并输出中文回顾。

## Requirements / 运行条件

- Use a Codex environment that exposes chat-history tools such as `list_threads`, `read_thread`, and `list_archived_threads`.
- Installing a skill provides workflow instructions; it does not install these tools or grant access to other chats.
- Without those tools, provide the chat records yourself or limit the summary to accessible records.
- The skill instructions and final recap are in Chinese. The default timezone is Asia/Shanghai; an explicitly supplied timezone takes precedence.

需要能读取聊天记录的 Codex 环境。技能本身不会新增聊天工具或访问权限；工具不可用时，需要用户提供记录，或仅汇总可读取的范围。当前技能说明和汇总答复为中文，默认使用北京时间。

## Install with Codex / 通过 Codex 安装

Open this repository on GitHub, then copy the URL of `skills/todaysummary` into this prompt:

```text
$skill-installer Please install the skill from this GitHub folder: https://github.com/xsxcfl/my-skills/tree/main/skills/todaysummary
```

在 GitHub 打开本仓库的 `skills/todaysummary` 文件夹，复制该文件夹地址，在 Codex 中输入：

```text
$skill-installer 请安装这个 GitHub 技能：https://github.com/xsxcfl/my-skills/tree/main/skills/todaysummary
```

## Manual installation / 手动安装

Download the repository ZIP and copy the entire `skills/todaysummary` folder into your personal skills directory:

```text
Windows: %USERPROFILE%\.agents\skills\todaysummary\SKILL.md
macOS / Linux: ~/.agents/skills/todaysummary/SKILL.md
```

For project-scoped use, place it at `.agents/skills/todaysummary/SKILL.md` inside the project.

下载仓库 ZIP，将完整的 `todaysummary` 文件夹复制到个人技能目录；团队项目也可以将其放在项目内的 `.agents/skills/todaysummary/`。如果安装后没有显示技能，请重启 Codex。

## Usage / 使用

```text
$todaysummary
```

Or ask / 或直接提问：

```text
今天我问了你什么问题，你汇总统计一下，谢谢
```

The recap includes the current date, chat count, user-message count, a topic table, and a concise summary of the questions. Follow-up messages and feedback each count as one message; multiple questions within one message are not split. Inherited history is deduplicated where stable message IDs are available.

汇总包含当天日期、聊天数量、用户消息数量、主题统计表和具体提问回顾。每条追问或反馈算一条消息，同一消息中的多个问题不拆开；能获取稳定消息 ID 时，对继承历史去重。

## Package contents / 文件结构

```text
todaysummary/
├── README.md
└── skills/
    └── todaysummary/
        └── SKILL.md
```

Only the reusable instructions are included. No personal chat logs or credentials are packaged.

仅包含可复用的技能说明，不包含个人聊天记录或凭据。