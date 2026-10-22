# Learn Claude Code · Agent Harness 工程

17 个递进式课程，从 Agent 循环、工具与权限，到上下文、记忆、团队协作、工作流和目标收口。每章用小型代码示例讲清一个机制，帮助理解模型如何通过工具和运行环境完成任务。

这是教学仓库，示例有意保持简洁，不能直接视为生产环境的安全实现。运行模型请求可能产生 API 费用；密钥只放本机 `.env`，不要提交。

## 快速开始

### 新版 17 章主线

```sh
git clone https://github.com/w93139/harness-learn.git
cd harness-learn

# Mac 用户：双击「启动.command」即可（自动装依赖 + 首次引导填 DeepSeek key）
# 或命令行方式：
python3 run.py                # 自动装依赖 + 首次引导填 key + 菜单选择章节 s01–s17

# 高级用法：
python run.py 3               # 直接运行指定章节（3 / s03 / agent_loop 均可）
python run.py s16 demo        # s16 附带的 demo / resume 模式
python s01_agent_loop/code.py # 各章代码仍可独立运行
```

> **零基础学生分发**：让学生下载本仓库（GitHub 页面点「Code → Download ZIP」，或 `git clone`），下载内容不含 `.env` 和 `.venv`。解压后打开「使用说明.txt」，从第 0 步开始。

### 旧版 12 章过渡线

```sh
python agents/s01_agent_loop.py
python agents/s12_worktree_task_isolation.py
python agents/s_full.py
```

### Web 平台

Web 平台从根目录课程生成内容。s16、s17 提供阅读、源码、模拟和架构视图；仅专用首屏可视化保持精简。

```sh
cd web && npm install && npm run dev   # http://localhost:3000
```

## 阅读顺序

新读者按根目录 `s01_*` 到 `s17_*` 阅读。每章包含英文 README、中文／日文译本和 `code.py`。s15 集成前面的机制，s16 讲固定工作流，s17 讲目标判断与续跑。

旧版 `agents/` 与 `docs/` 的 12 章仅保留作过渡，章节号不能与新版混用。理念说明、核心循环、旧新章节对照见 [课程导言](docs/course-introduction.md)。

## 全部章节

| 章节 | 主题 | 关键概念 |
|---|---|---|
| [s01](./s01_agent_loop/) | Agent Loop | `messages` / `while True` / `tool_use` |
| [s02](./s02_tool_use/) | Tool Use | `TOOL_HANDLERS` / dispatch map / 并发 |
| [s03](./s03_permission/) | Permission | `PermissionRule` / 审批管线 |
| [s04](./s04_hooks/) | Hooks | `PreToolUse` / `PostToolUse` / 扩展点 |
| [s05](./s05_todo_write/) | TodoWrite | `TodoItem` / 先计划后执行 |
| [s06](./s06_subagent/) | Subagent | `fresh messages[]` / 上下文隔离 |
| [s07](./s07_skill_loading/) | Skill Loading | `SkillLoader` / 技能目录 / 按需注入 |
| [s08](./s08_context_compact/) | Context Compact | budget / snip / micro / summary 四步压缩 |
| [s09](./s09_memory/) | Memory | selection / extraction / consolidation |
| [s10](./s10_task_system/) | Task System | `TaskRecord` / `blockedBy` / 磁盘持久化 |
| [s11](./s11_background_tasks/) | Background Tasks | 线程执行 / 通知队列 |
| [s12](./s12_cron_scheduler/) | Cron Scheduler | 持久化调度 / 会话级触发 |
| [s13](./s13_agent_teams/) | Agent Teams | 持久队友 / 原子认领 / 任务绑定的 Worktree / 类型协议 |
| [s14](./s14_mcp_plugin/) | MCP Plugin | 工具发现 / 命名空间 / 工具池组装 |
| [s15](./s15_integrated_harness/) | Agent Harness 集成 | 工具、运行时上下文、任务、团队、调度和 MCP 归到一个循环 |
| [s16](./s16_workflow_runtime/) | Workflow Runtime | 脚本编排 / 生命周期事件 / journal 续跑 |
| [s17](./s17_goal_loop/) | Goal Loop | 目标闸门 / 对话判断 / 自动续轮 |

## 目录与贡献

- `s01_*/`–`s17_*/`：现行课程、代码和图示。
- `skills/`：技能加载示例；`web/`：课程阅读平台。
- `agents/`、`docs/`：旧版教程与补充说明；`tests/`：测试。

贡献要求见 [CONTRIBUTING.md](CONTRIBUTING.md)。章节代码或说明变动需要同步对应三语文档；此仓库的组件在 [agent-blueprint](https://github.com/w93139/agent-blueprint) 中另作产品架构模板使用。

## 许可

[MIT License](LICENSE)。
