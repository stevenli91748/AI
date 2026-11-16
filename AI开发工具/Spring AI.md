# **Spring AI 是什么？官方学习教程（2026）**

适合 Java / Spring Boot 开发者

**Spring AI 是 Spring 官方生态推出的 AI 应用开发框架，帮助 Java 开发者将大语言模型、企业数据库、外部 API 和 AI Agent 集成到 Spring Boot 应用中。**

简单理解：它让 Java 开发者不必转到 Python，也可以开发 RAG、AI Chatbot、Tool Calling、MCP 和 AI Agent。

Spring AI 借鉴了 LangChain、LlamaIndex 等项目的设计理念，但不是 LangChain 的 Java 移植版本。

[image](https://www.google.com/s2/favicons?domain=https://docs.spring.io\&sz=32)

Spring Docs+1



## **1. Spring AI 能做什么？**

| 功能                | 用途                          |
| ----------------- | --------------------------- |
| ChatClient        | 调用 OpenAI、Claude、Gemini 等模型 |
| Prompt            | 管理 AI 提示词                   |
| Chat Memory       | 保存多轮对话记忆                    |
| RAG               | 企业知识库问答                     |
| Embedding         | 文本向量化                       |
| Vector Store      | 向量数据库集成                     |
| Tool Calling      | 让 AI 调用 Java 方法             |
| Structured Output | 将 AI 输出转换成 Java 对象          |
| MCP               | 连接 MCP Server 和 Client      |
| Observability     | AI 调用监控和追踪                  |
| Evaluation        | 评估模型输出质量                    |

支持的模型和向量数据库很多，包括 OpenAI、Anthropic、Google、Amazon Bedrock、Ollama、PostgreSQL/PGVector、Pinecone、Qdrant 等。

[image](https://www.google.com/s2/favicons?domain=https://docs.spring.io\&sz=32)

Spring Docs+1



## **2. Spring AI 核心架构**

[Spring AI 2.0 vs LangChain4j，怎么选？ - 技术栈](https://images.openai.com/static-rsc-4/X1hs9MMCVvyuCVDNDGMTKCPsRmGgXLQINCfn6Nk9dntiN7oXYmzyS6Uxx7nBd7AKS3NMFngf6XvGkS_y9hqguO38GITXsmnQTiSpE-ig9FjPK67S8FlwVMHKNcUSUo3Ysu9VzjjST5XbFaIxriTxwnEdIsZ3fu3v7eKfR4f276E?purpose=inline)

[jishuzhan.net](https://jishuzhan.net/article/2047956491848712194?utm_source=chatgpt.com)

重点学习这几个核心组件：

1. **ChatClient**：调用大语言模型。
2. **ChatModel**：模型接口及其实现。
3. **Advisors**：封装 RAG、Memory 等常用 AI 模式。
4. **ChatMemory**：管理对话上下文。
5. **VectorStore**：连接向量数据库。
6. **EmbeddingModel**：生成向量。
7. **Tool Calling**：让模型调用 Java 工具。
8. **MCP**：连接外部 AI 工具和服务。

## **3. Spring AI、LangChain4j、LangChain 区别**

| 对比           | Spring AI   | LangChain4j  | LangChain    |
| ------------ | ----------- | ------------ | ------------ |
| 主要语言         | Java        | Java         | Python / JS  |
| 开发生态         | Spring Boot | Java         | Python / JS  |
| LLM 集成       | 支持          | 支持           | 支持           |
| RAG          | 支持          | 支持           | 支持           |
| Tool Calling | 支持          | 支持           | 支持           |
| MCP          | 支持          | 支持           | 支持           |
| Agent        | 支持相关能力      | 支持           | 支持           |
| 主要优势         | Spring 生态集成 | Java AI 开发抽象 | Python AI 生态 |

**我的建议：**

- Spring Boot 企业项目：优先学习 Spring AI。
- Java AI 应用开发：再学习 LangChain4j。
- Python Agent 开发：学习 LangChain + LangGraph。

不需要一开始把三个框架都深入学习。

## **4. 官方学习教程（2026）**

以下都是官方资源：

[image](https://www.google.com/s2/favicons?domain=https://docs.spring.io\&sz=32)

**1. Spring AI 官方文档**

必学

[Spring AI Reference Documentation](https://docs.spring.io/spring-ai/reference/?utm_source=chatgpt.com)

**2. Getting Started**

从零创建第一个 Spring AI 项目。

[官方入门教程](https://docs.spring.io/spring-ai/reference/getting-started.html?utm_source=chatgpt.com)

**3. ChatClient**

学习 Java 调用大模型、流式输出。

[ChatClient API](https://docs.spring.io/spring-ai/reference/api/chatclient.html?utm_source=chatgpt.com)

**4. RAG**

学习企业知识库、文档检索、向量数据库。

[RAG 官方教程](https://docs.spring.io/spring-ai/reference/api/retrieval-augmented-generation.html?utm_source=chatgpt.com)

**5. Tool Calling**

学习让 AI 调用 Java 方法和外部 API。

[Tool Calling API](https://docs.spring.io/spring-ai/reference/api/tools.html?utm_source=chatgpt.com)

**6. MCP**

学习创建 MCP Client 和 MCP Server。

[MCP 官方教程](https://docs.spring.io/spring-ai/reference/api/mcp/mcp-overview.html?utm_source=chatgpt.com)

**7. Spring AI GitHub**

[官方源代码](https://github.com/spring-projects/spring-ai?utm_source=chatgpt.com)

**8. 官方示例项目**

[Spring AI Examples](https://github.com/spring-projects/spring-ai-examples?utm_source=chatgpt.com)

**9. Spring Academy**

学习 Spring 生态及 AI 开发课程。

[Spring Academy](https://spring.academy/?utm_source=chatgpt.com)

## **5. 第一个 Spring AI 程序**

建议从 Spring Boot + OpenAI 开始。

版本说明：截至 2026 年 11 月，官方资料展示 Spring AI 2.0.x 对应 Spring Boot 4.x；Spring AI 1.1.x 对应 Spring Boot 3.5.x。下面以 2.0.x 系列为例，具体补丁版本请以官方文档为准。

[image](https://www.google.com/s2/favicons?domain=https://github.com\&sz=32)

GitHub+1



**第一步：创建项目**

打开 [Spring Initializr](https://start.spring.io/?utm_source=chatgpt.com)，选择：

- Project：Maven
- Language：Java
- Spring Boot：4.x
- Java：17 或更高版本
- Dependencies：Spring Web、Spring AI OpenAI

**第二步：添加依赖**

```
<dependency>
    <groupId>org.springframework.ai</groupId>
    <artifactId>spring-ai-starter-model-openai</artifactId>
</dependency>
```

建议使用 Spring AI 官方 BOM 管理版本，避免手动混用不同模块版本。

**第三步：配置 application.yml**

```
spring:
  ai:
    openai:
      api-key: ${OPENAI_API_KEY}
      chat:
        options:
          model: gpt-4o-mini
```

**第四步：编写 Java Controller**

```
@RestController
@RequestMapping("/api/ai")
public class AIController {

    private final ChatClient chatClient;

    public AIController(ChatClient.Builder builder) {
        this.chatClient = builder.build();
    }

    @GetMapping("/chat")
    public String chat(@RequestParam String message) {

        return chatClient.prompt()
                .user(message)
                .call()
                .content();
    }
}
```

**第五步：运行测试**

```
export OPENAI_API_KEY="your-api-key"

./mvnw spring-boot:run
```

浏览器访问：

```
http://localhost:8080/api/ai/chat?message=What%20is%20RAG
```

就能通过 Spring Boot 调用大模型。

## **6. 30 天学习路线**

| 时间        | 学习内容                           | 实战项目       |
| --------- | ------------------------------ | ---------- |
| Day 1–5   | ChatClient、ChatModel、Prompt    | AI Chatbot |
| Day 6–10  | Memory、Advisors、Streaming      | 多轮对话系统     |
| Day 11–15 | Embedding、VectorStore、RAG      | PDF 知识库    |
| Day 16–20 | Tool Calling、Structured Output | SQL Agent  |
| Day 21–25 | MCP、Agent                      | AI 工具助手    |
| Day 26–30 | Evaluation、Observability、AWS   | 企业 AI 应用   |

## **7. 推荐 Java AI Engineer 技术栈**

**Frontend**

React + Next.js + TypeScript

**Backend**

Java + Spring Boot + Spring Security

**AI Framework**

Spring AI + LangChain4j

**AI Engineering**

LLM + RAG + Agent + MCP + Vector DB

**Cloud**

AWS + Docker + Kubernetes + PostgreSQL

## **8. 建议做的 3 个 GitHub 项目**

[RAG Chatbot: What It Is, How It Works, and Why It Matters](https://images.openai.com/static-rsc-4/CCAa-9V8h0M-62LbmX4N-xe4ezCLGsqU6nAP5_vOJavePM3YgmokkU1_lmrZAJ7JHUOMQ4IIN2K2wv8dcs94iryhAq1nCeg_yZrOIHcbvfcwG3zhytnSrEokkgn07N8iqmKG5sCCouBwQP1OvWrKWEpEVMsdh6HqUnWfuRgB2tQ?purpose=inline)

**项目一：Enterprise RAG**

PDF 上传、文本切分、向量检索、企业知识库问答。

Spring AI + PostgreSQL + pgvector + OpenAI

[OpenBB Platform — built with AI on Blink](https://images.openai.com/static-rsc-4/h9eiLV1ciuRrmWPUnaGvv6S23NZa8zqLXhrsFuCM5iDPG7AOXCwKwx9mK0SMy6MsZu5YgOYYFZEOsl2RBXffk8Pa8vSRBS7C9kbobNatHzGeM6RqDOOLD_goHID7UzkBct-KU3kUaLkpJPqwnKKgNt5HN9Q8knR8XLhS39d5QB0?purpose=inline)

**项目二：AI Financial Agent**

查询股票数据、分析财报、整理新闻、生成风险报告。

Spring AI + Tool Calling + Market Data API

[FlowPilot Orchestrator | Devpost](https://images.openai.com/static-rsc-4/_iQxKB8XvnQQGB3sO8AXH5XguYApcTqwM-n3U21uhASST_4RDmphNmMBHGBZdA_ja0WpZ5iCQ9W5ip5KpGe_mTgMDhVu-_jWfQAiTVVNE9J72rauk3ZlLQ8B7VrU3_QtSx2yLlAMRDRbYx2Ujlo4qwAav0ucGLXqLju2RCUb4Ss?purpose=inline)

**项目三：Enterprise AI Agent**

企业知识库、数据库查询、MCP 工具调用、人工审批。

Spring AI + MCP + PostgreSQL + AWS

**最后给你一个明确建议：**

如果目标是美国 Java AI Engineer / AI Application Developer：

1. 先把 Spring AI 学扎实。
2. 学 LangChain4j，了解不同 Java AI 框架的设计。
3. 再学 Python + LangGraph，扩展 Agent 开发能力。
4. 用 AWS 部署完整项目，形成 GitHub 作品集。

**Spring AI 是 Java AI 开发值得优先掌握的框架。** 不需要为了学习 AI 而放弃已有的 Java / Spring Boot 技术积累。
