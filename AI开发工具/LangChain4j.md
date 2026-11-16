# **LangChain4j 是什么？**

**LangChain4j 是一个基于 Java 的开源 LLM 应用开发框架。**

简单理解：它相当于 Java 生态中的 LangChain，帮助 Java 开发者将 OpenAI、Claude、Gemini 等大模型接入 Spring Boot 应用，并开发 RAG、AI Chatbot、Tool Calling 和 AI Agent。

它不是 Python LangChain 的 Java 移植版本，而是按照 Java 的接口、注解、类型安全和依赖注入习惯独立设计的框架。

[image](https://www.google.com/s2/favicons?domain=https://docs.langchain4j.dev\&sz=32)

LangChain4j+1



适合 Java / Spring Boot 开发者

## **1. LangChain4j 可以做什么？**

| 功能                 | 用途                          |
| ------------------ | --------------------------- |
| LLM Integration    | 接入 OpenAI、Claude、Gemini 等模型 |
| AI Services        | 使用 Java 接口快速构建 AI 服务        |
| Prompt Engineering | 管理和设计 Prompt                |
| Chat Memory        | 保存对话上下文                     |
| Tool Calling       | 让 AI 调用 Java 方法和外部 API      |
| RAG                | 构建企业知识库问答                   |
| Embeddings         | 文本向量化                       |
| Vector Database    | 接入 pgvector、Pinecone 等      |
| Agents             | 构建 AI Agent                 |
| MCP                | 接入 MCP Server 和外部工具         |

官方文档介绍了 20 多种模型提供商和 30 多种向量存储集成。

[image](https://www.google.com/s2/favicons?domain=https://docs.langchain4j.dev\&sz=32)

LangChain4j+1



## **2. LangChain4j 核心架构**

[JVM Java 大模型框架选型：Spring AI 2.0 vs LangChain4j 深度对比 - 云栈社区](https://images.openai.com/static-rsc-4/7IELrP6g_Zdv9eBcLXVZjS8Cj1ZP2TvK28i1qGG4ubht40lOq0unC5O_TmkbxXaYlP3mQu9ittcVthGGeU9-azjXOCWGzHGW9vbSRjGPLnKpxa3HRoBFq-HbFdA7eFV3zxCzIzz--JimO8Rr0fYOBDaHHenELQdPIdSwYPCh7w4?purpose=inline)

[yunpan.plus](https://yunpan.plus/t/24304-1-1?utm_source=chatgpt.com)

建议掌握以下核心组件：

1. `ChatModel`：连接大语言模型。
2. `ChatMemory`：保存对话记录。
3. `AiServices`：通过 Java Interface 定义 AI 服务。
4. `EmbeddingModel`：生成文本向量。
5. `EmbeddingStore`：存储和检索向量。
6. `ContentRetriever`：检索相关知识。
7. `Tools`：调用 Java 方法。
8. `Agentic`：构建 Agent 工作流程。

## **3. LangChain4j 和 LangChain 有什么区别？**

| 比较           | LangChain4j | LangChain           |
| ------------ | ----------- | ------------------- |
| 开发语言         | Java        | Python / JavaScript |
| 主要生态         | Spring Boot | Python、JS/TS        |
| AI Services  | 支持          | 有不同的 Agent/API 抽象   |
| RAG          | 支持          | 支持                  |
| Tool Calling | 支持          | 支持                  |
| Agent        | 支持          | 支持                  |
| MCP          | 支持          | 支持                  |
| 适合场景         | Java 企业应用   | Python AI 应用        |

**怎么选择？**

- 如果开发 Spring Boot 企业系统：优先 LangChain4j。
- 如果开发 Python AI 应用：优先 LangChain。
- 如果开发复杂 Agent：进一步学习 LangGraph。

## **4. 官方学习教程（2026）**

以下是建议收藏的官方学习资料。

[image](https://www.google.com/s2/favicons?domain=https://docs.langchain4j.dev\&sz=32)

**1. 官方文档**

必学

[LangChain4j Introduction](https://docs.langchain4j.dev/intro/?utm_source=chatgpt.com)

**2. Getting Started**

从零开始安装、配置和调用大模型。

[官方入门教程](https://docs.langchain4j.dev/get-started/?utm_source=chatgpt.com)

**3. Tutorials**

包含 Chat Model、Memory、AI Services、RAG、Tools、Agents。

[官方完整教程](https://docs.langchain4j.dev/category/tutorials/?utm_source=chatgpt.com)

**4. RAG 教程**

学习文档加载、切分、向量检索和问答。

[RAG Tutorial](https://docs.langchain4j.dev/tutorials/rag/?utm_source=chatgpt.com)

**5. Spring Boot 集成**

使用 LangChain4j 开发 Spring Boot AI 应用。

[Spring Boot Integration](https://docs.langchain4j.dev/tutorials/spring-boot-integration/?utm_source=chatgpt.com)

**6. GitHub 源代码**

[LangChain4j GitHub](https://github.com/langchain4j/langchain4j?utm_source=chatgpt.com)

**7. 官方代码示例**

[LangChain4j Examples](https://github.com/langchain4j/langchain4j-examples?utm_source=chatgpt.com)

**8. Microsoft 免费入门课程**

从 Chat、Prompt、RAG、Tools 一直学习到 MCP 和 Agent。

强烈推荐

[LangChain4j for Beginners](https://github.com/microsoft/LangChain4j-for-Beginners?utm_source=chatgpt.com)

## **5. 第一个 LangChain4j 程序**

建议使用 Java 17+、Maven、Spring Boot。

**第一步：添加 Maven 依赖**

以下版本以官方 Getting Started 页面展示的 1.23.0 为例。

[image](https://www.google.com/s2/favicons?domain=https://docs.langchain4j.dev\&sz=32)

LangChain4j



```
<dependency>
    <groupId>dev.langchain4j</groupId>
    <artifactId>langchain4j-open-ai</artifactId>
    <version>1.23.0</version>
</dependency>
```

**第二步：配置 API Key**

```
export OPENAI_API_KEY="your-api-key"
```

**第三步：Java 调用大模型**

```
import dev.langchain4j.model.openai.OpenAiChatModel;

public class Main {

    public static void main(String[] args) {

        var model = OpenAiChatModel.builder()
                .apiKey(System.getenv("OPENAI_API_KEY"))
                .modelName("gpt-4o-mini")
                .build();

        String answer = model.chat(
                "Explain what RAG is."
        );

        System.out.println(answer);
    }
}
```

运行后，Java 程序就能通过 LangChain4j 调用大模型。

## **6. 30 天学习路线**

| 时间        | 学习内容                       | 实战项目        |
| --------- | -------------------------- | ----------- |
| Day 1–5   | ChatModel、Prompt、Messages  | AI Chatbot  |
| Day 6–10  | AI Services、ChatMemory     | 多轮对话助手      |
| Day 11–15 | Embeddings、Vector Database | PDF 知识库     |
| Day 16–20 | RAG、Retriever、Tools        | 企业知识库 Agent |
| Day 21–25 | MCP、Agentic                | AI 工具调用系统   |
| Day 26–30 | Spring Boot、AWS、Docker     | 完整 AI 应用    |

## **7. 推荐的 Java AI Engineer 技术栈**

**Frontend**

React + Next.js + TypeScript

**Backend**

Java + Spring Boot + Spring Security

**AI Development**

LangChain4j + Spring AI + LLM API

**AI Architecture**

RAG + Agent + MCP + Vector Database

**Cloud & Deployment**

AWS + Docker + Kubernetes + PostgreSQL

## **8. 我建议你重点学习什么？**

如果目标是美国 Java AI Engineer / AI Application Developer 岗位，我建议：

- **优先掌握：** Spring Boot + LangChain4j + RAG + Tool Calling。
- **继续掌握：** MCP + Agent + LangGraph（Python 生态）。
- **最后掌握：** AWS 部署、AI Evaluation、Monitoring。

特别建议做一个 GitHub 项目：

**Enterprise AI Knowledge Assistant**

- Spring Boot 后端
- LangChain4j 接入 OpenAI
- PostgreSQL + pgvector
- RAG 企业知识库
- MCP 外部工具调用
- LangSmith / 可观测性方案
- Docker + AWS 部署

这比单纯完成几个教程更能体现实际工程能力。

**我的建议：** 如果走 Java AI 开发路线，先学 LangChain4j，再学 Spring AI。两者都值得了解，但不需要一开始同时深入。
