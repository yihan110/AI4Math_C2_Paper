# Challenge C2 — AI for Math 论文（AI4Math 可靠性框架）

> 挑战 ID：ch-20260717031343-8ot0ji ｜ 状态：已完成并发布 ｜ 截止：2026-12-31
> 论文题目：**From Natural Language to Verifiable Reasoning: A Semantic Reduction Framework for Reliable AI Mathematics**
> 公开仓库：https://github.com/yihan110/AI4Math_C2_Paper
> 交付物齐全、可编译、可独立使用（已在本地实测编译通过，见第四节）。

## 交付物对照表（与挑战要求一一对应）

| 挑战要求 | 仓库文件 | 说明 |
|---|---|---|
| `paper.tex` | `paper.tex` | 论文主文件（LaTeX），可独立编译 |
| `references.bib` | `references.bib` | BibTeX 引用库，21 条，全部真实可核验 |
| `*AI日志*` | `AI日志.md` | AI 协作日志：每日记录 / 多轮迭代 / 提示词优化 / 人工核验登记表 |
| `*AAR*` | `AAR.md` | 七维 AAR 复盘（含“AI 误导”案例与对策） |
| 附加 | `paper.pdf` | 编译产物，10 页，可直接阅读（无需任何环境） |
| 附加 | `README.md` | 本说明文件 |

## 论文结构（评分维度 researchRigor / technicalExecution 对应）

1. 摘要 Abstract
2. 引言 Introduction
3. 问题定义与三层分解（生成 / 语义规约 / 验证）
4. 相关工作 Related Work
5. 提出框架 Proposed Framework
   - 结构化中间表示（Typed IR）
   - 四阶段流水线（NL → IR → 验证 → 渲染）
   - 双向一致性（interpretability / traceability）
   - **原创贡献 ①**：语义规约失败分类 F1–F4
   - **原创贡献 ②**：可验证性证书 V0–V4
6. 案例分析 Case-Study Analysis（AlphaProof / LLM 智能体 / 反例构造）
7. 评估协议 Evaluation Protocol（GSM8K / MATH：accuracy、verifiability、consistency）
8. 应用 Applications（ATP / 解题 / 教育评估）
9. 讨论 Discussion（局限与边界）
10. 结论 Conclusion

## 如何编译（本地）

依赖：TeX Live 2026（small 方案 + 以下宏包）或任意完整发行版（MiKTeX/TeX Live）。

```bash
pdflatex paper
bibtex  paper
pdflatex paper
pdflatex paper
```

需要宏包（TeX Live 下可用 `tlmgr install` 补齐）：
`geometry amsmath amsfonts amscls graphics graphics-def hyperref natbib booktabs caption subcaption enumitem microtype xcolor pgf latex-tools`。

也可使用 `latexmk -pdf paper`（若已安装 latexmk）。

**实测结果（2026-10-04，Windows + TeX Live 2026）**：按上述序列执行，`pdflatex → bibtex → pdflatex → pdflatex` 四次调用全部退出码 0，**0 个未定义引用、0 个 LaTeX Error**，输出 `paper.pdf` 共 10 页。论文含 1 幅 TikZ 流程图、4 张表格、3 组公式、9 个章节，无缺图（不使用外部图片文件）。

## 快速开始

1. **只阅读**：直接打开 `paper.pdf`（10 页，无需任何环境）。
2. **取源码**：`git clone https://github.com/yihan110/AI4Math_C2_Paper.git`
3. **重编译**：见上一节四条命令。

## 引用与真实性声明

- 全部 21 条引用均为真实、可公开核验的一手/权威文献（Nature、Science、JMLR、PNAS、arXiv 官方编号、CPP 等）。
- 每处事实性陈述的人工核验记录见 `AI日志.md` 第 5 节“AI 生成结论的人工核验登记表”。
- 无编造引用、无编造实验数据；实验部分以“协议设计 + 目标值”形式呈现，避免虚构数字。

## 仓库状态（GitHub public，已发布）

- 仓库地址：https://github.com/yihan110/AI4Math_C2_Paper （Public，无需登录即可 clone / 在线阅读）
- 远程名：`origin` ｜ 分支：`main`
- 获取最新版本（直连，无需代理）：

```bash
git clone https://github.com/yihan110/AI4Math_C2_Paper.git
cd AI4Math_C2_Paper
```

- 仓库内容：`paper.tex`、`references.bib`、`paper.pdf`、`AI日志.md`、`AAR.md`、`README.md`、`.gitignore`
- 本地工作树干净：`git status` 应为 `nothing to commit, working tree clean`（无未提交改动、无未跟踪文件）。
- 后续更新流程：修改文件 → `git add -A` → `git commit -m "说明"` → `git push origin main`。

## 学术诚信声明

- **无编造引用**：`references.bib` 的 21 条参考文献全部真实、可公开核验（Nature / Science / JMLR / PNAS / arXiv 官方编号等），且与正文 `\cite` 一一对应，无孤立条目、无缺失条目。
- **无编造数据**：实验部分以“评估协议 + 目标值”呈现，明确标注为协议设计而非实测结果，不以虚构数字充数。
- **AI 参与透明**：AI 的使用范围、多轮迭代轮次与人工核验过程完整记录于 `AI日志.md`，含人工核验登记表与“AI 误导”案例的纠正记录。

---
*最后更新：2026-10-04*
