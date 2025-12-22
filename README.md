# iOS App 生态研究仓库

本仓库用于系统化研究 iOS App 生态（分发/隐私/广告/支付/风控/数据采集/网络/安全等），并沉淀可复用的方法论、实验脚本与研究产物。

## 目录结构（建议）

```
docs/                     # 总览文档：研究范围、方法论、规范、索引
research/
  apps/                   # 以“应用”为中心的研究档案（每个 App 一份）
    _template/            # 新建 App 档案的模板
  topics/                 # 以“专题”为中心的知识沉淀（隐私/支付/广告/安全...）
  experiments/            # 可复现实验（抓包/逆向/自动化/基准测试）
artifacts/                # 大体积/二进制/可追溯产物（截图、pcap、报告、ipa 等）
  ipa/
  traffic-captures/
  screenshots/
  reports/
data/                     # 结构化数据（CSV/JSON/SQLite），尽量可再生成
tools/                    # 工具与脚本（frida/mitmproxy/通用脚本）
  scripts/
  frida/
  mitmproxy/
references/               # 参考资料索引（论文/文章/链接清单）
templates/                # 通用模板（访谈提纲/研究记录/检查清单等）
```

## 工作流（推荐）

- **新增一个 App 研究档案**：复制 `research/apps/_template` 为 `research/apps/<bundle-id 或 app-name>`，然后按模板填写。
- **新增一个专题**：在 `research/topics/` 下新建目录或文档（例如 `privacy/`、`payments/`）。
- **产物归档**：抓包文件、截图、分析报告统一放 `artifacts/`，并在对应研究文档中引用路径与生成步骤。

## 命名规范（简化版）

- **App 目录**：`research/apps/<app-name>` 或 `research/apps/<bundle-id>`
- **实验目录**：`research/experiments/<date>-<topic>-<short-title>/`
- **产物文件名**：`YYYYMMDD_<app>_<scene>_<type>`（例：`20251222_wechat_login_pcap`）