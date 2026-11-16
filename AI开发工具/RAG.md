# **RAG 是什么？官方学习资源（2026）**

**RAG = Retrieval-Augmented Generation，检索增强生成。**

它是 AI Engineer 必须掌握的核心技术之一。

简单理解：

普通 ChatGPT 主要根据模型已经学习的知识回答问题；RAG 则让 AI 先从你提供的资料、数据库或企业知识库中查找相关内容，再把找到的内容交给 LLM 生成答案。

**例如：**

你上传 1000 份 PDF 文件，建立一个企业知识库。

然后问 AI：

> 公司员工的年假政策是什么？

AI 会：

1. 搜索相关 PDF。
2. 找到年假政策所在的段落。
3. 把相关内容交给 GPT 或 Claude。
4. 根据原始文件回答。
5. 提供文件来源和引用。

这就是 RAG。

## **一、RAG 的工作原理**

[Building RAG Chatbots: Bridging LLMs with Private Data | Rahul K B | Staff Machine Learning Engineer](https://images.openai.com/static-rsc-4/zee8MkIg-u9r2bPUM2aLGQO4-Otm_xxZ8OAIc8kMIT6YEUi4Lq6cYhbrXDXlrR1N6K2mxLZaNPQhlk6xcMKMihqDnRd47YZjqaHBDtIRuL1ja0jK5jt1zoFXJuSYUhITSgaM29PbwitMjBx5SS67x5X8lrQqc7-26o7REMCHYPU?purpose=inline)

[kb-rahul.github.io](https://kb-rahul.github.io/posts/rag-chatbots-architecture/?utm_source=chatgpt.com)

RAG 主要分为两个流程：

**A. Indexing（知识库建立）**

1. Document Loading：读取 PDF、Word、TXT。
2. Text Splitting：把长文档切分成小块（Chunking）。
3. Embedding：把文本转换成向量。
4. Vector Storage：存入向量数据库。

**B. Retrieval + Generation（问答）**

1. 用户提出问题。
2. 把问题转换成向量。
3. 搜索相关文档。
4. 将搜索结果和问题一起发送给 LLM。
5. LLM 生成答案。

[image](https://www.google.com/s2/favicons?domain=https://www.pinecone.io\&sz=32)

Pinecone+2

## **二、RAG 必须学习的核心技术**

| 技术                 | 作用          | 重要程度 |
| ------------------ | ----------- | ---- |
| Document Loading   | 读取文档        | 必须   |
| Chunking           | 文本切分        | 必须   |
| Embeddings         | 文本向量化       | 必须   |
| Vector Database    | 向量存储        | 必须   |
| Similarity Search  | 相似度搜索       | 必须   |
| Metadata Filtering | 元数据过滤       | 必须   |
| Reranking          | 搜索结果排序      | 必须   |
| Hybrid Search      | 混合搜索        | 推荐   |
| Query Rewriting    | 查询优化        | 推荐   |
| RAG Evaluation     | RAG 质量评估    | 必须   |
| Agentic RAG        | Agent 驱动的检索 | 进阶   |

## **三、2026 年值得学习的 RAG 框架**

[Upsurge | Sovereign Agentic Infrastructure](https://images.openai.com/static-rsc-4/aLIlKpJiXKJl6y-cJpfmvEqD35lbjmlL5Ns-gvZ2aSkAsHQSX39cfCm1QJ4aj5WYA36Ci_eYlGv7Ohjzeo-hsPl_cbe_saFAhv851oGz_leTTu7CjeEsJnmzG4DC0uiJ_FmjYcU5_mUhE1sRSG_k0fgsvMywESiZF1q_i2JMWCE?purpose=inline)

**1. LangChain**

优先学习

- Document Loaders
- Text Splitters
- Embeddings
- Vector Stores
- Retrievers

官方资源：[LangChain RAG 教程](https://docs.langchain.com/oss/python/langchain/rag?utm_source=chatgpt.com)

[LlamaIndex IA - Construye agentes LLM sobre datos empresariales](https://images.openai.com/static-rsc-4/Jwyz2pGQx3aEvo88hfCxFHaSOdnH8jabqMSMBe9v1eQIxy_-qmfvCmMNFdzPKNgHOOxI3pMSShPq0BfaSJLeoet3PftCEu4tC6zcFl-iHXXVAcWa52sLB-JnJLWzuvBg20TFbjOmD9XuWqVoTWMy6WpMrqizWJHRCOACUFk6OQw?purpose=inline)

**2. LlamaIndex**

优先学习

- Data Connectors
- Indexing
- Query Engine
- Retrieval
- RAG Pipeline

官方资源：[LlamaIndex RAG Documentation](https://developers.llamaindex.ai/python/framework/understanding/rag/?trk=article-ssr-frontend-pulse_little-text-block\&utm_source=chatgpt.com)

[adding the Haystack logo · deepset/should-i-follow at b707cdc](https://images.openai.com/static-rsc-4/x0c9VO_SM_2w9dKqdLj60YLB-qdItmEYXogLNd4CVAECq6SZIR2-cZpOEsUcVyfz-cBK411AtBL1ov8ivQEu1p2wkOPsQGEdFLTxXb4u8GFc-S6qC5z1ikK9NnRqnuIq467rW_-ALCcx1Om1xrJxBqMY19SJAEFveC1ShJrRf_Q?purpose=inline)

**3. Haystack**

- RAG Pipelines
- Document Stores
- Retrieval
- Production AI

官方资源：[Haystack Documentation](https://docs.haystack.deepset.ai/?utm_source=chatgpt.com)

**学习建议：** 先学 LangChain，再学 LlamaIndex。两个都不需要同时精通。

## **四、向量数据库（Vector Database）**

RAG 的核心组件之一。负责存储 Embeddings，并根据用户问题检索相关内容。

| 数据库                   | 特点         | 官方学习资源                                                                  |
| --------------------- | ---------- | ----------------------------------------------------------------------- |
| PostgreSQL + pgvector | SQL + 向量搜索 | [pgvector](https://github.com/pgvector/pgvector?utm_source=chatgpt.com) |
| Pinecone              | 托管向量数据库    | [Pinecone](https://docs.pinecone.io/?utm_source=chatgpt.com)            |
| Chroma                | 适合快速开发和学习  | [Chroma](https://docs.trychroma.com/?utm_source=chatgpt.com)            |
| Qdrant                | 向量检索和过滤    | [Qdrant](https://qdrant.tech/documentation/?utm_source=chatgpt.com)     |
| Weaviate              | 向量数据库和语义搜索 | [Weaviate](https://docs.weaviate.io/?utm_source=chatgpt.com)            |
| Milvus                | 大规模向量检索    | [Milvus](https://milvus.io/docs?utm_source=chatgpt.com)                 |

**我的建议：**

先学 PostgreSQL + pgvector，再了解 Pinecone 和 Qdrant。

## **五、RAG 官方学习资源大全**

下面这些建议收藏。

**1. RAG 基础理论**

- [Pinecone — What is RAG?](https://www.pinecone.io/learn/retrieval-augmented-generation/?utm_source=chatgpt.com)
- [LlamaIndex — Introduction to RAG](https://developers.llamaindex.ai/python/framework/understanding/rag/?trk=article-ssr-frontend-pulse_little-text-block\&utm_source=chatgpt.com)

  **2. LLM 和 Embeddings**
- [OpenAI Embeddings](https://platform.openai.com/docs/guides/embeddings?utm_source=chatgpt.com)
- [OpenAI API Documentation](https://platform.openai.com/docs?utm_source=chatgpt.com)

  **3. RAG 开发框架**
- [LangChain Documentation](https://docs.langchain.com/?utm_source=chatgpt.com)
- [LlamaIndex Documentation](https://developers.llamaindex.ai/?utm_source=chatgpt.com)

  **4. 向量数据库**
- [pgvector GitHub](https://github.com/pgvector/pgvector?utm_source=chatgpt.com)
- [Pinecone Documentation](https://docs.pinecone.io/?utm_source=chatgpt.com)
- [Qdrant Documentation](https://qdrant.tech/documentation/?utm_source=chatgpt.com)

  **5. RAG 质量评估**
- [Ragas Documentation](https://docs.ragas.io/?utm_source=chatgpt.com)
- [LangSmith Documentation](https://docs.smith.langchain.com/?utm_source=chatgpt.com)

  Ragas 可用于评估检索质量、答案相关性和忠实度。

## **六、RAG 和 Fine-tuning 有什么区别？**

这是 AI Engineer 面试常见问题。

| 比较     | RAG    | Fine-tuning |
| ------ | ------ | ----------- |
| 中文     | 检索增强生成 | 模型微调        |
| 主要目的   | 增加外部知识 | 改变模型行为或输出方式 |
| 是否训练模型 | 不需要    | 需要          |
| 更新知识   | 更新知识库  | 通常需要重新训练或微调 |
| 私有知识库  | 非常适合   | 不适合作为唯一方案   |
| 成本     | 通常较低   | 训练和数据准备成本较高 |

例如：

- 让 AI 查询公司最新的员工手册：使用 RAG。
- 让 AI 学会固定的客服表达风格：考虑 Fine-tuning。

两种技术也可以组合使用。

## **七、30 天 RAG 学习路线**

每天 2 小时，建议按顺序完成

| 时间        | 学习内容                    | 实践目标   |
| --------- | ----------------------- | ------ |
| Day 1–3   | RAG 原理、LLM API          | 理解 RAG |
| Day 4–6   | Python、Document Loading | 读取 PDF |
| Day 7–9   | Chunking                | 文档切分   |
| Day 10–12 | Embeddings              | 文本向量化  |
| Day 13–15 | PostgreSQL + pgvector   | 向量存储   |
| Day 16–18 | Similarity Search       | 语义搜索   |
| Day 19–21 | LangChain RAG           | 建立问答系统 |
| Day 22–24 | Reranking、Hybrid Search | 优化检索   |
| Day 25–26 | RAG Evaluation          | 评估准确性  |
| Day 27–28 | LangGraph + Agentic RAG | 智能检索   |
| Day 29–30 | Docker + AWS            | 部署项目   |

## **八、推荐做的 3 个 GitHub 项目**

[How I Built a Local RAG App for PDF Q&A | Streamlit | LLAMA 3.x | 2025 | by SEO Tanvir BD | Medium](https://images.openai.com/static-rsc-4/DqCqVbfxeivz0-fxKFUCt5JF-qKWp73izzkeFf15UYYDzBxpqBQarOiRlSrqOyZb5vlG23FWt_OgxedoCvFdp945e_2mHlm5eGuo0JRA6TZ-LDMEtVRO_huXBpYSCSrZHdPcM8d5pUQSAQmNjYPc90AKSKKHJUf9iAtpGjv_yiQ?purpose=inline)

**项目 1：PDF RAG Chatbot**

初级

- 上传 PDF
- 自动切分
- 向量检索
- AI 问答和来源引用

技术：Python + FastAPI + OpenAI + pgvector

[AI Internal Knowledge Search by Mohammed TAYOR on Dribbble](https://images.openai.com/static-rsc-4/UQmigjAZukVk01CB-45P5nBMldyJGulBRvGELdEpQ4ygClyyuEInDWrcU3YDosOZdGDFRk9fKZ3izMZz0jNwoBFhxz0grSPkb3JOAzENtbDiqTG06dhKXcue7_UtYPsJ50zPo3G9H9jE2xK3VHMYCu-1rdDU-pv8K6awdFTO_-0?purpose=inline)

**项目 2：Enterprise Knowledge Base**

中级

- 多文档知识库
- Hybrid Search
- Reranking
- 用户权限管理

技术：LangChain + PostgreSQL + RAG

[Руководство по созданию приложения для поиска данных на основе агента GraphRAG / Хабр](https://images.openai.com/static-rsc-4/Dn_LofE30KHXa0zc-V_10359A-g67Vnipgs8nlJ7fgZJT1pT6lX4io9qUAcy0j9TmJDpCbqQoZtOcEhR5Xi2sPJNHJR2r-EYsR1BfYh2EF0DaNHFD0X-l89RadNIiKXEIYBkqZuw1I8t9ATBte90fc6LYNZQHpufIlgDOqLeExw?purpose=inline)

**项目 3：Agentic RAG Platform**

高级

- Agent 自动检索
- 多数据源查询
- 多模型切换
- RAG 质量评估

技术：LangGraph + FastAPI + Next.js + AWS

## **九、最终推荐的 AI Engineer 技术栈**

**AI Application Development**

前端

Next.js + React + TypeScript

后端

Python + FastAPI

LLM

OpenAI + Claude + Gemini

RAG / Agent

LangChain + LangGraph + LlamaIndex

Database

PostgreSQL + pgvector + Redis

Deployment

Docker + AWS + CI/CD

**最重要的建议：** 不要只学 RAG 框架，要理解 Chunking、Embedding、Retrieval、Reranking 的底层原理。真正的工程能力还包括检索评估、权限隔离、数据更新和错误处理。

下一步最值得做的是：从零开发一个 **Python + FastAPI + PostgreSQL + pgvector 的 PDF RAG 项目**，这是很好的 AI Engineer 求职作品集起点。
