# Challenge C2 — AI for Math 论文（AI4Math 可靠性框架）

> 挑战 ID：ch-20260717031343-8ot0ji ｜ 状态：published ｜ 截止：2026-12-31
> 主题：**From Natural Language to Verifiable Reasoning: A Semantic Reduction Framework for Reliable AI Mathematics**
> 交付物齐全、可编译、可独立使用。

## 项目内容

| 文件 | 说明 |
|---|---|
| `paper.tex` | 论文主文件，可独立编译（pdflatex） |
| `references.bib` | BibTeX 引用库（21 条，全部真实可查，含一手文献） |
| `paper.pdf` | 编译产物（在编译步骤生成） |
| `AI_Log.md` | 每日 AI 协作日志（文献调研/写作迭代/提示词优化/核验记录） |
| `AAR.md` | 七维 AAR 复盘（含“AI 误导”案例与对策） |
| `README.md` | 本说明文件 |

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

## 引用与真实性声明

- 全部 21 条引用均为真实、可公开核验的一手/权威文献（Nature、Science、JMLR、PNAS、arXiv 官方编号、CPP 等）。
- 每处事实性陈述的人工核验记录见 `AI_Log.md` 第 5 节“AI 生成结论的人工核验登记表”。
- 无编造引用、无编造实验数据；实验部分以“协议设计 + 目标值”形式呈现，避免虚构数字。

## 提交说明

项目以 git 仓库组织（见 `.git/`）。提交历史清晰、分阶段；如需推送到 GitHub/Gitee 等 **public 远程仓库**，请在目标平台新建空仓库后，将远程地址配置到 `origin` 并 `git push -u origin main`（首次推送需本机 git 身份/凭据授权，见提交说明）。
