# Oh My OpenCode 项目分析

> 来源: https://github.com/code-yeongyu/oh-my-opencode

## 一句话总结

**OpenCode 的增强插件包**，通过多 Agent 协作和 IDE 级工具提升 AI 编程能力。

---

## 项目定位

| 属性 | 说明 |
|------|------|
| 类型 | OpenCode 插件/配置增强包 |
| 类比 | 相当于 Zsh 的 "Oh My Zsh" |
| 目标 | 让 AI 生成的代码质量媲美人类 |
| 投入 | 作者烧了 $24,000 token 进行测试验证 |

---

## 核心功能

### 1. 多 Agent 协作系统

| Agent 名称 | 模型 | 职责 |
|-----------|------|------|
| **Sisyphus** | Claude Opus 4.5 | 主编排器，任务分配调度 |
| **Oracle** | GPT-5.2 | 架构设计、调试专家 |
| **Librarian** | Claude Sonnet 4.5 | 文档分析、代码库理解 |
| **Explore** | - | 高速仓库扫描 |
| **Frontend Engineer** | Gemini 3 Pro | UI/UX 设计开发 |
| **Document Writer** | Gemini | 技术文档撰写 |

### 2. IDE 级开发工具

- **LSP 集成**: 代码导航、重构支持
- **AST 感知搜索**: 结构化代码搜索和替换
- **会话管理**: 跨 OpenCode 对话的上下文保持
- **上下文注入**: 自动加载 AGENTS.md 和条件规则

### 3. 工作流自动化

- **后台 Agent 执行**: 支持并行任务处理
- **Ralph Loop**: 自引用开发循环
- **Todo 完成强制器**: 防止任务半途而废
- **关键词触发**: `ultrawork`/`ulw` 自动激活全并行编排

### 4. 内置 MCP 服务

| MCP | 用途 |
|-----|------|
| Context7 | 文档上下文 |
| Exa | 网页搜索 |
| grep.app | GitHub 代码搜索 |

---

## 安装方式

```bash
bunx oh-my-opencode install
```

**前置要求**: 需要已有 Claude / ChatGPT / Gemini 的 API 订阅

---

## 配置体系

### 配置层级

1. **用户级配置**: 全局默认设置
2. **项目级配置**: 项目特定覆盖
3. **本地覆盖**: 个人本地调整

### 可配置项

- Agent 模型选择和行为
- 权限粒度（文件编辑、bash 执行、网络访问）
- Hook 管理（会话生命周期事件）
- MCP 服务器配置
- LSP 服务器定制

### 配置格式

支持 **JSONC** (带注释的 JSON)

---

## 设计理念

### 核心原则

1. **代码质量优先**: AI 生成的代码应与人类代码无异
2. **避免 token 浪费**: 拒绝臃肿的子 Agent 和工具集
3. **注释检查器**: 防止过度 AI 生成注释
4. **合理默认值**: 开箱即用，但完全可定制

### 兼容性

- 与 Claude Code 配置向后兼容
- 可加载 Claude Code 的 commands、skills、agents、hooks
- 提供平滑迁移路径

---

## 快速激活

使用魔法关键词即可激活完整并行编排：

```
ultrawork
```

或简写：

```
ulw
```

---

## 适用场景

- 使用 OpenCode 作为主力 AI 编程工具
- 需要处理复杂多模块开发任务
- 希望多个专科 Agent 协作而非单一 Agent
- 追求 AI 代码质量接近人类标准

---

## 相关链接

- GitHub: https://github.com/code-yeongyu/oh-my-opencode
- 分支: dev
