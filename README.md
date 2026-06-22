# npc — 确定性执行层 CLI

把 spec-driven 开发流程里**确定性的机械动作**（状态读写、事件计时、prompt 渲染、子进程编排、质量门、git 卫生、跨 run 指标）从 LLM 手里拿走、做成可测试的软件，让 LLM 只做决策。

零运行时依赖（纯标准库），`uv tool install` 即用。被 **agent-spine**（人驾驭 harness skill）与 **aidevos**（自治系统）作为子模块复用——同一套确定性工具，赋能不同上层的 LLM 执行，减少 LLM 处理确定性任务。

## 安装

```bash
uv tool install --from . npc      # 从本仓库（子模块）装
npc --version
npc --help
```

## 命令族

init / resume / state / phase / review / focus / fixer / archive / implement(record·run) / fix(record·run) / agent / auto-decide / summary / index / telemetry / **doctor** / **verify**(tests·routing) / **spec analyze** / **plan**(check·new-change) / **git**(branch-for·ensure-clean·commit) / **deliver** · **pr open** / **status** / **cost** / **clean**

完整契约见 [docs/cli.md](docs/cli.md)，设计见 [docs/design.md](docs/design.md)。

## 核心纪律

- 确定性动作进 npc；判断留 LLM。
- 生成 ⊥ 验证：执行体永不评判自己。
- 轨迹/结构化契约是唯一真相，不信 LLM 散文。
