# Claude Scientific Skills 项目分析

> 来源: https://github.com/K-Dense-AI/claude-scientific-skills
> 官网: https://k-dense.ai

## 一句话总结

**Claude 的科学研究技能包**，提供 138+ 即用型科学技能，覆盖生物信息学、化学信息学、临床研究、机器学习等领域。

---

## 项目定位

| 属性 | 说明 |
|------|------|
| 类型 | Claude Code 插件/技能包 |
| 定位 | 将 Claude 转变为 AI 科研助手 |
| 技能数量 | 138 个 |
| 开源协议 | MIT |
| 维护方 | K-Dense AI 团队 |

---

## 核心功能

### 技能分类概览

| 领域 | 技能数 | 主要工具 |
|------|--------|----------|
| 科学数据库 | 28+ | OpenAlex, PubMed, bioRxiv, ChEMBL, UniProt, COSMIC 等 |
| Python 包 | 55+ | RDKit, Scanpy, PyTorch Lightning, scikit-learn, BioPython 等 |
| 科学集成 | 15+ | Benchling, DNAnexus, LatchBio, OMERO 等 |
| 分析与写作 | 30+ | 文献综述、科学写作、同行评审、海报制作等 |
| 研究与临床 | 10+ | 假设生成、基金申请、临床决策支持等 |

### 详细技能领域

#### 🧬 生物信息学与基因组学 (16+ 技能)
- 序列分析: BioPython, pysam, scikit-bio, BioServices
- 单细胞分析: Scanpy, AnnData, scvi-tools, Arboreto, Cellxgene Census
- 基因组工具: gget, geniml, gtars, deepTools, FlowIO, Zarr
- 系统发育: ETE Toolkit

#### 🧪 化学信息学与药物发现 (10+ 技能)
- 分子操作: RDKit, Datamol, Molfeat
- 深度学习: DeepChem, TorchDrug
- 对接与筛选: DiffDock
- 类药性分析: MedChem
- 基准测试: PyTDC

#### 🏥 临床研究与精准医疗 (12+ 技能)
- 临床数据库: ClinicalTrials.gov, ClinVar, ClinPGx, COSMIC, FDA 数据库
- 医疗AI: PyHealth, NeuroKit2, 临床决策支持
- 临床文档: 临床报告、治疗计划
- 变异分析: Ensembl, NCBI Gene

#### 🤖 机器学习与AI (15+ 技能)
- 深度学习: PyTorch Lightning, Transformers, Stable Baselines3
- 经典ML: scikit-learn, scikit-survival, SHAP
- 时间序列: aeon
- 贝叶斯方法: PyMC
- 图神经网络: Torch Geometric

#### 📊 数据分析与可视化 (14+ 技能)
- 可视化: Matplotlib, Seaborn, Plotly
- 地理空间: GeoPandas
- 网络分析: NetworkX
- 符号计算: SymPy
- PDF生成: ReportLab

#### 📚 科学写作与传播 (20+ 技能)
- 文献检索: OpenAlex, PubMed, bioRxiv
- 科学写作、同行评审
- 文档处理: XLSX, MarkItDown
- 演示文稿: 科学幻灯片、LaTeX 海报
- 图表绘制: 科学示意图
- AI图像生成: FLUX.2 Pro, Gemini 3 Pro

---

## 安装方式

### 方式一：Claude Code（推荐）

```bash
# 1. 安装 Claude Code
curl -fsSL https://claude.ai/install.sh | bash  # macOS/Linux
# 或 Windows:
irm https://claude.ai/install.ps1 | iex

# 2. 注册市场
/plugin marketplace add K-Dense-AI/claude-scientific-skills

# 3. 在 Claude Code 中选择并安装技能
```

### 方式二：Cursor IDE

一键安装：通过 Cursor MCP 安装按钮

### 方式三：任意 MCP 客户端

```
# 托管 MCP 服务器
https://mcp.k-dense.ai/claude-scientific-skills/mcp
```

---

## 使用示例

### 药物发现流程

```
使用你可用的技能。从 ChEMBL 查询 EGFR 抑制剂 (IC50 < 50nM)，
用 RDKit 分析构效关系，用 datamol 生成改进类似物，
用 DiffDock 对 AlphaFold EGFR 结构进行虚拟筛选，
在 PubMed 搜索耐药机制，检查 COSMIC 中的突变，
生成可视化和综合报告。
```

**使用的技能**: ChEMBL, RDKit, datamol, DiffDock, AlphaFold DB, PubMed, COSMIC

### 单细胞 RNA-seq 分析

```
加载 10X 数据集用 Scanpy 进行 QC 和双细胞去除，
与 Cellxgene Census 数据整合，使用 NCBI Gene 标记识别细胞类型，
用 PyDESeq2 进行差异表达分析，用 Arboreto 推断基因调控网络，
通过 Reactome/KEGG 进行通路富集，用 Open Targets 识别治疗靶点。
```

**使用的技能**: Scanpy, Cellxgene Census, NCBI Gene, PyDESeq2, Arboreto, Reactome, KEGG, Open Targets

### 临床变异解读

```
用 pysam 解析 VCF 文件，用 Ensembl VEP 注释变异，
查询 ClinVar 获取致病性信息，检查 COSMIC 中的癌症突变，
从 NCBI Gene 获取基因信息，用 UniProt 分析蛋白质影响，
在 PubMed 搜索病例报告，检查 ClinPGx 获取药物基因组学信息，
用 ReportLab 生成临床报告，在 ClinicalTrials.gov 查找匹配的临床试验。
```

**使用的技能**: pysam, Ensembl, ClinVar, COSMIC, NCBI Gene, UniProt, PubMed, ClinPGx, ReportLab, ClinicalTrials.gov

---

## 技术要求

| 依赖 | 要求 |
|------|------|
| Python | 3.9+（推荐 3.12+）|
| 包管理器 | uv |
| 客户端 | Claude Code, Cursor, 或任意 MCP 兼容客户端 |
| 系统 | macOS, Linux, 或 Windows WSL2 |

### 安装 uv

```bash
# macOS/Linux
curl -LsSf https://astral.sh/uv/install.sh | sh

# Windows
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"

# 或通过 pip
pip install uv
```

---

## 技能结构

每个技能包含：
- ✅ 完整文档 (`SKILL.md`)
- ✅ 实用代码示例
- ✅ 使用场景与最佳实践
- ✅ 集成指南
- ✅ 参考资料

---

## 适用场景

| 场景 | 说明 |
|------|------|
| 药物发现 | 虚拟筛选、先导化合物优化、ADMET 预测 |
| 生物信息学 | 序列分析、单细胞分析、变异注释 |
| 临床研究 | 临床试验检索、变异解读、药物安全 |
| 多组学 | 多组学整合、通路分析、生物标志物发现 |
| 数据分析 | 统计分析、发表级图表、网络可视化 |
| 实验室自动化 | 液体处理协议、工作流自动化 |

---

## 项目状态

| 指标 | 数据 |
|------|------|
| GitHub Stars | 4.1k |
| Forks | 470 |
| Commits | 192 |
| 技能数量 | 138 |
| 许可证 | MIT |

---

## 商业版本

K-Dense 提供企业级产品 [K-Dense Web](https://app.k-dense.ai)：
- 端到端研究工作流
- 计算基础设施
- 发表级输出质量
- 高级 AI 共同科学家功能

---

## 相关链接

- GitHub: https://github.com/K-Dense-AI/claude-scientific-skills
- 官网: https://k-dense.ai
- 产品: https://app.k-dense.ai
- 文档: [docs/scientific-skills.md](https://github.com/K-Dense-AI/claude-scientific-skills/blob/main/docs/scientific-skills.md)
- 示例: [docs/examples.md](https://github.com/K-Dense-AI/claude-scientific-skills/blob/main/docs/examples.md)
