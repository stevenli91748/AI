# **LangChain 是什么？官方学习教程（2026）**

**LangChain 是一个开源的 LLM 应用开发框架，主要用于构建 AI 应用和 AI Agent。**

它帮助开发者把大语言模型、Prompt、外部工具、数据库、向量检索和业务逻辑连接起来，不需要每次都从零编写集成代码。

官方定位已经从早期的 Chain 框架发展为 **Agent Engineering Platform（AI Agent 工程开发平台）**。

[image](https://www.google.com/s2/favicons?domain=https://reference.langchain.com\&sz=32)

LangChain Reference+1



## **1. LangChain 能做什么？**

主要用于以下开发场景：

| 功能                | 用途                           |
| ----------------- | ---------------------------- |
| LLM Integration   | 接入 OpenAI、Claude、Gemini 等模型  |
| Prompt Templates  | 管理和设计提示词                     |
| Tool Calling      | 让 AI 调用 Python 函数或外部 API     |
| RAG               | 让 AI 检索企业知识库并回答问题            |
| Structured Output | 让 AI 输出符合 JSON Schema 的结构化数据 |
| Agent             | 构建可以自主选择工具、执行任务的 AI Agent    |
| Streaming         | 实现 AI 流式输出                   |
| Middleware        | 控制 Agent 执行过程和行为             |

例如，你可以用 LangChain 开发：

- 企业 AI 客服
- PDF 智能问答系统
- AI 金融分析助手
- SQL 数据库查询 Agent
- AI 自动化工作助手
- 多模型 AI 应用

## **2. LangChain 的核心架构**

[LangChain: Designing Real-World LLM Applications | by Koduru Meghana | Apr, 2026 | Medium](https://images.openai.com/static-rsc-4/-_slmjdrHNLl1WK970UCcRwWXsKigqS3tSwUmGbyEZwd7-5pJtaV3IX0X1IHCvLrzGCqa4kKiX3-l_-uhYJ_RKAkrB3RTOK5T7TencPunaMsTDp_SHMd8udLIMMz2rU9sANkoIgjqPHEjmtoO8ONwd0W2oHMHwERHrP9oJvKRKs?purpose=inline)

[medium.com](https://medium.com/%40kodurumeghana3/langchain-designing-real-world-llm-applications-cd36f9433090?utm_source=chatgpt.com)

建议先掌握这几个核心模块：

1. **Models**：连接不同 LLM。
2. **Messages**：管理 System、Human、AI、Tool 消息。
3. **Prompts**：构建提示词模板。
4. **Tools**：定义 AI 可以调用的工具。
5. **Agents**：让模型根据任务决定调用什么工具。
6. **Retrieval**：实现 RAG 知识检索。
7. **Middleware**：扩展和控制 Agent 行为。

## **3. LangChain、LangGraph、LangSmith 有什么区别？**

这三个经常一起使用，但职责不同。

应用开发

**LangChain**

快速开发 LLM 应用、工具调用和 Agent。

流程编排

**LangGraph**

管理复杂 Agent 工作流、状态、循环、持久化和人工审核。

监控评估

**LangSmith**

调试、追踪、评估和监控 AI 应用。

官方建议：简单 Agent 可以先用 LangChain；需要精细控制复杂流程时使用 LangGraph。LangChain 的 Agent 底层使用 LangGraph。

[image](https://www.google.com/s2/favicons?domain=https://reference.langchain.com\&sz=32)

LangChain Reference+1



## **4. 2026 官方学习资源**

以下是我建议优先收藏的官方资料。

[image](https://www.google.com/s2/favicons?domain=https://docs.langchain.com\&sz=32)

**1. LangChain 官方文档**

必学

核心概念、教程、模型、Tools、Agents、RAG。

[Python 官方教程](https://docs.langchain.com/oss/python/langchain/overview?utm_source=chatgpt.com)

[image](https://www.google.com/s2/favicons?domain=https://academy.langchain.com\&sz=32)

**2. LangChain Academy**

必学

官方免费课程，适合循序渐进地学习和实战。

[进入官方 Academy](https://academy.langchain.com/?utm_source=chatgpt.com)

[image](https://www.google.com/s2/favicons?domain=https://github.com\&sz=32)

**3. GitHub 源代码**

阅读源码、学习实际项目、练习代码。

[LangChain GitHub](https://github.com/langchain-ai/langchain?utm_source=chatgpt.com)

**4. 官方实战教程**

包括 RAG、SQL Agent、语义搜索和语音 Agent。

[LangChain Learn Tutorials](https://docs.langchain.com/oss/python/learn?utm_source=chatgpt.com)

**5. API Reference**

查询类、方法和参数。

[Python API Reference](https://reference.langchain.com/python/?utm_source=chatgpt.com)

**6. LangChain.js**

如果使用 Next.js、TypeScript，可以学习 JavaScript 版本。

[JavaScript 官方文档](https://docs.langchain.com/oss/javascript/langchain/overview?utm_source=chatgpt.com)

## **5. 安装与第一个 LangChain 程序**

建议使用 Python 学习。

**第一步：安装**

```
pip install -U langchain langchain-openai
```

**第二步：配置 API Key**

```
export OPENAI_API_KEY="你的API_KEY"
```

Windows PowerShell：

```
$env:OPENAI_API_KEY="你的API_KEY"
```

**第三步：运行程序**

```
from langchain.chat_models import init_chat_modelmodel = init_chat_model("openai:gpt-5.5")response = model.invoke("Explain what an AI Agent is.")print(response.content)
```

这是最基础的模型调用示例。实际使用时，需要根据所选模型配置对应的 Provider 集成包。

[image](https://www.google.com/s2/favicons?domain=https://github.com\&sz=32)

GitHub+1



## **6. 30 天学习路线**

| 时间        | 学习内容                        | 实战目标           |
| --------- | --------------------------- | -------------- |
| Day 1–5   | Models、Messages、Prompts     | AI Chatbot     |
| Day 6–10  | Tools、Function Calling      | 天气查询 Agent     |
| Day 11–15 | Embeddings、Vector Store、RAG | PDF 知识库        |
| Day 16–20 | Agents、Structured Output    | SQL Agent      |
| Day 21–25 | Middleware、Streaming        | 企业 AI 助手       |
| Day 26–30 | LangGraph、LangSmith         | 完整 AI Agent 项目 |

## **7. 建议完成的 3 个 GitHub 项目**

[Retrieval-Augmented Generation (RAG) with LangChain and Ollama | by Dennis Treder-Tschechlov | Medium](https://images.openai.com/static-rsc-4/CgCSjyDZNyK54CS_GuvbmQh-qJiinMemkplvYOg4ev3tFvaNHLez8oTI2hqq78cSViHg1hC6WPWp6hovRGAZcaGivKWlHebOf-RKmW6o50GyeWbkBhDNHEZxXfa9xOTXxIUAf8QrtYg7sBqS5P-Qq38S9dF4CVIG214qLxqmSYU?purpose=inline)

**项目一：AI PDF RAG**

上传 PDF，提取内容，向量检索，AI 回答并显示文档来源。

技术：LangChain + OpenAI + PostgreSQL + pgvector + FastAPI

[OpenBB Platform — built with AI on Blink](https://images.openai.com/static-rsc-4/h9eiLV1ciuRrmWPUnaGvv6S23NZa8zqLXhrsFuCM5iDPG7AOXCwKwx9mK0SMy6MsZu5YgOYYFZEOsl2RBXffk8Pa8vSRBS7C9kbobNatHzGeM6RqDOOLD_goHID7UzkBct-KU3kUaLkpJPqwnKKgNt5HN9Q8knR8XLhS39d5QB0?purpose=inline)

**项目二：AI 股票研究 Agent**

查询股票数据、分析财报、整理新闻、生成风险报告。

技术：LangChain + Market Data API + Tools + FastAPI

[Our Products | Vortex - Smartify AI & PakkaHisab](https://images.openai.com/static-rsc-4/jqLWNKehVK-I8jCG3KL_BKuUypMdlZYahE8BVVweyQsPIo6pKOwgoml691DK1t7vP9Oo6DOWG7V9eeyQILz-YIZt2d024z82-0fsOge8iZGm3I7yLflJ8h51R2TVOICKh3wMiUEnVvYYrxiESetxu6JfOe--JVQyq4UqqSU5bu4?purpose=inline)

**项目三：Enterprise AI Agent**

企业知识库问答、数据库查询、外部 API 调用、人工审批。

技术：LangChain + LangGraph + MCP + PostgreSQL + AWS

## **8. 2026 AI Engineer 应该怎么学？**

我的建议是按照这个顺序：

1. **Python + FastAPI**

   掌握后端开发基础。
2. **LLM API + LangChain**

   掌握模型集成、Prompt、Tool Calling。
3. **RAG + Vector Database**

   掌握企业知识库开发。
4. **LangGraph + MCP + Skills**

   掌握复杂 Agent 系统开发。
5. **AWS + Docker + PostgreSQL**

   掌握部署和生产环境。
6. **LangSmith + Evaluation**

   掌握调试、评估和质量监控。

**最重要的建议：** 不要只学习 LangChain API。美国 AI Engineer 求职更需要你能够独立完成一个真实的 LLM 应用，包括 RAG、Agent、数据库、API、安全、部署和评估。

下一步建议学习 **LangChain 实战：从零开发一个带 RAG 和 Tool Calling 的 AI Agent**。
