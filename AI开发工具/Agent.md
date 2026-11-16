# **Agent 是什么？官方学习资源（2026）**

**AI Agent（人工智能智能体）是一种能够理解目标、规划步骤、调用工具、获取信息并执行任务的 AI 系统。**

简单理解：

普通 LLM 主要负责回答问题；Agent 不仅回答问题，还能根据目标采取行动，完成多步骤任务。

例如，你开发一个 AI 股票分析 Agent，用户说：

> 帮我分析 AMD，查询最新股价、财报、机构持仓，并生成投资分析报告。

Agent 可以：

1. 理解用户目标。
2. 选择股票查询工具。
3. 调用金融数据 API。
4. 查询财报和相关资料。
5. 使用 Python 分析数据。
6. 生成投资分析报告。
7. 将结果保存到数据库。

这就是 AI Agent。

## **一、Agent 的核心架构**

[What Are AI Agents? Complete Guide (2026)](https://images.openai.com/static-rsc-4/a3QbMBEV5ahW6DV7bi9ttvU2kpjWzLCD0mQnuUgdASUBmvEqMCnkZw454on705EYM22WaE1LdzXZEDnTsTGLHpW-srogqslQDUmfUQAs-apAkWIBsXGrk8HSBayO9ZvLqLpu6Gj2G0l9-3PmPDahNJL5aJMaSke9uvqlj4HjjOM?purpose=inline)

[pickaxe.co](https://pickaxe.co/post/what-are-ai-agents?utm_source=chatgpt.com)

Agent 通常包含以下核心组件：

| 组件    | 英文           | 作用                |
| ----- | ------------ | ----------------- |
| 大语言模型 | LLM          | 理解和推理             |
| 指令    | Instructions | 定义任务目标和规则         |
| 规划    | Planning     | 分解任务、制定步骤         |
| 工具    | Tools        | 调用 API、数据库、Python |
| 记忆    | Memory       | 保存相关历史信息          |
| 状态    | State        | 记录任务执行进度          |
| 执行循环  | Agent Loop   | 观察、决策、行动          |
| 评估    | Evaluation   | 检查任务结果            |

## **二、Agent 和 LLM、RAG、MCP、Skills 的区别**

这是 AI Engineer 必须理解的知识。

| 技术           | 核心作用            |
| ------------ | --------------- |
| LLM          | 理解语言、推理、生成答案    |
| RAG          | 从外部知识库检索资料      |
| Tool Calling | 让模型请求调用工具       |
| MCP          | 标准化连接工具和数据      |
| Skills       | 提供可复用的专业任务指令    |
| Agent        | 组织以上能力完成目标      |
| Multi-Agent  | 多个 Agent 协作完成任务 |

例如，一个企业 AI Agent：

- 使用 RAG 搜索公司文件。
- 使用 MCP 连接 PostgreSQL。
- 使用 Tool Calling 查询数据库。
- 使用 Skills 执行财务分析流程。
- 使用 LLM 生成最终报告。

## **三、Agent 的主要类型**

[Single-Agent vs. Multi-Agent Architecture: When to Split and When to Stay Monolithic | by Suresh Kumar Ariya Gowder | Agentic AI & System Design Mastery Series | Mar, 2026 | Medium](https://images.openai.com/static-rsc-4/9aX7PNhESsE3U5-I1xxFlo_aW-ocAayGlk-0Ken7PwkUWj0hdy3SQqrswZZE4IRxTIQNvYYJJskC442lADjF6dDVhrjKGusCmNQDRiBsN9p9amlv1sY-p6ev1Q7FjAE8tElfIAncL37SypS65SK9kq3RY3bm83863aHmfY4cB38?purpose=inline)

**1. Single Agent**

单个 Agent 完成任务。

例如：AI 客服、PDF 分析助手。

[Here’s how I would learn AI Agents as a total beginner - DEV Community](https://images.openai.com/static-rsc-4/jlwj3QCkQI2xgQy6z2TtHIfxg6-vmZ8_dz1Fiy3xqvt29eAYJbxw6aA2SKssT8PW-phqrTrBuw1APTA1LPkOWk3HtR_ofUkTIvOnMSKtkqYXyE9ftmmL3iHhneAQpxoPcraXVT6Wpdvs6-I9j8h8OhjjEwUS71nTA8cmLiRgnQw?purpose=inline)

**2. Multi-Agent**

多个 Agent 分工协作。

例如：Research Agent、Analyst Agent、Writer Agent。

[Core Dynamics Blog — LangChain vs. LangGraph](https://images.openai.com/static-rsc-4/f_0Dwl4Dj_i-2gOmQ8gWOqZZulzV3Bwoo_r7dwo9J_unHo60_BKj_QinzsrX7VMGOGcAtnvZTDpGXUovStZbeBn4QUrCexc1OxfF6_gtJe-txYQXRD58HVQXtXl2Mj6DecWo3LkiRjGtusLypCMU-yY5H03HobU-bDKoSc_iVmc?purpose=inline)

**3. Workflow Agent**

按照确定的工作流程执行任务。

例如：文档审核、订单处理。

[International AI Safety Report 2026 | International AI Safety Report](https://images.openai.com/static-rsc-4/X7yr_ADecU45sYULVb2cVSpbbdJYhjs4V0PA0qy7Q_4pabnh2ce5QWETtRdMYaybwSpkXWMP2wD5OvBYcLV-ZWjYkYGereq7b3wtBU7pj_2mHAI-fPZDdWr506_6r9fi6xxHJIOFkr0Gmn2bsoNgHMVQerfNPFx5OkY-KzFHa7A?purpose=inline)

**4. Autonomous Agent**

能够自主规划、选择工具、反复执行和检查任务。

例如：自动研究、代码开发助手。

注意：Workflow 和 Autonomous Agent 并非完全互斥的分类。实际企业系统通常会组合使用。

## **四、2026 年值得学习的 Agent 开发框架**

这是我建议重点关注的技术。

[Qbit Labs | AI-First MVP Studio](https://images.openai.com/static-rsc-4/6uTjTK_ypWUnb5yDrFgHDv0HqGzlcy9xVeQguw4rJ4a5INGFhiqlR2mwBCLUtxr556fgwceESoauyytugtSZazCS99REkZhL2dzXQ7kgnOnm6d8dN6uovsm8Vy4QoN8PKMG32VORvYjTacS-iuEN0OHRQ0cAqnMUH-bKdzw1LFw?purpose=inline)

**1. LangGraph**

重点学习

- Agent Workflow
- State Management
- Checkpointing
- Human-in-the-loop
- Multi-Agent

官方资源：[LangGraph Documentation](https://docs.langchain.com/oss/python/langgraph/overview?utm_source=chatgpt.com)

[OpenAI Agents SDK: Streamlining Enterprise AI Development with Minimal Abstractions](https://images.openai.com/static-rsc-4/u5-3ODDjmZY9ZGVhCtG4lH2WTbo2jICG9KhIJl9IGTHSVYJDTbqNHdt1s-wpJRQ5QTDf4GwEEH7ELekXKqfjaSH92jbSfXMxSmdffUv0rrU5FmSdwIN2XAR8GPiiZfqXEiXoVP43UlNRq4120lHMRdDgA9e9LTtP9LiI2Xku1vY?purpose=inline)

**2. OpenAI Agents SDK**

重点学习

- Agents
- Tools
- Handoffs
- Guardrails
- Tracing

官方资源：[OpenAI Agents SDK](https://openai.github.io/openai-agents-python/?utm_source=chatgpt.com)

[How does Google Agent Development Kit compare to other AI...](https://images.openai.com/static-rsc-4/LtM2JSbmZQ7xAWBfRot3krlHN8xAQ6TnkTkBAENRj-llijhI0Tdr3Bh78mh7uynyrmkyfANcSRTRpmlS0n7IWVlYX_WkTGpysNGPbqwBLihJPRmrd_-ZiIwvwGbcDN-whrnkRSrF4nwCp-mOHgj_rY4HkvqnnMua52nu6si1WOg?purpose=inline)

**3. Google ADK**

- Multi-Agent
- Sequential / Parallel Workflow
- Tool Integration
- Agent Evaluation

官方资源：[Google ADK Documentation](https://google.github.io/adk-docs/?utm_source=chatgpt.com)

[Claude](https://images.openai.com/static-rsc-4/cLHBfiXuOV35_PSb5wC1jXivsAXbOR_8j6QIuMUVJNmHhvqDTZSAjip3DZXEZE8rrigO3zrBPXPTm3OPFqtXG1oYbfxtfR2epfKwRiaR-r0auw26KWwnnPiRgtOfu6qqeScD6KjrINNkb8STcXPBIHcixXdk1xpiKuwC8UdBT_8?purpose=inline)

**4. Claude Agent SDK**

- Agentic Loop
- Tool Use
- MCP
- Subagents
- Permission Control

官方资源：[Claude Agent SDK](https://platform.claude.com/docs/en/agent-sdk/overview?utm_source=chatgpt.com)

[Crew AI Pricing & Reviews 2025 | Techjockey.com](https://images.openai.com/static-rsc-4/JNb7QCnH_dz14wuRNyg6WT0MMpWuF05uhvd27FT-9kRIlDRbNc3W8wiBRs3nfxx4Gng3B312S5M9kQxftb6G6-yIBSecwsRC4uwtvL16Jc2M4lvvEHdi4IwlJ-CG9KuuYQHEt4ErL2_Dd1vh1sYoGNPBMoVEzXQjrxJxAaICp1I?purpose=inline)

**5. CrewAI**

- Agent Roles
- Tasks
- Crews
- Flows

官方资源：[CrewAI Documentation](https://docs.crewai.com/?utm_source=chatgpt.com)

[Microsoft Agent Framework - Framework para agentes de IA generativa](https://images.openai.com/static-rsc-4/J4KD2_NAfPqZU5sr8xu13f4R7MLYv3emPVKUN41k8AJ6UbO3ks3CCj647MDDnUZnvJ5Yst2OlnJaP71ntA6Q38ZBLd3k47wMHHA_8bkVSfe5rtQR1I1nVmTzsT4DX26B5zLc_kucBCdZiSxiDUiL54kgWbBCx_GuyO6Wn699FrA?purpose=inline)

**6. Microsoft Agent Framework**

- Agent Orchestration
- Workflow
- Multi-Agent
- .NET / Python

官方资源：[Microsoft Agent Framework](https://learn.microsoft.com/en-us/agent-framework/?utm_source=chatgpt.com)

这些框架各有侧重。LangGraph 适合复杂、有状态的流程；OpenAI Agents SDK 适合轻量 Agent 和工具交接；Google ADK 适合 Google 生态；CrewAI 适合角色分工。

[image](https://www.google.com/s2/favicons?domain=https://openai.com\&sz=32)

OpenAI+3



## **五、Agent 必须掌握的核心技术**

| 技术                 | 具体知识                    | 优先级 |
| ------------------ | ----------------------- | --- |
| Prompt Engineering | System Instructions     | 必须  |
| Tool Calling       | Function Calling        | 必须  |
| Planning           | Task Decomposition      | 必须  |
| Memory             | Short-term / Long-term  | 必须  |
| RAG                | Knowledge Retrieval     | 必须  |
| MCP                | MCP Client / Server     | 高   |
| State Management   | Agent State             | 高   |
| Multi-Agent        | Handoff / Collaboration | 高   |
| Guardrails         | 安全和权限控制                 | 必须  |
| Evaluation         | Agent 测试与评估             | 必须  |
| Observability      | Tracing / Logging       | 高   |

## **六、30 天 Agent 学习计划**

每天 2 小时

| 时间        | 学习内容           | 实战任务              |
| --------- | -------------- | ----------------- |
| Day 1–3   | Agent 原理、架构    | 创建简单 Agent        |
| Day 4–6   | OpenAI API     | LLM 对话            |
| Day 7–9   | Tool Calling   | 调用 Python 函数      |
| Day 10–12 | Agent Loop     | 自动执行多步任务          |
| Day 13–15 | Memory / State | 保存对话和状态           |
| Day 16–18 | RAG            | 建立知识库             |
| Day 19–21 | MCP            | 连接外部工具            |
| Day 22–24 | LangGraph      | 建立 Agent Workflow |
| Day 25–26 | Multi-Agent    | 多 Agent 协作        |
| Day 27–28 | Evaluation     | 测试 Agent          |
| Day 29–30 | Docker + AWS   | 部署 Agent          |

## **七、建议做的 3 个 GitHub 项目**

[Autonomous Research Assistant Platform — · Built with Blink](https://images.openai.com/static-rsc-4/iaR1hhDWzE_s_CR9TjxFjb_ju41MbU6KgRRLewJnyC4B1oxcZ1nX5uo28NVvf9OjLkkzlOE7tM3CPUF0ti40XtzezqZa-iVASL-tQoDcI-v7vAgckzG43EQnDbnXX05lMYxA9fd6BFmBIUDm_F8ZBljKqhC3BBcJ9q7ZYU0UvJs?purpose=inline)

**项目 1：AI Research Agent**

初级

- 搜索网络资料
- 总结研究结果
- 生成报告

技术：Python + OpenAI API + Tool Calling

[AI Internal Knowledge Search by Mohammed TAYOR on Dribbble](https://images.openai.com/static-rsc-4/UQmigjAZukVk01CB-45P5nBMldyJGulBRvGELdEpQ4ygClyyuEInDWrcU3YDosOZdGDFRk9fKZ3izMZz0jNwoBFhxz0grSPkb3JOAzENtbDiqTG06dhKXcue7_UtYPsJ50zPo3G9H9jE2xK3VHMYCu-1rdDU-pv8K6awdFTO_-0?purpose=inline)

**项目 2：Enterprise RAG Agent**

中级

- PDF 知识库
- PostgreSQL 查询
- MCP 工具连接
- Skills 工作流程

技术：FastAPI + LangGraph + pgvector

[Building a Multi-Agent Financial Analyst Assistant Using the OpenAI Agents SDK | by Dhananjay Kumar | Medium](https://images.openai.com/static-rsc-4/iTyvlob014PdhKw_eOoP2B-_kLUEgieEy_lfFgcwVw5N7LQAzCaP46k_ScdZSuJ7nmYGYWyCLL5nD6b-k0De6emUJtVCCRoPS2AeKLBbk55rd_2w8osmimdbZ9YOuHmRszYMZxYcmtl6ob6mtCdBaRfw6T78gQs2eiZcoRBUgsY?purpose=inline)

**项目 3：Multi-Agent Financial Platform**

高级

- Research Agent
- Financial Analyst Agent
- Risk Agent
- Report Agent
- 人工审批和报告生成

技术：LangGraph + MCP + PostgreSQL + Next.js

## **八、2026 美国 AI Engineer 推荐完整技术路线**

结合你之前学习的 Java、Python、FastAPI、Next.js、PostgreSQL，我建议：

## **AI Engineer 技术栈**

1. **Programming**

   Python + Java + TypeScript
2. **Backend**

   FastAPI + Spring Boot
3. **Database**

   PostgreSQL + Redis + pgvector↳
4. **LLM API**

   OpenAI + Claude + Gemini
5. **LLM Engineering**

   Prompt Engineering + Embeddings + RAG
6. **Tool Integration**

   Function Calling + MCP + Skills
7. **Agent Engineering**

   LangGraph + OpenAI Agents SDK
8. **Advanced AI**

   Multi-Agent + Evaluation + Guardrails
9. **Frontend**

   Next.js + React + TypeScript
10. **Cloud**

    Docker + AWS + CI/CD

## **九、最重要的学习建议**

不要一开始就学习 Multi-Agent。

我建议按照以下顺序：

1. 先开发一个可以调用 Python 函数的 Single Agent。
2. 增加 RAG，让 Agent 能查询自己的知识库。
3. 增加 MCP，让 Agent 能连接外部服务。
4. 增加 Memory 和 State，让 Agent 能保存任务进度。
5. 最后使用 LangGraph 开发 Multi-Agent。

**真正有求职价值的不是会使用某个 Agent 框架，而是能够设计、开发、测试、部署一个可靠的 Agent 系统。**

尤其要掌握 Agent Evaluation、权限管理、人工审批、成本控制和生产环境监控。
