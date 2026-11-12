# Project Development System

一套可复用的 AI 辅助软件工程体系。它从 MyOnlineTools 的实际开发经验中提炼通用方法，并将工程原则、Agent Skill、项目模板和 CI 工作流分层维护。

> 目标不是把每个项目都做成同一种架构，而是让每个项目以合适的复杂度完成需求分析、设计、实现、验证、交付和维护。

## 仓库结构

| 路径 | 用途 |
| --- | --- |
| `standards/` | 跨技术栈的工程原则、生命周期、测试、安全、性能和文档规范 |
| `skills/project-development/` | 可供支持 Agent Skills 的 AI 编程工具读取的开发 Skill |
| `templates/vue3-javascript/` | Vue 3 + JavaScript + Vite 最小项目起点 |
| `.github/workflows/` | 可复用的 GitHub Actions 工作流和仓库自身验证流程 |
| `examples/` | MyOnlineTools 实践案例及消费项目的工作流调用示例 |

## 快速使用

### 1. 使用 Agent Skill

将 `skills/project-development/` 目录整体复制到你的 AI 编程工具所支持的 Agent Skills 目录。Skill 的标准入口是 `SKILL.md`，相关专题规范位于 `references/`。不同工具的安装目录和自动发现机制可能不同，请以对应工具的官方文档为准。

让 Agent 先读取 Skill，再检查目标仓库现状。不要让它跳过仓库审查直接套用模板或重构。

### 2. 使用 Vue 3 + JavaScript 模板

将 `templates/vue3-javascript/` 内的文件复制到新项目：

```bash
npm install
npm run dev
npm run build
```

模板刻意保持轻量，不预装路由、全局状态库、UI 组件库或测试框架。只有项目确实需要时再引入。部署到仓库子路径时，按实际路径设置 Vite `base`。

### 3. 复用 GitHub Actions

可参考 `examples/workflows/frontend-ci-caller.yml`，在消费项目的 `.github/workflows/ci.yml` 中调用：

```yaml
name: CI
on:
  push:
    branches: [main]
  pull_request:

jobs:
  quality:
    uses: shenshou/Project-Development-System/.github/workflows/frontend-ci.yml@main
    with:
      node-version: '24'
      run-build: true
      run-tests: false
      run-audit: false
```

正式项目建议将 `@main` 替换为经过验证的版本 tag 或完整 commit SHA，以避免上游变化影响构建。启用测试、审计前，确认项目脚本、锁文件和依赖管理方式符合工作流要求。工作流默认只申请 `contents: read` 权限；部署权限和 secrets 应由消费项目单独配置。

Lighthouse 工作流同样可复用，调用示例见 `examples/workflows/lighthouse-caller.yml`。调用方应自行配置 `workflow_dispatch` 或 `schedule` 触发器，并传入实际可访问的 `audit-url`；性能分数受运行环境影响，应作为趋势指标而非绝对质量结论。

## 工程原则

- 先理解项目现状，再决定是否改造。
- 先满足需求，再按真实变化边界组织模块。
- 按风险设计测试，不追求测试数量。
- 先测量再优化；昂贵、波动较大的性能审计不必默认阻塞每次提交。
- 安全、可维护性和交付可验证性应贯穿开发流程。
- 不为减少行数、追求文件数量或引入新技术而机械重构。

## 来源与边界

本体系首个实践来源是 `shenshou/MyOnlineTools`：Vue 3 + JavaScript、组合式逻辑拆分、共享 UI 组件、Vitest、Playwright、依赖审计、Bundle budget、Design Tokens 检查和 GitHub Pages 部署。这里只提炼经过实践的工程方法，不包含该项目的业务代码、网址数据、访问令牌或私有配置。

当前仓库是持续演进的工程资产；模板和工作流应在真实消费项目中验证后再标记为稳定版本。
