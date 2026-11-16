# **AI 应用开发的 Workflow 是什么？官方学习教程（2026）**

**Workflow（工作流）就是把 AI 应用开发和执行任务所需的步骤，按照一定的顺序组织起来，让各个组件协同完成一个目标。**

在 AI Application Development 中，Workflow 特别重要，因为一个真正的 AI 应用通常不只是调用一次 LLM API，而是包含数据处理、模型调用、工具执行、检索、结果验证和部署。

例如，你开发一个 AI 企业知识库：

1. 用户上传 PDF。
2. 系统读取 PDF。
3. 切分文本。
4. 生成 Embeddings。
5. 保存到 PostgreSQL + pgvector。
6. 用户提问。
7. 检索相关文档。
8. 调用 LLM。
9. 返回答案和引用来源。

这整个过程就是 AI Application Workflow。

## **一、AI 应用开发的完整 Workflow**

[Inside a Production RAG System: Architecture, Stack, and Lessons Learned - DEV Community](https://images.openai.com/static-rsc-4/N1PtstGTj1_GiLjCvUhbnsgKSn2tn7og0-ir0o-1mldC_9vNVr8vUshH_mghBiYhmV2zQynt-6D1gyFNTiE59O4T9W65ea9hsRL-fSSrY3AdUFbBW_kLeCsuDJoxy6FqaVLdjHzRHog2eNXbb5jahK5L2LrgRNURnHIAQ50uot4?purpose=inline)

[dev.to](https://dev.to/seasia_infotech_899dc2c59/inside-a-production-rag-system-architecture-stack-and-lessons-learned-28h7?utm_source=chatgpt.com)

我建议把 AI 应用开发分为 8 个阶段：

1. **Requirements — 需求分析**
   - 确定应用解决什么问题
   - 定义用户和使用场景
   - 确定成功指标
2. **Architecture — 系统架构设计**
   - 前端、后端架构
   - LLM API 选择
   - 数据库和向量数据库
   - RAG 或 Agent 设计
3. **Data Engineering — 数据工程**
   - 数据收集
   - PDF / Word 解析
   - Chunking
   - Embeddings
   - 数据存储
4. **LLM Integration — 模型集成**
   - OpenAI / Claude / Gemini API
   - Prompt Engineering
   - Structured Outputs
   - Streaming
5. **Application Logic — 应用逻辑**
   - Tool Calling
   - RAG
   - MCP
   - Skills
   - Agent / Workflow
6. **Testing & Evaluation — 测试评估**
   - 功能测试
   - RAG 检索准确性
   - Agent 执行成功率
   - 安全性测试
7. **Deployment — 部署**
   - Docker
   - AWS
   - CI/CD
   - API 服务部署
8. **Monitoring & Optimization — 监控优化**
   - 日志和 Tracing
   - Token 成本
   - 响应延迟
   - 模型效果持续改进

OpenAI 官方的 AI 应用开发课程也采用了从基础、应用构建、评估、安全到生产优化的路线。

[image](https://www.google.com/s2/favicons?domain=https://developers.openai.com\&sz=32)

OpenAI Developers



## **二、AI Workflow 有哪几种？**

这部分尤其重要。你需要区分普通应用 Workflow 和 Agent Workflow。

### **1. Sequential Workflow（顺序工作流）**

初级，最容易掌握

每个步骤按固定顺序执行。

**User Input**

**Document Loading**

**Chunking**

**Embedding**

**Vector Database**

**LLM Generation**

**Final Answer**

应用：PDF 处理、文档总结、数据导入。

### **2. Conditional Workflow（条件工作流）**

中级

根据判断结果，选择不同执行路径。

**User Question**

**Question Classification**

**Decision**

**RAG**

知识库问题

**Tool Calling**

外部数据查询

**Final Response**

应用：智能客服、企业 AI Assistant。

### **3. Parallel Workflow（并行工作流）**

中高级

同时执行多个独立任务，然后合并结果。

**User Request: Analyze AMD**

**Parallel Execution**

**Financial**

**Technical**

**News**

**Combine Results**

**AI Analysis Report**

应用：股票分析、市场研究、综合报告。

### **4. Agentic Workflow（智能体工作流）**

高级

Agent 可以根据执行结果动态决定下一步行动，而不是始终按照固定步骤执行。

例如：

- 先搜索资料。
- 如果资料不足，继续搜索。
- 如果需要计算，调用 Python。
- 如果需要数据库数据，调用 MCP。
- 最后检查结果并生成报告。

它通常包含循环、状态管理、工具调用和退出条件。

**重要区别：** Workflow 可以是完全固定的程序流程；Agentic Workflow 则允许模型参与决策。实际项目经常将两者结合，关键步骤使用确定性代码，适合动态决策的步骤交给 Agent。

## **三、Workflow 和 Agent 有什么区别？**

这是 AI Engineer 面试常见问题。

| 比较   | Workflow | Agent    |
| ---- | -------- | -------- |
| 执行方式 | 通常按预设步骤  | 根据目标动态决策 |
| 流程控制 | 程序控制     | 模型参与决策   |
| 工具调用 | 可以       | 可以       |
| 循环执行 | 可以预先设计   | 可以动态决定   |
| 可预测性 | 通常较高     | 通常较低     |
| 适用场景 | 固定业务流程   | 复杂、多步骤任务 |

我的建议：**先掌握 Workflow，再学习 Agent。**

企业生产系统不一定需要完全自主的 Agent。很多时候，Workflow + LLM 就能解决问题，而且更容易测试、维护和控制成本。

## **四、AI Workflow 开发框架**

建议重点学习以下 5 个。

[Cognee - Open-Source Agent Memory Platform](https://images.openai.com/static-rsc-4/wL63mMHjP9A4nG7QHBfJUeUo29Z8_5vwHzEJEymfNWI92wcSfSDSK3DN1KAjBF_KzENTQBuV3lOp_Bv2N5i2LyVyNRI9nROlb71BDgT896s6U_MgivtiGv0HgtO85XYEOz2GSWE5NlbnVCiV7-B4wYrSpb_REXAGSUVIU9MrWjU?purpose=inline)

**1. LangGraph**

重点学习

- Sequential / Conditional
- Parallel Execution
- State Management
- Checkpointing
- Human-in-the-loop

[官方教程](https://docs.langchain.com/oss/python/langgraph/overview?utm_source=chatgpt.com)

[OpenAI Agents SDK: Streamlining Enterprise AI Development with Minimal Abstractions](https://images.openai.com/static-rsc-4/u5-3ODDjmZY9ZGVhCtG4lH2WTbo2jICG9KhIJl9IGTHSVYJDTbqNHdt1s-wpJRQ5QTDf4GwEEH7ELekXKqfjaSH92jbSfXMxSmdffUv0rrU5FmSdwIN2XAR8GPiiZfqXEiXoVP43UlNRq4120lHMRdDgA9e9LTtP9LiI2Xku1vY?purpose=inline)

**2. OpenAI Agents SDK**

- Agent Loop
- Handoffs
- Tools
- Guardrails
- Tracing

[官方教程](https://developers.openai.com/api/docs/guides/agents/sdk?trk=article-ssr-frontend-pulse_little-text-block\&utm_source=chatgpt.com)

[How does Google Agent Development Kit compare to other AI...](https://images.openai.com/static-rsc-4/LtM2JSbmZQ7xAWBfRot3krlHN8xAQ6TnkTkBAENRj-llijhI0Tdr3Bh78mh7uynyrmkyfANcSRTRpmlS0n7IWVlYX_WkTGpysNGPbqwBLihJPRmrd_-ZiIwvwGbcDN-whrnkRSrF4nwCp-mOHgj_rY4HkvqnnMua52nu6si1WOg?purpose=inline)

**3. Google ADK**

- Sequential Agents
- Parallel Agents
- Loop Agents
- Multi-Agent Workflow

[官方教程](https://google.github.io/adk-docs/?utm_source=chatgpt.com)

[Vercel AI SDK Logo PNG Vector (SVG) Free Download](https://images.openai.com/static-rsc-4/HsW3d8YEPPhLYrecMnxwdu9B769HQghdnpzcsNGyfUIQcatjLEjqoKbFYN2cFQRtvnwiQyIjBleZ8AMyWcNxekXBU4Nf4orX6ujX9cfCEsMugYbGo0KFNMVVlU7J8PqBB8zWlN0gddM1GV76y6Yt3r_9gqox5z8Q0kz1pTy2aNk?purpose=inline)

**4. Vercel AI SDK**

- Next.js AI 应用
- Tool Calling
- Streaming
- Agent 开发

[官方教程](https://ai-sdk.dev/docs/introduction?utm_source=chatgpt.com)

[AWS - Amazon Web Services Logo PNG Vector (SVG) Free Download](https://images.openai.com/static-rsc-4/XC8qnE2iY5UhcUmwJ8upDQJvEvEzL0PDLUOoP-MfX7BKCQyj7JMiLPcANiij-DDbkscqNA0SySHyYkbANvG_MhDAPY4A8P1hT2WP9dVm41qpjBKHqdf2ec9mIfROf3JAwhue3-Wx-OgSii9kPXBTXzVZrNplBlIGgf_nMdrgN5E?purpose=inline)

**5. AWS Step Functions**

- Workflow Orchestration
- State Machines
- Retry / Error Handling
- AWS 服务集成

[官方教程](https://docs.aws.amazon.com/step-functions/?utm_source=chatgpt.com)

## **五、官方学习教程（2026）**

以下是我最推荐收藏的官方学习资料。

**1. OpenAI — AI Application Development**

最推荐先学

[AI Application Development: Concept to Production](https://developers.openai.com/tracks/ai-application-development?utm_source=chatgpt.com)

从基础概念、AI Agent、RAG、应用构建，到评估、安全和生产优化。

[image](https://www.google.com/s2/favicons?domain=https://developers.openai.com\&sz=32)

OpenAI Developers



**2. OpenAI — Building Agents**

[Building Agents Guide](https://platform.openai.com/docs/guides/agents?utm_source=chatgpt.com)

学习 Agent 设计、工具调用和任务执行。

**3. LangGraph — Workflows and Agents**

[官方 Workflow 和 Agent 教程](https://docs.langchain.com/oss/python/langgraph/workflows-agents?utm_source=chatgpt.com)

**4. OpenAI — Practical Guide to Building Agents**

[A Practical Guide to Building Agents](https://cdn.openai.com/business-guides-and-resources/a-practical-guide-to-building-agents.pdf?file=a-practical-guide-to-building-agents.pdf\&utm_source=chatgpt.com)

学习 Agent 设计原则、工具和工作流。

**5. AWS — Agentic AI Patterns and Workflows**

[AWS 官方架构指南](https://docs.aws.amazon.com/pdfs/prescriptive-guidance/latest/agentic-ai-patterns/agentic-ai-patterns.pdf?utm_source=chatgpt.com)

**6. Vercel — AI Agent Development**

[Build AI Agents with AI Gateway and AI SDK](https://vercel.com/kb/guide/ai-gateway-and-ai-sdk?utm_source=chatgpt.com)

学习 TypeScript、AI Agent 和 Workflow 集成。

## **六、30 天 AI Workflow 学习计划**

每天 2 小时

| 时间        | 学习内容                        | 实践目标            |
| --------- | --------------------------- | --------------- |
| Day 1–3   | AI Application Architecture | 理解整体架构          |
| Day 4–6   | Sequential Workflow         | 开发顺序流程          |
| Day 7–9   | Conditional Workflow        | 开发条件分支          |
| Day 10–12 | Parallel Workflow           | 开发并行任务          |
| Day 13–15 | Python + FastAPI            | 开发后端服务          |
| Day 16–18 | LLM API + Tool Calling      | 集成模型和工具         |
| Day 19–21 | RAG Workflow                | 建立知识库流程         |
| Day 22–24 | LangGraph                   | State、Node、Edge |
| Day 25–26 | Agent Workflow              | 开发动态 Agent      |
| Day 27–28 | Evaluation                  | 测试和评估           |
| Day 29–30 | Docker + AWS                | 部署项目            |

## **七、建议做的 3 个 GitHub 实战项目**

[GenAIIDP Web User Interface | GenAI IDP](https://images.openai.com/static-rsc-4/17X31cYVAS8rQc33GUOZ9iTyhI9BEg0ULXm7HKFrRdFsmZqy5Gx1nAOxwBtaogVxFz55rbHa7oC6-mgppMSbv0AZm1p1KdOZskN_ksY30-FVEqKziHEVkagcZXxwACrj0FbKaKnnyj7vuigh0854Ts3464Xnd5m4ZttCYPkM4FU?purpose=inline)

**项目 1：PDF Processing Workflow**

初级

- PDF 上传
- 文档解析
- 文本切分
- Embedding
- PostgreSQL 存储

技术：Python + FastAPI + PostgreSQL

[How to Build a Custom (RAG) Chatbot in Keboola](https://images.openai.com/static-rsc-4/7UEyPDUZCQWSEbigmCGuSGeDiw3NqhUpx07aGTcV02dNaEccKM-kGnw0j13yNBe3XyB4JFX6UztKOySmHMP8nwT6SWnt29-gmBaVyzzEW-P6FkF3C2mXc6AKYR4gnOFdGCflK70dQrRHhZn597pCKzHYEQ_po5eO2rpk8Xjr8R0?purpose=inline)

**项目 2：Enterprise RAG Workflow**

中级

- RAG 检索
- Hybrid Search
- Reranking
- 多模型调用
- 自动生成报告

技术：LangGraph + OpenAI + pgvector

[ImpireX | AI Agents](https://images.openai.com/static-rsc-4/4DZ2TbL0Nn3ReiRFbSrgtWaKNb79E-Wtea_l_IbA98h_YjKhlfy1O5fRKZ0MwTqrWc0Ssb4OT2RTyUullg7rpaqSLtMyFKGS6r5OE-BRGpKpjzEjY-oKw75P4smxDa53l7Ntvakkw70gk-XUeSS5vh0q7EP1AW94YqG4xI5PKf0?purpose=inline)

**项目 3：Multi-Agent Workflow Platform**

高级

- Research Agent
- Analyst Agent
- Writer Agent
- MCP 工具连接
- 人工审批
- 任务状态管理

技术：LangGraph + MCP + FastAPI + Next.js

## **八、推荐的 AI 应用开发整体架构**

这是建议你最终掌握的企业级开发架构：

**Frontend**

Next.js + React + TypeScript

**Backend**

Python + FastAPI

**Workflow Orchestration**

LangGraph + OpenAI Agents SDK

**RAG**

LangChain + pgvector

**Integration**

MCP + Tool Calling

**Infrastructure**

Docker + AWS + PostgreSQL + Redis

## **九、最终学习优先级**

如果目标是 2026 年美国 AI Engineer / AI Application Developer，我建议：

| 优先级 | 技术                      |
| --- | ----------------------- |
| 1   | Python + FastAPI        |
| 2   | LLM API                 |
| 3   | Prompt Engineering      |
| 4   | Tool Calling            |
| 5   | RAG                     |
| 6   | Workflow Design         |
| 7   | LangGraph               |
| 8   | MCP                     |
| 9   | Agent + Skills          |
| 10  | Evaluation + Deployment |

**我的核心建议：先学 LangGraph 的 Workflow，再学 Agent。**

因为企业级 AI 应用真正重要的是：能够把 LLM、RAG、数据库、API、MCP 和业务逻辑组织成一个可靠、可监控、可部署的完整系统。

官方入门课程建议从这里开始：

[OpenAI AI Application Development — Concept to Production](https://developers.openai.com/tracks/ai-application-development?utm_source=chatgpt.com)。
