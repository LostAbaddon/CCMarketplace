# 自建 Claude Code Marketplace

我和朋友自己做的 Claude Code 的 Plugin 的一个 Marketplace。

添加方式：

```
/plugin marketplace add lostabaddon/CCMarketplace
```

## Plugins

- [InfoCollector](https://github.com/lostabaddon/InfoCollector.git)
  + 作者: LostAbaddon
  + 版本: 1.3.0
  + 简介: 自动信息收集工具，包含一个 Skill 和三个 Agent，可以并发地对多个信息源进行信息收集。

- [Reminder](https://github.com/lostabaddon/ReminderSkill.git)
  + 作者: LostAbaddon
  + 版本: 1.1.1
  + 简介: 让 Claude Code 具备记住事项并定时发出提醒的能力，支持 Windows/MacOS/Linux。
          本插件会注册一个 SessionStart 的 hook，其作用是自动判断 mcp 下的 Node.js 项目是否已经初始化，如果没有初始化则自动执行 `npm install`。如果没有成功触发，则用户需要自行到插件目录下的 mcp 目录中执行 `npm install`。
          本 Plugin 可以配合 [CCExtension](https://github.com/lostabaddon/CCExtension) 这个 Chrome Extension 一起使用，后者可以使用 Chrome 的 Notification 来做统一的提醒通知，并能进行更加全面的提醒管理。

- [WorkReport](https://github.com/lostabaddon/DailyReportSkill.git)
  + 作者: LostAbaddon
  + 版本: 1.1.1
  + 简介: 一个能自动记录用户在 Claude Code 中操作，并生成每日简报的 Plugin。如果使用配套的服务器与 Chrome 插件，那能记录的东西可以更多，提供的服务也会更多。

- [CCP2GCE](https://github.com/lostabaddon/CCP2GCE.git)
  + 作者: LostAbaddon
  + 版本: 1.0.0
  + 简介: 一个能将 Claude Code Plugin “翻译”为 Gemini CLI Extension 的 Plugin。包含一个 SubAgent 和一个 Command。

- [ComplexMissionManager](https://github.com/lostabaddon/complexMissionManager.git)
  + 作者: LostAbaddon
  + 版本: 1.0.1
  + 简介: 智能多级任务拆分和并行执行系统 - 自动将复杂任务拆分为可并行执行的任务组，并通过多级 Agent 协作完成。第一层：根据耦合情况拆分并行任务组；第二层：根据业务量以及拆分顺序任务序列；第三层：原子化任务执行层。

- [HeadlessKnight](https://github.com/lostabaddon/HeadlessKnight.git)
  + 作者: LostAbaddon
  + 版本: 1.0.0
  + 简介: 让 Claude Code 具备调用 Claude Code、Gemini CLI、Codex CLI 等 AI CLI 工具能力的 Claude Code 插件。其中还自带了 Context7 这个 MCP 以及一个方便生成 commit 信息的 command。

## 配套服务组件

- [CCCore](https://github.com/lostabaddon/CCCore.git)
  + 作者: LostAbaddon
  + 版本: undefined
  + 简介: 一个 Node.JS 服务器，为 Claude Code 以及 Chrome 插件等提供基础服务，包括：日志读写、提醒转发，等等。

- [CCExtension](https://github.com/lostabaddon/CCExtension.git)
  + 作者: LostAbaddon
  + 版本: undefined
  + 简介: 一个与 Claude Code 插件相互配合的 Chrome 插件，功能包括：活动日志记录与展示、事件提醒、Markdown 直接解析，等等。