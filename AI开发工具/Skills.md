# **Skills 是什么？官方学习资源（2026）**

在 AI Agent 开发领域，**Skills（技能）是让 AI Agent 按照一套可复用的指令、知识和工作流程完成特定任务的能力模块。**

简单理解：

- LLM 是 AI 的大脑。
- Tool Calling 是 AI 调用工具的能力。
- MCP 是 AI 连接外部工具和数据的协议。
- Skills 是 AI 完成特定任务时可以遵循的操作指南和工作流程。
- Agent 是把这些能力组合起来完成任务的系统。

例如，你开发一个 AI 股票分析 Agent，可以给它配置：

- `stock-analysis`：股票分析技能。
- `financial-report`：财报分析技能。
- `risk-management`：风险管理技能。
- `market-research`：市场研究技能。

当用户要求分析股票时，Agent 可以选择相关 Skill，按照其中的步骤执行分析，并调用外部工具获取实时数据。

[“Claude Skills很棒，可能比 MCP 更重要” - InfoQ](https://images.openai.com/static-rsc-4/--kxsAPObyHY-8vfBls73FreEtIB5QsuudnkNzovBKo__vDcK6juGsIalxi_FDJ1WZYOhoW6jrUyQOwCRPOVinQejSrn5SEmwTNVVwcHrLda6yC5py5jDQJeCy4aGdQrYz8kGM__CryzgfWfeyHZtywNoMkfi8oxdcQLWkIOlRg?purpose=inline)

[infoq.cn](https://www.infoq.cn/article/yoHN3B9DOwIc4i48GujC?utm_source=chatgpt.com)

## **一、Skills 的核心组成**

目前值得重点学习的是 Agent Skills 这一类开放技能规范。

一个典型的 Skill 通常包含：

| 组成           | 作用          |
| ------------ | ----------- |
| SKILL.md     | 核心技能说明和操作指令 |
| Instructions | 任务执行规则      |
| Workflow     | 具体工作步骤      |
| Scripts      | 可执行脚本       |
| References   | 参考资料        |
| Assets       | 模板、图片等资源    |

典型目录结构：

```
skills/
│
├── stock-analysis/
│   ├── SKILL.md
│   ├── scripts/
│   │   └── analyze.py
│   ├── references/
│   │   └── indicators.md
│   └── assets/
│
├── pdf-analysis/
│   └── SKILL.md
│
└── rag-development/
    └── SKILL.md
```

**重点：SKILL.md 是核心文件。**

它告诉 Agent：

- 什么时候使用这个 Skill。
- 需要什么输入。
- 按什么步骤执行。
- 使用哪些工具。
- 输出什么结果。
- 有哪些限制。

## **二、Skills 和 Tool Calling、MCP 的区别**

这是 AI Agent 开发中非常重要的知识。

| 比较       | Skills   | Tool Calling    | MCP          |
| -------- | -------- | --------------- | ------------ |
| 核心作用     | 指导任务如何完成 | 调用具体函数          | 连接外部工具       |
| 核心内容     | SKILL.md | Function Schema | MCP Protocol |
| 是否包含工作流程 | 是        | 通常不是            | 不是主要职责       |
| 是否能执行代码  | 可配合脚本    | 由应用执行函数         | Server 可提供工具 |
| 是否可以组合   | 可以       | 可以              | 可以           |

用一个企业财务分析 Agent 举例：

- **Skill**：告诉 AI 如何分析财务报表。
- **Tool Calling**：让 AI 调用 `get_revenue()`。
- **MCP**：让 AI 通过标准接口连接财务数据库。
- **Agent**：综合使用以上能力，完成财务分析报告。

## **四者如何协作**

**AI Agent**

任务规划与执行

**Skills**

工作流程和专业知识

**Tool Calling**

函数调用机制

**MCP**

连接外部服务和数据

**External Systems**

PostgreSQL / GitHub / APIs / Files

## **三、Skills 官方学习资源（2026）**

目前建议重点学习以下官方资源。

[Specification - Agent Skills](https://images.openai.com/static-rsc-4/r8pfnSw5X1WVmdqoRm_TQMvjlPECdFle8khc9aQ-MnLNjXCMaDkVDk2_0smrzboPWIYaHu_2BXniRq5PQIlQ0ePkQQLIXdmyC1wKULn4Z3E0TJ-TxwucBaTVsrB2bj2Dl3qiBobBL4WhQunA4AbwY8A53Gi8cFTrwBHXuMYltzQ?purpose=inline)

**1. Agent Skills 开放标准**

最重要

[Agent Skills 官方网站](https://agentskills.io/?utm_source=chatgpt.com)

了解跨平台 SKILL.md 标准。

**2. Agent Skills Specification**

[官方技术规范](https://agentskills.io/specification?utm_source=chatgpt.com)

**3. OpenAI Skills 文档**

[OpenAI Developer — Skills](https://developers.openai.com/api/docs/guides/tools-skills?utm_source=chatgpt.com)

学习如何给 OpenAI Agent 提供可复用的指令和支持文件。

**4. OpenAI Skills GitHub**

[github.com/openai/skills](https://github.com/openai/skills/blob/main/skills/.system/skill-creator/SKILL.md?utm_source=chatgpt.com)

**5. ChatGPT Skills 学习指南**

[Build Skills — ChatGPT Learn](https://learn.chatgpt.com/docs/build-skills?kbid=111697\&utm_source=chatgpt.com)

**6. Anthropic Agent Skills**

[Claude Agent Skills 官方文档](https://platform.claude.com/docs/en/agents-and-tools/agent-skills/overview?utm_source=chatgpt.com)

**7. Anthropic Skills GitHub**

[github.com/anthropics/skills](https://github.com/anthropics/skills?utm_source=chatgpt.com)

查看 PDF、DOCX、PPTX、XLSX 等实用 Skills 示例。

## **四、自己创建一个 Skill（实战）**

假设你要创建一个股票分析 Skill。

项目目录：

```
stock-analysis/
│
├── SKILL.md
│
├── scripts/
│   ├── stock_data.py
│   └── technical_analysis.py
│
├── references/
│   ├── indicators.md
│   └── risk_rules.md
│
└── assets/
    └── report_template.md
```

`SKILL.md` 示例：

```
---
name: stock-analysis
description: Analyze US stocks using financial
  data and technical indicators. Use when the
  user requests stock analysis or market research.
---

# Stock Analysis Skill

## Objective
Analyze US stocks and produce a structured report.

## Workflow

1. Obtain current stock market data.
2. Analyze price trends.
3. Calculate RSI and moving averages.
4. Review financial fundamentals.
5. Evaluate investment risks.
6. Generate a structured report.

## Output

- Stock overview
- Technical analysis
- Financial analysis
- Risk assessment
- Conclusion

## Rules

- Never invent real-time stock prices.
- Identify data sources.
- Clearly distinguish facts from estimates.
```

这个 Skill 可以配合 Python 脚本、股票 API 和 MCP Server 使用。

## **五、Skills 的重要设计原理：Progressive Disclosure**

这是面试值得掌握的概念。

[Developer’s Guide to Building ADK Agents with Skills                                       - Google Developers Blog](https://images.openai.com/static-rsc-4/DilgBwzhAwWwqf4O4HpGqEMN6wu4-HPGOGDLyGu3lQ8M-2grlWtj2nvpXiby36cOgdc43PZSYnYQazp7OgWd_TB-NuXEeiu6HMrizFTfDDjXA9CW0OfsJUSHnKC6sWHjq8ZoethW5dQC6ZkAjRA7rUBESFu4UwZhJyPwDZymRAQ?purpose=inline)

[developers.googleblog.com](https://developers.googleblog.com/developers-guide-to-building-adk-agents-with-skills/?utm_source=chatgpt.com)

Skills 通常采用三级信息加载：

| 层级      | 加载内容                          | 目的     |
| ------- | ----------------------------- | ------ |
| Level 1 | name + description            | 发现技能   |
| Level 2 | SKILL.md 完整指令                 | 执行任务   |
| Level 3 | scripts / references / assets | 按需读取资源 |

好处是不用一开始就把所有技能的详细内容放进 LLM 上下文，减少 Token 消耗。

[image](https://www.google.com/s2/favicons?domain=https://developers.openai.com\&sz=32)

OpenAI API+2



## **六、30 天 Skills 学习计划**

| 时间        | 学习内容                  | 实践目标            |
| --------- | --------------------- | --------------- |
| Day 1–3   | Agent Skills 原理       | 理解 Skills       |
| Day 4–6   | SKILL.md、YAML         | 编写技能文件          |
| Day 7–9   | Instructions、Workflow | 设计工作流程          |
| Day 10–12 | Scripts、Python        | 集成 Python       |
| Day 13–15 | References、Assets     | 管理知识和模板         |
| Day 16–18 | OpenAI Skills         | 创建 OpenAI Skill |
| Day 19–21 | Claude Agent Skills   | 创建 Claude Skill |
| Day 22–24 | Skills + MCP          | 连接外部工具          |
| Day 25–27 | Skills + LangGraph    | 集成 Agent        |
| Day 28–30 | Docker + AWS          | 部署 AI Agent     |

## **七、建议完成的 3 个 GitHub 项目**

[OpenBB Platform — built with AI on Blink](https://images.openai.com/static-rsc-4/h9eiLV1ciuRrmWPUnaGvv6S23NZa8zqLXhrsFuCM5iDPG7AOXCwKwx9mK0SMy6MsZu5YgOYYFZEOsl2RBXffk8Pa8vSRBS7C9kbobNatHzGeM6RqDOOLD_goHID7UzkBct-KU3kUaLkpJPqwnKKgNt5HN9Q8knR8XLhS39d5QB0?purpose=inline)

**项目 1：Financial Analysis Skills**

初级

- 股票分析 Skill
- 财报分析 Skill
- 风险分析 Skill

[AI Internal Knowledge Search by Mohammed TAYOR on Dribbble](https://images.openai.com/static-rsc-4/UQmigjAZukVk01CB-45P5nBMldyJGulBRvGELdEpQ4ygClyyuEInDWrcU3YDosOZdGDFRk9fKZ3izMZz0jNwoBFhxz0grSPkb3JOAzENtbDiqTG06dhKXcue7_UtYPsJ50zPo3G9H9jE2xK3VHMYCu-1rdDU-pv8K6awdFTO_-0?purpose=inline)

**项目 2：Enterprise Skills Platform**

中级

- PDF 分析 Skill
- RAG 检索 Skill
- SQL 查询 Skill
- MCP 集成

[OrchestrateIQ , AI Agent Management Product by Nizam on Dribbble](https://images.openai.com/static-rsc-4/VWYg1LybcWaRhIXPpdv-vpdwkpWfmoDgYOFjeayAdbGBM-kvQvsJAW99E_wr_-8fjummgSeP2MfQCnkNtFKuRh7rnqqh8Wx81LB5MTH10Igl2EstHgr4Fqvt6OK7DYXoRc4zSXAmVVVwX2EegukmfeNYD43wXguld7_UfsJzAxA?purpose=inline)

**项目 3：Multi-Agent Skills Platform**

高级

- 多 Skills 管理
- Agent 自动选择 Skill
- MCP 工具调用
- 多 Agent 工作流
- 权限和安全管理

## **八、2026 美国 AI Engineer 完整学习路线**

把你目前学习的技术整合起来，我建议按照这个顺序：

1. **Programming**

   Python + Java + TypeScript
2. **Backend**

   FastAPI + Spring Boot
3. **Database**

   PostgreSQL + Redis + pgvector
4. **LLM API**

   OpenAI + Claude + Gemini
5. **LLM Engineering**

   Prompt Engineering + Embeddings + RAG↳
6. **Tool Integration**

   Function Calling + MCP↳
7. **Agent Engineering**

   Skills + LangChain + LangGraph↳
8. **Advanced Agent**

   Multi-Agent + Agent Evaluation
9. **Frontend**

   Next.js + React + TypeScript
10. **Cloud & Deployment**

    Docker + AWS + CI/CD

我的核心建议

Skills、MCP、Tool Calling、RAG 是四种不同的能力，不要混为一谈。

如果目标是美国 AI Engineer 求职，建议最终做一个完整的 **Enterprise AI Agent Platform**，把这四种技术整合在一个 GitHub 项目中。

这比单独做几个简单的 ChatGPT API Demo 更能展示实际工程能力。
