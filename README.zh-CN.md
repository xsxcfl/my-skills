# todaysummary

[English](README.md) | 简体中文

一个用于汇总当天 Codex 提问、修改要求和补充反馈的技能，按主题统计用户消息数量并输出中文回顾。

## 运行条件

- 使用能读取聊天记录的 Codex 环境，需要提供 `list_threads`、`read_thread`、`list_archived_threads` 等工具。
- 安装技能只会提供操作说明，不会自动新增这些工具或授予其他聊天的访问权限。
- 工具不可用时，需要用户自行提供聊天记录，或仅汇总当前可读取的范围。
- 当前技能说明和最终汇总答复为中文，默认时区为 Asia/Shanghai（北京时间）；用户明确指定其他时区时，以指定时区为准。

## 通过 Codex 安装

在 Codex 中输入：

```text
$skill-installer 请安装这个 GitHub 技能：
https://github.com/xsxcfl/my-skills/tree/main/skills/todaysummary
```

## 手动安装

下载仓库 ZIP，将完整的 `skills/todaysummary` 文件夹复制到个人技能目录：

```text
Windows: %USERPROFILE%\.agents\skills\todaysummary\SKILL.md
macOS / Linux: ~/.agents/skills/todaysummary/SKILL.md
```

如果只在某个项目中使用，可以将其放在项目内的 `.agents/skills/todaysummary/SKILL.md`。如果安装后没有显示技能，请重启 Codex。

## 使用

```text
$todaysummary
```

也可以直接提问：

```text
今天我问了你什么问题，你汇总统计一下，谢谢
```

汇总包含当天日期、聊天数量、用户消息数量、主题统计表和具体提问回顾。每条追问或反馈算一条消息，同一消息中的多个问题不拆开计算；能获取稳定消息 ID 时，对继承历史去重。

## 文件结构

```text
my-skills/
├── README.md
├── README.zh-CN.md
└── skills/
    └── todaysummary/
        └── SKILL.md
```

仅包含可复用的技能说明，不包含个人聊天记录或凭据。