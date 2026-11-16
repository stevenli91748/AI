# **LangSmith 是什么？官方学习教程（2026）**

**LangSmith 是一个 AI 应用和 Agent 的调试、测试、评估、监控与部署平台。**

简单理解：

- LangChain：负责开发 AI 应用。
- LangGraph：负责编排复杂 Agent 工作流。
- LangSmith：负责检查 AI 是否正常工作、回答质量是否合格，以及上线后如何持续改进。

它由 LangChain 团队开发，但**不要求必须使用 LangChain**，也可以监控 LangGraph、其他 Agent 框架或自己编写的 AI 应用。

[image](https://www.google.com/s2/favicons?domain=https://www.langchain.com\&sz=32)

LangChain+1



## **1. LangSmith 主要解决什么问题？**

假设你开发了一个 AI 客服 Agent：

用户问：「我的订单为什么没有发货？」

Agent 执行：

1. 调用 OpenAI 模型。
2. 查询 PostgreSQL 数据库。
3. 检索订单信息。
4. 调用物流 API。
5. 生成回答。

如果 AI 回答错误，你需要知道：

- 是模型理解错误？
- 是数据库查询错误？
- 是 RAG 检索错误？
- 是 Tool Calling 调用失败？
- 是 Prompt 设计不合理？
- 是模型成本太高、响应太慢？

LangSmith 可以把 Agent 执行过程记录下来，方便逐步排查。

[image](https://www.google.com/s2/favicons?domain=https://www.langchain.com\&sz=32)

LangChain+1



## **2. LangSmith 六大核心功能**

[LangSmith：LLM 可观测性平台 | LearnGraph.online](https://images.openai.com/static-rsc-4/v8Y1kvR-OfpOtfg6v1sybxTzmsMuYSVAOZFEB1aXEdsvR_o4KySmx1z1mgtqbp_yzdpmRE_OpRfG4rLP9ZBLX10yH6tlqhpOPzDfv6Mt6B00WIU-CpRdoV9igBJ6xGfIO32-IpUD883FjzL8v_J236JnjVt4znZUsx90GCWfFds?purpose=inline)

**1. Tracing（执行追踪）**

记录每次 LLM 调用、Prompt、工具调用、检索结果、执行时间和错误。

[使用 LangSmith 运行 SWE-bench | 🦜️🛠️ LangSmith 教程](https://images.openai.com/static-rsc-4/mwuUl25Xw-HW91Cn5m-OlCmLnQQv9WN243e9J8WoC5IRrVMx5VpF82Y4JwJvNKnIoDvsVD2514yTT5GwLBqR6kZUKtfTkyLvNWPhJk4M-DH-DpZ3iNncR8CT2d9466vQCdJ4XV9EsrZHAIexggMD59cPr9_hKIvahpF0f9xlMGY?purpose=inline)

**2. Evaluation（质量评估）**

测试 AI 回答是否准确、是否符合要求、RAG 是否检索到正确内容。

[Create and manage datasets in the UI - Docs by LangChain](https://images.openai.com/static-rsc-4/6VUIoxtGXC_Ir9hxyTCxSZRSojEIsgT4X2EIJ2Ry_64RpRpj8kiAI5MtzUmCCpXKkd4xlQ1gPJ0lvbzdwMClOlHAsLfbsRVCkTNwtvbgU1QYbsTCL-vkCH6XZde1JTI-xGEBrQ0qYzKNfH34NSna_LnRie5rT1jY7FE7HTvtCJk?purpose=inline)

**3. Datasets（测试数据集）**

创建标准问题和参考答案，用于重复测试 AI。

[更新提示 | 🦜️🛠️ LangSmith 教程](https://images.openai.com/static-rsc-4/aATrZZJHvWt0pe0Nu0nm40XBnDwlmob5GHldFAldSU2uG6LFHSkmPI8ur04qXU5eqmvX9L1lEcRGUZEHcdo__U4jTrnTQu1Ck2F0W_GcrV7EWr4lodkwl6MA3GTo4NX-r99dU8DyY6nqYwcs0or4p3zyphQdy9nagz_f1iz_zyc?purpose=inline)

**4. Prompt Management**

管理 Prompt 版本，比较不同 Prompt 和模型的输出效果。

[LangSmith: Production Monitoring & Automations](https://images.openai.com/static-rsc-4/bj01O6RKdrxjoLavKd3h5ExLIAz6cU4qU9nTIq8nCG8zLIlDUwaD6x7FaipAiPbvSdZJ_UExHMESc1WUzHeZQRYi4_OLt5jGGZlRO6Z7vbY7RL0DeJa15Eo8t8uNV53KYN4kNVXa58XD7GwgwawLHzS83v5VhVhZ_4YhJpgr85M?purpose=inline)

**5. Monitoring（生产监控）**

监控 AI 应用的调用量、错误率、延迟、成本和回答质量。

[LangSmith: LangChain's LLM Debugger, Evaluator, & Monitoring Tool](https://images.openai.com/static-rsc-4/cYi30N2in4fugLAdjBZNVG_RFb_9-X7DQOYs3V2I_KAMyqBrDXhBcPaM8AOXxckRIdlwpAL0-jwwjnBmz4TZxRnLRCYHWPB_ic6NsotNNN3FzvdPEKqArBMC6EgV2eUSq7PpK2FhY_9sfo10h0H18i__GclVSTECdhIRHlw_yoM?purpose=inline)

**6. Deployment（部署）**

提供 Agent 部署和运行管理能力，支持生产环境工作流。

[image](https://www.google.com/s2/favicons?domain=https://www.langchain.com\&sz=32)

LangChain+2

## **3. LangSmith 官方学习资源（2026）**

以下是官方入口：

[image](https://www.google.com/s2/favicons?domain=https://docs.langchain.com\&sz=32)

**1. LangSmith 官方文档**

必学

[LangSmith Overview](https://docs.langchain.com/langsmith/overview?utm_source=chatgpt.com)

**2. Tracing 官方教程**

学习如何追踪 AI 模型和 Agent 的执行过程。

[Observability Documentation](https://docs.langchain.com/langsmith/observability?utm_source=chatgpt.com)

**3. Evaluation 官方教程**

学习数据集、评估器、准确率和回归测试。

[Evaluation Documentation](https://docs.langchain.com/langsmith/evaluation?utm_source=chatgpt.com)

**4. Python SDK**

使用 Python 编程方式记录和管理 Trace。

[Trace with LangChain](https://docs.langchain.com/langsmith/trace-with-langchain?utm_source=chatgpt.com)

**5. LangSmith 官方网站**

[LangSmith Platform](https://www.langchain.com/langsmith-platform?utm_source=chatgpt.com)

**6. 注册与控制台**

[LangSmith Dashboard](https://smith.langchain.com/?utm_source=chatgpt.com)

**7. 官方 GitHub**

[LangChain GitHub Organization](https://github.com/langchain-ai?utm_source=chatgpt.com)

## **4. 第一个 LangSmith 实战：追踪 AI 调用**

**第一步：安装**

```
pip install -U langchain langchain-openai
```

**第二步：配置环境变量**

```
export OPENAI_API_KEY="your-openai-key"
export LANGSMITH_API_KEY="your-langsmith-key"
export LANGSMITH_TRACING="true"
export LANGSMITH_PROJECT="my-first-ai-agent"
```

Windows PowerShell：

```
$env:LANGSMITH_TRACING="true"
$env:LANGSMITH_API_KEY="your-langsmith-key"
$env:LANGSMITH_PROJECT="my-first-ai-agent"
```

**第三步：编写 Python 程序**

```
from langchain.chat_models import init_chat_modelmodel = init_chat_model("openai:gpt-4.1-mini")response = model.invoke(    "Explain how RAG works.")print(response.content)
```

**第四步：查看执行记录**

打开 LangSmith Dashboard：

[https://smith.langchain.com/](https://smith.langchain.com/?utm_source=chatgpt.com)

找到项目 `my-first-ai-agent`，查看：

- 模型输入和输出
- Token 使用情况
- 调用耗时
- 模型执行错误
- 每次调用的 Trace

以上示例通过 LangChain 自动追踪模型调用。

[image](https://www.google.com/s2/favicons?domain=https://docs.langchain.com\&sz=32)

Docs by LangChain+1



## **5. Offline Evaluation 和 Online Evaluation**

这是 LangSmith 非常重要的两个概念。

| 类型                 | 用途           | 时间  |
| ------------------ | ------------ | --- |
| Offline Evaluation | 使用标准测试集测试 AI | 上线前 |
| Online Evaluation  | 对真实用户请求持续评分  | 上线后 |

例如，你准备了 100 道企业知识库问题：

- AI 回答正确率是否达到 90%？
- 是否引用了正确的文档？
- 是否出现幻觉？
- 更换模型后效果有没有下降？

LangSmith 可以使用代码评估、LLM-as-a-judge 和人工评估来检查这些问题。

[image](https://www.google.com/s2/favicons?domain=https://docs.langchain.com\&sz=32)

Docs by LangChain+1



## **6. 30 天学习计划**

| 时间        | 学习内容                         | 实战            |
| --------- | ---------------------------- | ------------- |
| Day 1–5   | LangSmith、Tracing            | 追踪 OpenAI API |
| Day 6–10  | Projects、Runs、Threads        | 分析 Agent 执行过程 |
| Day 11–15 | Dataset、Evaluation           | 建立 100 条测试数据  |
| Day 16–20 | LLM-as-a-Judge               | 自动评估回答质量      |
| Day 21–25 | Online Evaluation、Monitoring | 监控生产环境        |
| Day 26–30 | LangGraph + LangSmith        | 完整 Agent 项目   |

## **7. LangSmith 在 AI Engineer 技术栈中的位置**

**AI Application**

FastAPI / Next.js / Python

**LangChain**

LLM / Tools / RAG

**LangGraph**

Agent Workflow

**LangSmith**

Tracing / Evaluation / Monitoring / Deployment

**AWS / Docker / PostgreSQL**

Infrastructure / Database / Deployment

## **8. 是否值得学习？**

建议学习

我的建议：

1. LangChain：先学会开发 AI 应用。
2. LangGraph：再学会开发复杂 Agent。
3. LangSmith：最后学习测试、调试和生产监控。

**特别注意：** LangSmith 不只是 LangChain 的调试工具，它支持不同框架。实际企业项目中，Trace、Evaluation 和生产监控都是很有价值的工程能力。涉及客户数据时，还要注意脱敏、访问权限和数据存储要求。

官方介绍：[What is LangSmith?](https://www.langchain.com/resources/what-is-langsmith?utm_source=chatgpt.com)。↳

下一步最值得做的是：用 **FastAPI + LangChain + LangGraph + LangSmith + PostgreSQL + AWS** 开发一个完整的企业级 AI Agent 项目。
