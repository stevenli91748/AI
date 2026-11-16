# **Tool Calling 是什么？官方学习资源（2026）**

**Tool Calling（工具调用），也叫 Function Calling（函数调用），是让 LLM 能够调用外部工具、API、数据库和程序的技术。**

简单理解：

普通 LLM 只能根据输入生成文字；加入 Tool Calling 后，AI 可以决定什么时候调用外部工具，由你的程序执行操作，再把结果交给 AI 生成最终答案。

这是开发 **AI Agent（智能体）必须掌握的核心技术**。

## **一、Tool Calling 能做什么？**

例如，你开发一个 AI 助手，用户说：

> 帮我查询今天的天气，并计算 100 美元兑换多少人民币。

AI 可以调用两个工具：

1. `get_weather()`：查询天气 API。
2. `convert_currency()`：调用汇率 API。

AI 获得结果后，再组织成自然语言回答。

其他典型用途：

| Tool Calling 应用 | 调用的工具                  |
| --------------- | ---------------------- |
| 查询天气            | Weather API            |
| 查询股票价格          | Financial API          |
| 查询用户资料          | PostgreSQL             |
| 发送电子邮件          | Gmail API              |
| 搜索企业文档          | RAG                    |
| 预订会议            | Calendar API           |
| 生成报表            | Python                 |
| 操作网页            | Browser / Computer Use |

## **二、Tool Calling 工作原理**

[Connecting LLMs to the Real World: Tool Use, Function Calling, and MCP](https://images.openai.com/static-rsc-4/m-GfkM7lSvSk1PsCwspjca43skkp2SUdttp40Yb7mKHg6SVU26M5NTFsmLvExrgqjTXbIVuAVLwlxD34NYrIHgbgscQKT0U53wS1peFThiwCbWICFg5Q7rCvVU9lmtIWpvQ4XNntCF49kN4QkZTY1tYDVmU4FxlfMRrttWZXA10?purpose=inline)

[blog.bytebytego.com](https://blog.bytebytego.com/p/connecting-llms-to-the-real-world?utm_source=chatgpt.com)

标准流程分为 5 步：

1. **用户提出问题**

   例如：查询苹果公司当前股价。
2. **LLM 判断需要调用工具**

   模型选择 `get_stock_price`，并生成参数 `AAPL`。
3. **应用程序执行函数**

   FastAPI 调用股票数据 API。
4. **返回工具执行结果**

   将股价数据返回给 LLM。
5. **LLM 生成最终答案**

   AI 根据返回的数据回答用户。

**关键概念：LLM 通常不直接执行你的 Python 函数。它只是生成结构化的调用请求，真正执行函数的是你的应用程序。**&#x20;

[image](https://www.google.com/s2/favicons?domain=https://developers.openai.com\&sz=32)

OpenAI API+2



## **三、Tool Calling 和 Function Calling 的区别**

这两个名称在大多数 LLM 开发场景中可以视为同一类技术。

| 名称               | 含义                    |
| ---------------- | --------------------- |
| Tool Calling     | 工具调用，范围更广             |
| Function Calling | 函数调用，通常通过函数 Schema 定义 |
| API Calling      | 应用程序调用外部 API          |
| MCP              | 标准化连接 AI 与外部工具、数据的协议  |
| AI Agent         | 能够规划任务并使用工具完成工作的系统    |

例如：

- Function Calling：让 GPT 调用 `get_stock_price()`。
- MCP：让 AI 通过标准协议连接股票服务。
- Agent：AI 自主判断何时查询股票、分析数据和生成报告。

## **四、主要 LLM 厂商的 Tool Calling**

这 5 家值得重点学习。

| 平台               | 官方技术名称           | 官方资源                                                                                                      |
| ---------------- | ---------------- | --------------------------------------------------------------------------------------------------------- |
| OpenAI           | Function Calling | [官方教程](https://developers.openai.com/api/docs/guides/function-calling?utm_source=chatgpt.com)             |
| Anthropic Claude | Tool Use         | [官方教程](https://platform.claude.com/docs/en/agents-and-tools/tool-use/overview?utm_source=chatgpt.com)     |
| Google Gemini    | Function Calling | [官方教程](https://ai.google.dev/gemini-api/docs/function-calling?hl=en\&utm_source=chatgpt.com)              |
| LangChain        | Tool Calling     | [官方教程](https://github.com/langchain-ai/docs/blob/main/src/oss/langchain/tools.mdx?utm_source=chatgpt.com) |
| DeepSeek         | Tool Calls       | [官方教程](https://api-docs.deepseek.com/guides/tool_calls?utm_source=chatgpt.com)                            |

特别推荐先学习 OpenAI、Claude 和 Gemini 的原生实现，再学习 LangChain 的统一工具接口。

## **五、Python 实战：自己写一个 Tool Calling**

使用 Python + OpenAI API。

**第一步：定义一个工具**

```
def get_weather(city: str):    return {        "city": city,        "temperature": 25,        "weather": "Sunny"    }
```

**第二步：定义工具 Schema**

```
tools = [{    "type": "function",    "name": "get_weather",    "description": "查询指定城市的天气",    "parameters": {        "type": "object",        "properties": {            "city": {                "type": "string",                "description": "城市名称"            }        },        "required": ["city"],        "additionalProperties": False    },    "strict": True}]
```

**第三步：发送给 OpenAI**

```
from openai import OpenAIclient = OpenAI()response = client.responses.create(    model="YOUR_SUPPORTED_MODEL",    input="查询洛杉矶天气",    tools=tools)for item in response.output:    if item.type == "function_call":        print(item.name)        print(item.arguments)
```

**第四步：应用程序执行函数**

```
import jsonfor item in response.output:    if item.type == "function_call":        args = json.loads(item.arguments)        if item.name == "get_weather":            result = get_weather(**args)            print(result)
```

这里展示的是核心流程。完整实现还要把函数执行结果通过 `function_call_output` 和对应的 `call_id` 发送回模型，让模型生成最终答案。

[image](https://www.google.com/s2/favicons?domain=https://developers.openai.com\&sz=32)

OpenAI API



注意：生产环境必须校验参数、限制工具权限，并对发送邮件、转账、删除数据等有副作用的操作设置授权确认。

## **六、Tool Calling 必须掌握的技术**

| 技术                    | 学习内容          | 优先级 |
| --------------------- | ------------- | --- |
| JSON Schema           | 定义工具参数        | 必须  |
| Pydantic              | Python 参数验证   | 必须  |
| Function Calling      | 模型调用函数        | 必须  |
| Tool Execution        | 执行 Python 函数  | 必须  |
| Tool Result           | 返回执行结果        | 必须  |
| Parallel Tool Calling | 并行调用多个工具      | 高   |
| Error Handling        | 错误处理和重试       | 必须  |
| Async Tools           | 异步工具调用        | 高   |
| Tool Permissions      | 工具权限管理        | 必须  |
| MCP                   | 标准化工具连接       | 高   |
| LangGraph             | 多步骤 Agent 工作流 | 高   |

## **七、Tool Calling 官方学习资源**

**LLM 原生 API**

- [OpenAI Function Calling](https://developers.openai.com/api/docs/guides/function-calling?utm_source=chatgpt.com)
- [Anthropic Tool Use](https://platform.claude.com/docs/en/agents-and-tools/tool-use/overview?utm_source=chatgpt.com)
- [Google Gemini Function Calling](https://ai.google.dev/gemini-api/docs/function-calling?hl=en\&utm_source=chatgpt.com)

  **Agent 开发框架**
- [LangChain Tools](https://github.com/langchain-ai/docs/blob/main/src/oss/langchain/tools.mdx?utm_source=chatgpt.com)
- [LangGraph 官方文档](https://docs.langchain.com/oss/python/langgraph/overview?utm_source=chatgpt.com)
- [OpenAI Agents SDK](https://openai.github.io/openai-agents-python/?utm_source=chatgpt.com)

  **MCP**
- [MCP 官方文档](https://modelcontextprotocol.io/docs/getting-started/intro?utm_source=chatgpt.com)
- [MCP Protocol Specification](https://modelcontextprotocol.io/specification/2025-11-25?utm_source=chatgpt.com)

  **Python 基础**
- [Pydantic 官方文档](https://docs.pydantic.dev/latest/?utm_source=chatgpt.com)
- [FastAPI 官方文档](https://fastapi.tiangolo.com/?utm_source=chatgpt.com)

## **八、30 天 Tool Calling 学习计划**

| 时间        | 学习任务                      |
| --------- | ------------------------- |
| Day 1–3   | JSON、JSON Schema、Pydantic |
| Day 4–6   | OpenAI Function Calling   |
| Day 7–9   | Python Function Execution |
| Day 10–12 | Claude Tool Use           |
| Day 13–15 | Gemini Function Calling   |
| Day 16–18 | Parallel Tool Calling     |
| Day 19–21 | FastAPI + Tool Calling    |
| Day 22–24 | LangChain Tools           |
| Day 25–26 | LangGraph                 |
| Day 27–28 | MCP                       |
| Day 29–30 | Docker + AWS 部署           |

## **九、建议做的 3 个 GitHub 实战项目**

[OpenBB Platform — built with AI on Blink](https://images.openai.com/static-rsc-4/h9eiLV1ciuRrmWPUnaGvv6S23NZa8zqLXhrsFuCM5iDPG7AOXCwKwx9mK0SMy6MsZu5YgOYYFZEOsl2RBXffk8Pa8vSRBS7C9kbobNatHzGeM6RqDOOLD_goHID7UzkBct-KU3kUaLkpJPqwnKKgNt5HN9Q8knR8XLhS39d5QB0?purpose=inline)

**项目 1：AI Financial Assistant**

初级

- 查询股票价格
- 查询财务数据
- 计算投资收益
- 调用多个 API

技术：OpenAI + Python + FastAPI

[AI Internal Knowledge Search by Mohammed TAYOR on Dribbble](https://images.openai.com/static-rsc-4/UQmigjAZukVk01CB-45P5nBMldyJGulBRvGELdEpQ4ygClyyuEInDWrcU3YDosOZdGDFRk9fKZ3izMZz0jNwoBFhxz0grSPkb3JOAzENtbDiqTG06dhKXcue7_UtYPsJ50zPo3G9H9jE2xK3VHMYCu-1rdDU-pv8K6awdFTO_-0?purpose=inline)

**项目 2：Enterprise AI Assistant**

中级

- 查询 PostgreSQL
- 搜索 RAG 知识库
- 发送邮件
- 调用企业内部 API

技术：LangChain + RAG + MCP

[ImpireX | AI Agents](https://images.openai.com/static-rsc-4/4DZ2TbL0Nn3ReiRFbSrgtWaKNb79E-Wtea_l_IbA98h_YjKhlfy1O5fRKZ0MwTqrWc0Ssb4OT2RTyUullg7rpaqSLtMyFKGS6r5OE-BRGpKpjzEjY-oKw75P4smxDa53l7Ntvakkw70gk-XUeSS5vh0q7EP1AW94YqG4xI5PKf0?purpose=inline)

**项目 3：Multi-Agent Platform**

高级

- 多 Agent 协作
- 自动选择工具
- 并行任务执行
- 人工审批
- 工作流管理

技术：LangGraph + OpenAI Agents SDK + FastAPI

## **十、AI Engineer 学习路线中的位置**

建议按这个顺序掌握：

1. Python + FastAPI
2. LLM API（OpenAI、Claude、Gemini）
3. Prompt Engineering
4. Structured Outputs + Tool Calling
5. RAG + Vector Database
6. MCP
7. LangGraph + AI Agent
8. Multi-Agent Systems
9. Docker + AWS + Production Deployment

**我的建议：** Tool Calling 是从普通 LLM 应用迈向 AI Agent 开发的关键一步。先掌握原生 Function Calling，再学习 MCP 和 LangGraph，不要一开始就跳到 Multi-Agent。

你最终应该能够独立开发一个可以查询数据库、调用外部 API、搜索知识库并执行任务的 AI Agent。
