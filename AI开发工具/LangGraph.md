# **LangGraph 是什么？官方学习教程（2026）**

**LangGraph 是一个用于开发、管理和运行 AI Agent 及复杂 AI Workflow 的开源框架。**

它由 LangChain 团队开发，主要使用 Python 和 TypeScript。

简单理解：

普通 LLM API 负责回答问题；LangChain 帮助开发者快速组合模型和工具；**LangGraph 则让你精确控制 AI Agent 的执行流程、状态、循环、记忆和人工审批。**

例如，你开发一个 AI 股票研究 Agent：

1. 查询 AMD 最新行情。
2. 查询 AMD 财报。
3. 搜索相关新闻。
4. 分析技术指标。
5. 检查风险。
6. 如果数据不足，重新查询。
7. 生成投资研究报告。

LangGraph 可以把这些步骤组织成一个可控制、可恢复的执行图。

[Task-Oriented AI Agents with LangGraph - Euron Daily | Euron Community](https://images.openai.com/static-rsc-4/SvN1Hcog9xRkkSpxoOddUqiFyFSQcqoX-PcTwGxNzvlEGPbwcGIspgC6Ugmd7odON63gYQfhXnqEvOTIve0RosHE4gCUGzo97vB2WkNWofH0EuelA4GYh2XmiEIKHE8pYb08B-C6vsG89gW78zR_LqZytTY3fpHP7zi6FYchFII?purpose=inline)

[euron.one](https://euron.one/community/posts/62469ad6-f24b-4673-bdd8-4d3b1f0e11ef?utm_source=chatgpt.com)

## **一、LangGraph 的核心架构**

LangGraph 最重要的是三个概念：

| 核心概念 | 英文    | 作用                |
| ---- | ----- | ----------------- |
| 状态   | State | 保存整个 Workflow 的数据 |
| 节点   | Nodes | 执行具体任务            |
| 边    | Edges | 决定下一步执行哪个节点       |

官方定义：State 保存共享状态，Node 执行逻辑，Edge 控制执行路径。

[image](https://www.google.com/s2/favicons?domain=https://github.com\&sz=32)

GitHub+1



### **1. State（状态）**

保存 Agent 执行过程中的信息。

例如：

```
state = {    "stock": "AMD",    "price": 220,    "financial_data": {},    "news": [],    "analysis": "",    "risk_level": ""}
```

### **2. Nodes（节点）**

每个 Node 负责一项任务。

```
def get_stock_price(state):    return {"price": 220}def analyze_financials(state):    return {"analysis": "Financial analysis"}def check_risk(state):    return {"risk_level": "Medium"}
```

### **3. Edges（边）**

决定节点之间如何连接。

例如：

```
START
  |
  v
Get Stock Price
  |
  v
Analyze Financials
  |
  v
Check Risk
  |
  v
Generate Report
  |
  v
 END
```

实际开发中，Edge 还可以根据条件决定走哪个分支，甚至返回前面的节点形成循环。

## **二、LangGraph 能解决什么问题？**

| 能力                  | 用途         |
| ------------------- | ---------- |
| Sequential Workflow | 顺序执行       |
| Conditional Routing | 条件分支       |
| Parallel Execution  | 并行执行       |
| Cyclic Workflow     | 循环执行       |
| State Management    | 管理任务状态     |
| Persistence         | 保存执行进度     |
| Short-term Memory   | 会话记忆       |
| Human-in-the-loop   | 人工审批       |
| Multi-Agent         | 多 Agent 协作 |
| Streaming           | 实时输出       |

特别值得学习的是：

- **Checkpointing**：保存执行状态，出错后可以恢复。
- **Human-in-the-loop**：在关键操作前暂停，等待人工审核。
- **Durable Execution**：支持长时间运行的任务和中断恢复。

这些是 LangGraph 的核心优势。

[image](https://www.google.com/s2/favicons?domain=https://github.com\&sz=32)

GitHub+1



## **三、LangGraph 和 LangChain 有什么区别？**

这是非常重要的面试知识。

# **LangChain**

**Agent 开发框架**

模型集成、Tools、Prompt、Agent 基础循环

# **LangGraph**

**Workflow 编排运行框架**

State、Nodes、Edges、循环、持久化、人工审批

# **LangSmith**

**开发与运维平台**

Tracing、Evaluation、Monitoring、Deployment

| 比较          | LangChain          | LangGraph           |
| ----------- | ------------------ | ------------------- |
| 主要作用        | 快速开发 LLM 应用和 Agent | 控制复杂 Agent Workflow |
| 工具集成        | 很强                 | 可以集成                |
| 状态管理        | 有相关能力              | 核心能力                |
| 循环控制        | 支持 Agent Loop      | 灵活控制                |
| 人工审批        | 支持相关集成             | 原生支持中断和恢复           |
| Multi-Agent | 支持                 | 支持复杂编排              |

**我的建议：先掌握 LangChain 的模型和工具基础，再重点学习 LangGraph。**

但有一点要注意：LangGraph 可以独立使用，不要求必须学习或安装 LangChain。LangChain 的 Agent 本身也建立在 LangGraph 之上。

[image](https://www.google.com/s2/favicons?domain=https://github.com\&sz=32)

GitHub+1



## **四、LangGraph 官方学习教程（2026）**

以下都是值得收藏的官方资源。

[Qbit Labs | AI-First MVP Studio](https://images.openai.com/static-rsc-4/6uTjTK_ypWUnb5yDrFgHDv0HqGzlcy9xVeQguw4rJ4a5INGFhiqlR2mwBCLUtxr556fgwceESoauyytugtSZazCS99REkZhL2dzXQ7kgnOnm6d8dN6uovsm8Vy4QoN8PKMG32VORvYjTacS-iuEN0OHRQ0cAqnMUH-bKdzw1LFw?purpose=inline)

**1. LangGraph 官方网站**

必学

[LangGraph 官网](https://www.langchain.com/langgraph?utm_source=chatgpt.com)

**2. 官方完整文档**

[LangGraph Documentation](https://github.com/langchain-ai/docs/blob/main/src/oss/langgraph/overview.mdx?utm_source=chatgpt.com)

**3. Quickstart 快速入门**

[LangGraph Quickstart](https://docs.langchain.com/oss/python/langgraph/quickstart?utm_source=chatgpt.com)

**4. Graph API**

[Graph API Overview](https://github.com/langchain-ai/docs/blob/main/src/oss/langgraph/graph-api.mdx?utm_source=chatgpt.com)

学习 State、Nodes、Edges、StateGraph。

**5. Workflows and Agents**

[官方 Workflow 教程](https://docs.langchain.com/oss/python/langgraph/workflows-agents?utm_source=chatgpt.com)

**6. Persistence**

[Persistence 官方教程](https://docs.langchain.com/oss/python/langgraph/persistence?utm_source=chatgpt.com)

**7. Human-in-the-loop**

[Interrupts 官方教程](https://docs.langchain.com/oss/python/langgraph/interrupts?utm_source=chatgpt.com)

**8. LangGraph GitHub**

[GitHub Repository](https://github.com/langchain-ai/langgraph?utm_source=chatgpt.com)

**9. LangSmith**

[Observability 官方教程](https://docs.langchain.com/oss/python/langgraph/observability?utm_source=chatgpt.com)

## **五、Python 实战：创建第一个 LangGraph**

建议先使用 Python。

**第一步：安装**

```
pip install -U langgraph
```

**第二步：创建 graph.py**

```
from typing_extensions import TypedDictfrom langgraph.graph import StateGraph, START, END# 1. Define Stateclass State(TypedDict):    question: str    answer: str# 2. Define Nodesdef analyze(state: State):    return {        "answer": f"AI analyzed: {state['question']}"    }def generate(state: State):    return {        "answer": state["answer"] + " - Completed"    }# 3. Build Graphbuilder = StateGraph(State)builder.add_node("analyze", analyze)builder.add_node("generate", generate)builder.add_edge(START, "analyze")builder.add_edge("analyze", "generate")builder.add_edge("generate", END)# 4. Compilegraph = builder.compile()# 5. Executeresult = graph.invoke({    "question": "What is AI Agent?",    "answer": ""
```

**第三步：运行**

```
python graph.py
```

这个例子没有调用真实 LLM，只是帮助你理解 State、Node、Edge 的关系。下一步可以把 `analyze()` 替换成 OpenAI API 调用。

## **六、LangGraph 30 天学习计划**

每天 2 小时

| 时间        | 学习内容                   | 实战目标       |
| --------- | ---------------------- | ---------- |
| Day 1–3   | LangGraph Architecture | 理解架构       |
| Day 4–6   | State / Nodes / Edges  | 创建 Graph   |
| Day 7–9   | Sequential Workflow    | 顺序执行       |
| Day 10–12 | Conditional Edges      | 条件分支       |
| Day 13–15 | Cyclic Workflow        | 循环执行       |
| Day 16–18 | Tool Calling           | 调用外部工具     |
| Day 19–21 | Memory / Persistence   | 状态持久化      |
| Day 22–24 | Human-in-the-loop      | 人工审批       |
| Day 25–27 | Multi-Agent            | 多 Agent 协作 |
| Day 28–30 | LangSmith + Docker     | 测试与部署      |

## **七、建议做的 3 个 GitHub 项目**

[agentic ai research partner | Devpost](https://images.openai.com/static-rsc-4/GpBg4E6rIt5zHFuDaLt5mWVRtgzZvkBySlxzPgEZUu6EGUabZSddiwLW732OC7OeZ5fddd75Nn_vdEJE7H0d1VsRQIHaz_5-vVToy4Ay86DhAUv-oru6MBqAoTFf92RE7avMaliUJNn4ejRB2qzHDkFs-gonuMZkpceTKqtDx1s?purpose=inline)

**项目 1：AI Research Workflow**

初级

- 搜索资料
- AI 总结
- 自动生成报告

技术：Python + LangGraph + OpenAI

[AI Internal Knowledge Search by Mohammed TAYOR on Dribbble](https://images.openai.com/static-rsc-4/UQmigjAZukVk01CB-45P5nBMldyJGulBRvGELdEpQ4ygClyyuEInDWrcU3YDosOZdGDFRk9fKZ3izMZz0jNwoBFhxz0grSPkb3JOAzENtbDiqTG06dhKXcue7_UtYPsJ50zPo3G9H9jE2xK3VHMYCu-1rdDU-pv8K6awdFTO_-0?purpose=inline)

**项目 2：Enterprise RAG Agent**

中级

- PDF 知识库
- PostgreSQL 查询
- MCP 工具调用
- RAG 检索
- 人工审核

技术：LangGraph + FastAPI + pgvector

[Agents, Personal Guidance, and Memory: How We Think About Building FinCatch | FinCatch Blog | FinCatch](https://images.openai.com/static-rsc-4/DYezKedD-6qKhwcu4nL3PQLb92fQAUacbPLCsWr62AHdAOgW8wK5LKClRDqY_wgzpH65e059_8SyaNan8KQjEtR43lRIeNC04Bu3mHBAIw739QLAZH2cME2Ut-yJWnHjNmRODkekQB8XrExBZ097CGSQ8dWjUlGveqW-XveAMEc?purpose=inline)

**项目 3：Multi-Agent Financial Platform**

高级

- Research Agent
- Financial Analyst Agent
- Risk Agent
- Report Agent
- 状态管理和人工审批

技术：LangGraph + OpenAI + MCP + PostgreSQL

## **八、LangGraph 在 AI Engineer 技术栈中的位置**

**Frontend**

Next.js + React + TypeScript

**Backend**

Python + FastAPI

**LLM**

OpenAI + Claude + Gemini

**Agent Orchestration**

LangGraph + Tool Calling + MCP + Skills

**RAG**

LangChain + pgvector

**Database**

PostgreSQL + Redis

**Deployment**

Docker + AWS + LangSmith

## **九、最终学习建议**

如果你的目标是美国 AI Engineer / AI Application Developer，我建议：

1. 先学习 Python + FastAPI。
2. 掌握 OpenAI、Claude、Gemini API。
3. 学习 Tool Calling 和 RAG。
4. 学习 LangChain 基础。
5. 重点学习 LangGraph。
6. 再学习 MCP、Skills、Multi-Agent。
7. 最后掌握 Evaluation、Docker 和 AWS。

**LangGraph 最值得深入掌握的 5 个知识点：**

- State Management
- Conditional Routing
- Cyclic Workflow
- Checkpointing
- Human-in-the-loop

不要只会创建 Graph。要能够设计一个可以中断、恢复、追踪、评估并部署到生产环境的 Agent 系统。
