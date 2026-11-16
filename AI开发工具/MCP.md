# **MCP 是什么？官方学习资源（2026）**

**MCP = Model Context Protocol（模型上下文协议）。**

MCP 是一种开放协议，由 Anthropic 于 2024 年推出，用于标准化 AI 应用与外部工具、数据源和服务之间的连接。

简单理解：

- LLM 是 AI 的大脑。
- Tool Calling 是 AI 调用工具的能力。
- MCP 是连接 AI 和外部工具、数据的标准协议。
- AI Agent 是利用这些能力完成任务的应用。

**MCP 最重要的价值：让不同 AI 应用可以通过统一协议连接不同工具，不必为每个 AI 应用重新开发一套集成方式。**

## **一、MCP 能做什么？**

例如，你开发一个企业 AI Assistant，希望它能够：

1. 读取本地 PDF 文件。
2. 查询 PostgreSQL 数据库。
3. 搜索 GitHub 代码。
4. 查询 Google Calendar。
5. 读取企业知识库。
6. 调用外部 REST API。

传统方式需要分别开发各种集成接口。

使用 MCP，可以让这些服务提供标准化的 MCP Server，再由支持 MCP 的 AI 应用连接。

[When AI Tools Turn Against You: Operationalizing MCP Server Security with the Splunk MCP TA | Splunk](https://images.openai.com/static-rsc-4/oaHbLWjGu8DaWKsX_lKOr-wnpfA4FJjiGxK6Xk2qHPIWqWXWoM0epxnZYegCUxd5eiXcdUGir43hvVXPiQXFCLcqCOndPJU0WYOKzQy8uPzvTjQIUbDmD6UXQcHLJfnUaV-ACu7yn1fFtDx9sYEwXCFKFYcYJQu8O3XfGaQOshw?purpose=inline)

[splunk.com](https://www.splunk.com/en_us/blog/security/securing-ai-agents-model-context-protocol.html?utm_source=chatgpt.com)

## **二、MCP 的核心架构**

MCP 有三个核心角色：

| 角色  | 英文     | 功能                      |
| --- | ------ | ----------------------- |
| 主机  | Host   | AI 应用，例如 Claude Desktop |
| 客户端 | Client | 负责 MCP 协议通信             |
| 服务端 | Server | 提供工具和数据能力               |

工作关系：

**MCP Host**

Claude / VS Code / 自己开发的 AI Agent

MCP Client

**MCP Protocol**

标准化通信协议 · JSON-RPC

**MCP Server 1**

Database

**MCP Server 2**

GitHub

**MCP Server 3**

Filesystem

例如，VS Code 可以作为 MCP Host，连接 GitHub MCP Server 和数据库 MCP Server。每个 Server 由对应的 MCP Client 负责通信。

[image](https://www.google.com/s2/favicons?domain=https://github.com\&sz=32)

GitHub+1



## **三、MCP 最重要的三个核心功能**

这是学习 MCP 必须理解的内容。

| 功能  | 英文        | 作用             |
| --- | --------- | -------------- |
| 工具  | Tools     | 执行操作，例如查询数据库   |
| 资源  | Resources | 提供上下文数据，例如读取文件 |
| 提示词 | Prompts   | 提供可复用的提示词模板    |

举例：

**Tools**

- `get_stock_price`
- `search_database`
- `send_email`

**Resources**

- `file://company/policy.pdf`
- 数据库 Schema
- 企业文档

**Prompts**

- 生成财务报告
- 分析股票
- 总结会议记录

注意：Tools 通常由模型根据上下文选择调用；Resources 主要由应用程序获取和提供；Prompts 通常由用户选择使用。

[image](https://www.google.com/s2/favicons?domain=https://github.com\&sz=32)

GitHub+1



## **四、MCP 通信方式**

主要学习两种：

| 通信方式            | 用途               | 学习优先级 |
| --------------- | ---------------- | ----- |
| STDIO           | 本地 MCP Server 通信 | 必须    |
| Streamable HTTP | 远程 MCP Server 通信 | 必须    |
| HTTP + SSE      | 旧式通信方式           | 了解即可  |

2026 年官方规范以 Streamable HTTP 和 STDIO 为主要传输方式。新项目优先学习这两种，不建议从旧的 HTTP + SSE 开始。

[image](https://www.google.com/s2/favicons?domain=https://github.com\&sz=32)

GitHub+1



## **五、MCP 官方学习资源（2026）**

以下是建议收藏的官方资料。

[MCP Icons, Logos, Symbols - Free Download PNG and SVG](https://images.openai.com/static-rsc-4/MJ3ZSnDJBvyGunpjHJyFvnbpIwRet3cgBQpouWa6A7rvbJunawAi6xy8gVTkFsP9A1blR8NQlmP4xXBJt0tnRVDUVpY3t5tIx1SPUTZGCE0EyCGR0AuNSvj9RsAhaJGMIHquQYBAzA1nzwVN7WUEru981ykioC_KvzXLUX8uJJA?purpose=inline)

**1. MCP 官方网站**

必学

[modelcontextprotocol.io](https://modelcontextprotocol.io/?utm_source=chatgpt.com)

**2. MCP 官方入门教程**

[Getting Started](https://modelcontextprotocol.io/docs/getting-started/intro?utm_source=chatgpt.com)

**3. MCP 官方协议规范**

[MCP Specification](https://modelcontextprotocol.io/specification/2026-07-28?utm_source=chatgpt.com)

2026 年 7 月 28 日规范版本，学习时注意版本兼容性。

**4. MCP 官方架构说明**

[Architecture Overview](https://github.com/modelcontextprotocol/modelcontextprotocol/blob/main/docs/docs/2026-07-28/learn/architecture.mdx?utm_source=chatgpt.com)

**5. MCP 官方 Python SDK**

[Python SDK GitHub](https://github.com/modelcontextprotocol/python-sdk?utm_source=chatgpt.com)

**6. MCP 官方 TypeScript SDK**

[TypeScript SDK GitHub](https://github.com/modelcontextprotocol/typescript-sdk?utm_source=chatgpt.com)

**7. MCP Inspector**

[MCP Inspector GitHub](https://github.com/modelcontextprotocol/inspector?utm_source=chatgpt.com)

用于测试、调试 MCP Server 和 MCP 工具。

**8. MCP 官方服务器示例**

[MCP Servers GitHub](https://github.com/modelcontextprotocol/servers?utm_source=chatgpt.com)

## **六、Python 实战：创建第一个 MCP Server**

建议先使用 Python SDK。

**第一步：安装**

```
pip install "mcp[cli]"
```

**第二步：创建 server.py**

```
from mcp.server.fastmcp import FastMCPmcp = FastMCP("My AI Server")@mcp.tool()def add(a: int, b: int) -> int:    """计算两个数字的和"""    return a + b@mcp.resource("info://company")def company_info() -> str:    return "Company AI Knowledge Base"if __name__ == "__main__":    mcp.run(transport="stdio")
```

**第三步：运行**

```
python server.py
```

这样就创建了一个简单的 MCP Server，提供：

- 一个 Tool：`add`
- 一个 Resource：`info://company`

接下来可以使用 MCP Inspector 连接和测试。

注意：这是一个入门示例。实际连接 AI Host 时，需要配置客户端启动方式和通信参数。

## **七、MCP 和 Tool Calling 有什么区别？**

这是美国 AI Engineer 面试值得掌握的问题。

| 比较         | Tool Calling | MCP           |
| ---------- | ------------ | ------------- |
| 本质         | 模型调用工具的机制    | 标准化通信协议       |
| 主要作用       | 让模型选择工具      | 连接 AI 应用与工具服务 |
| 是否依赖 LLM   | 通常是          | 不一定           |
| 是否标准化跨平台连接 | 不统一          | 是             |
| 能否连接数据库    | 可以           | 可以            |
| 能否连接外部 API | 可以           | 可以            |

举个例子：

- Tool Calling：GPT 决定调用 `search_github()`。
- MCP：通过 GitHub MCP Server 提供标准化的 GitHub 工具。
- Agent：根据用户任务，决定是否搜索 GitHub、读取代码、修改代码。

**三者是互补关系，不是相互替代。**

## **八、30 天 MCP 学习计划**

| 时间        | 学习内容                      | 实战目标                      |
| --------- | ------------------------- | ------------------------- |
| Day 1–3   | MCP 基本原理、架构               | 理解 Host / Client / Server |
| Day 4–6   | Tools、Resources、Prompts   | 理解三个核心功能                  |
| Day 7–10  | Python MCP SDK            | 创建 MCP Server             |
| Day 11–13 | MCP Client                | 创建客户端                     |
| Day 14–16 | STDIO                     | 本地连接                      |
| Day 17–19 | Streamable HTTP           | 远程连接                      |
| Day 20–22 | Authentication / Security | 权限管理                      |
| Day 23–25 | FastAPI + MCP             | 集成后端                      |
| Day 26–27 | LangGraph + MCP           | Agent 调用 MCP              |
| Day 28–30 | Docker + AWS              | 部署 MCP Server             |

## **九、建议完成的 3 个 GitHub 项目**

[GitHub - dhanababum/supermcp: 🚀 SuperMCP - Create multiple isolated MCP servers using a single connector. Build powerful Model Context Protocol integrations for databases (PostgreSQL, MSSQL) with FastAPI backend, React dashboard, and token-based auth. Perfect for multi-tenant apps and AI assistants. · GitHub](https://images.openai.com/static-rsc-4/VvH7ZzYlsYwCPky2NsYvyBau0SF5lZLo-aLwe1ji2pJM0ryt87_ePphzzLttAwLFlq7N7quVhHHL2kHWhdSc8MsAM7_0b8zw2GlEX7T8hByPHBOmizUviSXyBMbzRzepIaf89nWd4W_SQbqGYdeMHQovaThkmoIpIwPMKKj3zaE?purpose=inline)

**项目 1：PostgreSQL MCP Server**

初级

- 查询数据库
- 获取数据库 Schema
- 执行受限 SQL
- Python MCP SDK

[GitHub AI · AI built into every step of your workflow · GitHub](https://images.openai.com/static-rsc-4/VXOJxXHmQG6rxlOToQgttOaKAZmQX8UhWmbNI7qSlBvWWHNA70yBzP-z3_7GqlZ39mtL1BsaTmaAiPnoMbWLLQwS-lc-6yqAd8z2ysapN93fXV362ihmghOruYU6w3Z2Y3LrNyTiO9HA3sWHy-8OlgG1sO2Ph48RBFcX46GTsNs?purpose=inline)

**项目 2：GitHub MCP Assistant**

中级

- 搜索 GitHub Repository
- 查询 Issues
- 分析 Pull Requests
- AI 代码助手

[ImpireX | AI Agents](https://images.openai.com/static-rsc-4/4DZ2TbL0Nn3ReiRFbSrgtWaKNb79E-Wtea_l_IbA98h_YjKhlfy1O5fRKZ0MwTqrWc0Ssb4OT2RTyUullg7rpaqSLtMyFKGS6r5OE-BRGpKpjzEjY-oKw75P4smxDa53l7Ntvakkw70gk-XUeSS5vh0q7EP1AW94YqG4xI5PKf0?purpose=inline)

**项目 3：Enterprise MCP Agent Platform**

高级

- 多个 MCP Server
- 多模型调用
- RAG 知识库
- LangGraph Agent
- 权限和人工审批

## **十、美国 AI Engineer 推荐学习顺序**

结合你正在学习的 FastAPI、Next.js、PostgreSQL、LLM API 和 RAG，我建议采用以下顺序：

1. Python + FastAPI
2. PostgreSQL + SQLAlchemy
3. OpenAI / Claude / Gemini API
4. Prompt Engineering + Structured Outputs
5. Tool Calling / Function Calling
6. RAG + pgvector
7. **MCP Server + MCP Client**
8. LangChain + LangGraph
9. AI Agent + Multi-Agent
10. Docker + AWS + CI/CD

最重要的建议

不要只会使用 MCP Server，还要能够自己开发：

1. Python MCP Server
2. MCP Client
3. Remote MCP Server
4. MCP Authentication
5. MCP + LangGraph Agent

这五项能力能帮助你从普通 LLM API 开发进一步走向 AI Agent 工程开发。
