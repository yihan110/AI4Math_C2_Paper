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

## 提交说明（GitHub public 仓库）

项目已初始化为 git 仓库（分支 `main`，提交清晰、工作树干净）。推送到 **public** 仓库需你先在 GitHub 完成一次授权（本机当前无已存储的 GitHub 凭据，我无法代你登录）。

**第 1 步：在 GitHub 新建空仓库（公开）**
- 登录 https://github.com/yihan110
- New repository → 名称建议 `AI4Math_C2_Paper` → 可见性选 **Public** → 不勾选任何初始化文件 → Create。
- 复制该仓库地址（HTTPS 或 SSH 均可），形如 `https://github.com/yihan110/AI4Math_C2_Paper.git`。

**第 2 步：配置远程并推送（在桌面项目目录执行）**
```bash
cd C:\Users\lucky\Desktop\AI4Math_C2_Paper
git remote add origin https://github.com/yihan110/AI4Math_C2_Paper.git
git branch -M main
git push -u origin main
```
首次推送会弹出 GitHub 登录窗口（或提示输入 Personal Access Token），按提示授权一次即可；授权后凭据会由 Git Credential Manager 保存，后续 `git push` 无需再登录。

若推送时被提示需要 PAT：在 GitHub → Settings → Developer settings → Personal access tokens → 生成一个带 `repo` 权限的 token，作为密码粘贴即可。

> 说明：`references.bib`、`.gitignore`、README、AI 日志、AAR、paper.tex、paper.pdf 均已纳入本次提交（commit `66d790d`）。如需 Gitee 国内直连版本，把 `origin` 换成对应 gitee.com 仓库地址即可。
