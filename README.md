# 大数据与人工智能 · 课程作业仓库

> 课程：《大数据与人工智能》
> 本仓库存放本课程的两类产出：**编程作业** 与 **AI 概念学习资料**。
> 仓库为**公开**状态，教师无需申请权限即可查看。

---

## 目录结构

```
bigdata-ai-coursework/
├── README.md
├── .gitignore
│
│   # ---------- 编程作业 ----------
├── assignments/          # 作业代码（.py / .scala 等）
├── data/                 # 数据集（不上传，见下方说明）
├── notebooks/            # Jupyter 笔记本，用于探索与可视化
└── reports/              # 实验报告（Markdown 或 PDF）
│
│   # ---------- AI 概念学习 ----------
├── .workbuddy/
│   └── skills/
│       └── concept-study-generator/
│           └── SKILL.md              # 项目级 Skill
└── learning-materials/
    ├── agent.html                    # 概念一：Agent
    ├── llm-context.html              # 概念二：大模型的上下文
    ├── skill.html                    # 概念三：Skill
    ├── concept-relationship.html     # 三者关系说明（网页版）
    └── concept-relationship.md       # 三者关系说明（Markdown 版，含 Mermaid 图）
```

---

# 第一部分：编程作业

## 命名约定

同一份作业的多个文件用统一前缀，方便对应：

```
assignments/hw1_wordcount.py
notebooks/hw1_exploration.ipynb
reports/hw1_report.md
```

## 关于 `data/`

GitHub 单个文件上限 100MB，数据集一律不入库。
目录本身通过 `.gitkeep` 保留在 Git 中，换电脑克隆后文件夹还在，
但里面的数据文件不会上传 —— 数据集请自行保存备份。

## 环境

- Python 3.12
- 依赖统一放在仓库根目录的 `requirements.txt`

---

# 第二部分：AI 概念学习

## 一、项目级 Skill

| 项目 | 内容 |
|---|---|
| 名称 | `concept-study-generator` |
| 存放路径 | `.workbuddy/skills/concept-study-generator/SKILL.md` |
| 级别 | 项目级（位于本仓库的 `.workbuddy/skills/` 下） |
| 作用 | 输入任意一个新概念，输出一份结构化 HTML 学习资料 |

### 它规定了什么

`SKILL.md` 顶部是 YAML 元数据（`name` 与 `description`），正文规定：

1. **适用场景 / 不适用场景** —— 明确边界，避免误用
2. **输入信息** —— 概念名（必填）+ 学科背景、学习者基础、输出路径（选填，缺失时有默认处理规则）
3. **生成步骤** —— 7 步：定位界定 → 拆解机制 → 设计场景 → 整理易混点 → 核验来源 → 出自测 → 生成并自检
4. **输出结构** —— 固定 9 个章节（速览/目标/问题/机制/场景/易混点/自测/来源/我的疑问）
5. **资料来源要求** —— ≥3 条、必须实际访问验证、禁止编造、不得整段照搬
6. **自检要求** —— 9 条清单，最后一条是底线：
   *"如果删掉所有来源链接，剩下的内容仍然是我自己的理解，而非资料拼接"*

### 它不是一次性提示词

判断标准：**换一个新概念，它还能不能用。**
`SKILL.md` 里没有任何一处写死"Agent""上下文""Skill"这三个词的具体内容，
它规定的是"拿到任意概念后该怎么处理"的流程与标准。可直接用于其他概念，例如：

```
用 concept-study-generator 学习「向量数据库」
```

```
调用 concept-study-generator，概念：思维链（Chain-of-Thought）
学习者基础：刚学完 Transformer
输出路径：learning-materials/chain-of-thought.html
```

## 二、如何在 WorkBuddy 中调用

1. 在 WorkBuddy 中把**本仓库目录**作为工作区打开
2. WorkBuddy 会自动扫描 `.workbuddy/skills/` 目录，将其中的 Skill 注册为项目级 Skill
3. 在对话中直接说出概念名即可调用，例如：

   > 用 concept-study-generator 学习「RAG」

4. Skill 会按 `SKILL.md` 规定的流程执行，并在 `learning-materials/` 下生成对应的 HTML 文件
5. 生成后**必须人工打开浏览器检查排版，并逐条核对来源链接**

若未自动识别，可显式指定路径调用：
> 读取 `.workbuddy/skills/concept-study-generator/SKILL.md`，按它的流程学习「RAG」

## 三、已生成的学习资料

| 文件 | 概念 | 说明 |
|---|---|---|
| `learning-materials/agent.html` | Agent | 智能体的构成、ReAct 循环、工具调用边界 |
| `learning-materials/llm-context.html` | 大模型的上下文 | 上下文窗口、注意力机制、中间信息丢失、上下文工程 |
| `learning-materials/skill.html` | Skill | 指令包结构、按需加载、与提示词/工具的区别 |
| `learning-materials/concept-relationship.html` | 三者关系 | 闭环关系图、上下文如何决定 Agent、Skill 如何沉淀知识 |
| `learning-materials/concept-relationship.md` | 三者关系 | 同上，Markdown 版，含 Mermaid 图（GitHub 可直接渲染） |

每份资料都包含：**个人解释、核心机制、具体应用场景、易混淆点与使用边界、可核查的资料来源**，
以及自测题和"我的疑问"。

**关于 `concept-relationship` 为什么有两个格式**：作业"建议目录结构"中列出的是
`concept-relationship.html`，而"内容要求三"中写作 `concept-relationship.md`。
两者口径不一致，故两个都提供，内容一致。

---

# 第三部分：AI 使用情况与人工核查记录

> 作业要求如实说明：哪些用了 AI，我做了哪些核查和修改。**以下为真实记录。**

## AI 协助完成的部分

| 环节 | AI 的作用 |
|---|---|
| 仓库搭建 | 协助注册、克隆、配置 SSH 与 git 身份 |
| Skill 设计 | 协助梳理 `SKILL.md` 的章节结构与自检清单 |
| 资料生成 | 调用 `concept-study-generator`，由 AI 生成三份 HTML 初稿 |
| Git 操作 | 协助诊断网络与推送问题，生成命令 |
| 关系说明 | 协助整理三个概念的对照表与关系图 |

## 我做的核查

### 1. 逐条验证了所有资料来源链接（本次核查最下功夫的部分）

我写脚本把三份资料里的全部 URL 提取出来，用 `curl` 逐条访问验证，发现并修正了两个真问题：

- **发现"假 200"陷阱。** 有两条链接（`docs.claude.com` 和 `docs.anthropic.com` 域下）
  返回状态码 **200**，但跟随跳转后实际落到 `claude.com/app-unavailable-in-region`，
  **是地区限制页面，根本读不到正文**。如果只看状态码就会误判为"已核验"。
  处理方式：这两条**不用于论证**，并在资料末尾单独列出、如实标注"无法核验"，
  同时声明未采信其中可能存在的字段说明。

- **修正了一处提取导致的误报。** 首次验证时 `claude.com/blog/skills` 报 404，
  排查后发现是提取脚本把中文全角括号 `）` 一起抓进了 URL，链接本身是 **200**，虚惊一场。

最终引用的来源（Anthropic 官方工程博客、arXiv 论文、OpenAI 官方 PDF、MCP 官网等）
**全部经过实际访问确认**，标题与作者取自页面元数据，未凭印象编造。

### 2. 检查了内容是否"整段照搬"

作业明确禁止整段复制 AI 对话结果。我的判断标准是：
**删掉所有来源链接后，剩下的内容还能不能读通、是不是自己的话。**
通读三份资料后做了修改，把几处过于接近原文表述的段落改写成自己的说法，并补充个人理解。

### 3. 核对了 Skill 的可复用性

确认 `SKILL.md` 中没有写死这三个概念的具体内容，换一个新概念仍能工作，
并在"调用示例"一节补了两个其他概念的例子作为验证。

## 我做的人工修改

| 修改 | 原因 |
|---|---|
| 概念关系说明补了 Markdown 版 | 作业"目录结构"与"内容要求三"对文件扩展名要求不一致，两个都提供以消除歧义 |
| `.gitignore` 增加敏感信息规则 | 仓库转为公开，补充了 API Key、私钥、凭据文件、个人信息等排除规则 |
| 修正来源核验记录 | 把"200 但读不到正文"的链接从"已核验"改为"无法核验、未采用" |
| token 换算说明加限定 | 标注为量级估计，提示"需用真实分词器验证"，避免把经验值当成精确结论 |
| 提交邮箱改为隐私邮箱 | 原用 QQ 邮箱，公开仓库会暴露 QQ 号，已改为 GitHub noreply 邮箱 |

## 遇到的问题与解决方式

| 问题 | 解决方式 |
|---|---|
| 校园网封锁 GitHub 的 HTTPS，网页打不开 | 逐一探测端口后发现 **SSH 的 22 端口未被封**，改用 SSH 协议完成克隆与推送 |
| 手动复制 SSH 公钥漏字符，GitHub 报 `Key is invalid` | 改用 `cat ~/.ssh/id_ed25519.pub \| clip` 直接写入剪贴板，不再手抄 |
| 网络抖动导致命令重复执行，产生重复提交 | 用 `git reset --soft` 合并提交后重新推送，并核对本地与远程 HEAD 一致 |
| 目录结构一开始设计成按作业编号分，不符合需求 | 改为按文件类型分（`assignments`/`data`/`notebooks`/`reports`） |

---

# 第四部分：版本与安全说明

- **本仓库为公开仓库**，已确认不含任何敏感信息
- `.gitignore` 已排除：API Key、私钥（SSH/SSL）、云服务凭据、`.env` 文件、个人信息文件、大文件与数据集
- 提交邮箱使用 GitHub 隐私邮箱，提交历史中不暴露 QQ 号
- 提交前已检查：无密码、无 token、无个人隐私内容
- 所有资料来源链接均公开可访问，不含需要授权的内网地址

---

# 附录：Git 常用命令速查

```bash
git status          # 查看当前改动
git add .           # 把所有改动加入暂存区
git commit -m "提交说明"   # 打一个本地存档点
git push            # 推送到 GitHub
git pull            # 拉取远程最新内容
git log --oneline   # 查看提交历史
```

**良好的提交说明**：`hw1: 完成词频统计` —— 说明改了什么、为什么改，
不要写 `update`、`修改` 这类无信息量的内容。

## 作业索引

- 编程作业：待补充
- 概念学习资料：Agent、大模型的上下文、Skill（已完成）
