# todaysummary

English | [简体中文](README.zh-CN.md)

A Codex skill that summarizes the questions, change requests, and feedback you submitted today, with user-message counts grouped by topic.

## Requirements

- Use a Codex environment that exposes chat-history tools such as `list_threads`, `read_thread`, and `list_archived_threads`.
- Installing this skill provides workflow instructions; it does not install those tools or grant access to other chats.
- Without these tools, provide the chat records yourself or limit the summary to accessible records.
- The skill instructions and final recap are in Chinese. The default timezone is Asia/Shanghai; an explicitly supplied timezone takes precedence.

## Install with Codex

Enter this prompt in Codex:

```text
$skill-installer Please install the skill from this GitHub folder:
https://github.com/xsxcfl/my-skills/tree/main/skills/todaysummary
```

## Manual installation

Download the repository ZIP and copy the entire `skills/todaysummary` folder into your personal skills directory:

```text
Windows: %USERPROFILE%\.agents\skills\todaysummary\SKILL.md
macOS / Linux: ~/.agents/skills/todaysummary/SKILL.md
```

For project-scoped use, place it at `.agents/skills/todaysummary/SKILL.md` inside the project. If the skill does not appear after installation, restart Codex.

## Usage

```text
$todaysummary
```

You can also ask Codex to summarize today's questions:

```text
What questions did I ask you today? Please summarize them and provide counts by topic.
```

The recap includes the current date, chat count, user-message count, a topic table, and a concise summary of the questions. Each follow-up message or piece of feedback counts as one message; multiple questions within one message are not counted separately. Inherited history is deduplicated where stable message IDs are available.

## Package contents

```text
my-skills/
├── README.md
├── README.zh-CN.md
└── skills/
    └── todaysummary/
        └── SKILL.md
```

Only reusable instructions are included. No personal chat logs or credentials are packaged.