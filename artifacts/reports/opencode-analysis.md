# OpenCode 项目分析

> 来源: https://github.com/anomalyco/opencode
> 官网: https://opencode.ai

## 一句话总结

**开源的 AI 编程 Agent**，终端/桌面/IDE 多平台支持，厂商中立，支持 75+ LLM。

---

## 核心功能

### 1. Agent 模式

| 模式 | 权限 | 用途 |
|------|------|------|
| **Build** | 完全访问 | 默认开发模式，可读写文件、执行命令 |
| **Plan** | 只读 | 探索代码，执行前需确认 |
| **@general** | 子 Agent | 通过 `@general` 触发，处理复杂搜索 |

### 2. 多模型支持

- 支持 **75+ LLM 提供商**（通过 Models.dev）
- Claude、GPT、Gemini、本地模型均可
- 可复用现有 Claude Pro/Max 订阅

### 3. IDE 级工具

- **LSP 集成**: 开箱即用，自动加载语言服务协议
- **代码导航**: 定义跳转、引用查找
- **重构支持**: 智能重命名等

### 4. 多平台支持

| 平台 | 状态 |
|------|------|
| 终端 TUI | ✅ 稳定 |
| macOS 桌面 | ✅ 稳定 |
| Windows 桌面 | ✅ 稳定 |
| Linux 桌面 | ⚠️ Beta |
| IDE 扩展 | ✅ 支持 |

### 5. 高级特性

- **并发会话**: 同一项目可运行多个 Agent
- **会话分享**: 生成可分享链接，便于调试协作
- **客户端/服务器架构**: 支持远程运行 Agent
- **隐私优先**: 不存储任何代码或上下文数据

---

## 安装方法

### 方式一：一键安装（推荐）

```bash
curl -fsSL https://opencode.ai/install | bash
```

### 方式二：包管理器

```bash
# npm
npm install -g opencode

# Homebrew (macOS)
brew install opencode

# Scoop (Windows)
scoop install opencode
```

### 方式三：桌面应用

从官网下载: https://opencode.ai

### 方式四：Nix/Flake

支持 Nix 可复现环境安装

---

## 配置

### 配置文件位置

```
~/.config/opencode/opencode.json    # 全局配置
项目目录/.opencode/                  # 项目级配置
```

### 模型配置

支持多种认证方式：
- API Key 直接配置
- OAuth 登录（复用 Claude Pro/Max 等订阅）

---

## 与 Claude Code 对比

| 维度 | OpenCode | Claude Code |
|------|----------|-------------|
| 开源 | ✅ MIT | ❌ 闭源 |
| 模型选择 | 75+ 可选 | 仅 Claude |
| 数据隐私 | 本地处理 | Anthropic 服务 |
| 自托管 | ✅ 支持 | ❌ 不支持 |
| 价格 | 免费 + 自带 Key | 需订阅 |

---

## 项目状态

| 指标 | 数据 |
|------|------|
| GitHub Stars | 47.9k |
| 月活开发者 | 65 万+ |
| Commits | 6,700+ |
| Releases | 648 |
| 贡献者 | 500+ |
| 许可证 | MIT |

---

## 相关链接

- GitHub: https://github.com/anomalyco/opencode
- 官网: https://opencode.ai
- 文档: https://opencode.ai/docs
