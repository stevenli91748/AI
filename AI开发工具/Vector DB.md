# **Vector DB 有几种？官方学习教程（2026）**

**Vector DB（Vector Database，向量数据库）没有固定的种类数量。** 目前主流产品有十几种，按架构和部署方式，大致可以分为 4 大类。

它是 RAG（检索增强生成）的核心组件之一，负责存储 Embedding（向量），根据用户问题寻找语义相似的文档，再把相关内容交给 LLM 生成答案。

## **1. Vector DB 四大类别**

第一类

**专用向量数据库（Dedicated Vector Database）**

专门为向量存储、相似度搜索、RAG 设计。

代表：Pinecone、Qdrant、Milvus、Weaviate、Chroma。

第二类

**传统数据库增加向量功能**

在现有数据库中直接存储和检索向量。

代表：PostgreSQL + pgvector、MongoDB Atlas Vector Search、Redis。

第三类

**搜索引擎增加向量搜索**

将关键词搜索和语义搜索结合。

代表：Elasticsearch、OpenSearch。

第四类

**向量搜索库 / 嵌入式引擎**

直接在应用程序或本地进程中执行向量检索。

代表：FAISS、LanceDB。

## **2. 2026 年最值得学习的 10 种 Vector DB**

| Vector DB                   | 类型    | 主要特点         |
| --------------------------- | ----- | ------------ |
| Pinecone                    | 云服务   | 托管方便，减少运维    |
| Qdrant                      | 专用数据库 | 过滤、混合检索能力强   |
| Milvus                      | 专用数据库 | 大规模向量检索      |
| Weaviate                    | 专用数据库 | 混合搜索、多模态     |
| Chroma                      | 专用数据库 | 上手简单，适合原型    |
| PostgreSQL + pgvector       | 数据库扩展 | 与 SQL、业务数据结合 |
| MongoDB Atlas Vector Search | 数据库功能 | 文档数据与向量搜索结合  |
| Redis                       | 数据库功能 | 低延迟检索、缓存     |
| Elasticsearch               | 搜索引擎  | 关键词 + 语义混合搜索 |
| OpenSearch                  | 搜索引擎  | 开源搜索与向量检索    |

这些产品并不是完全相同类型的数据库。Spring AI 官方也提供了多种 VectorStore 实现，包括 PGVector、Pinecone、Qdrant、Milvus、Redis、Weaviate 等。

[image](https://www.google.com/s2/favicons?domain=https://docs.spring.io\&sz=32)

Spring Docs+2



## **3. 每种 Vector DB 的官方学习教程**

以下按学习优先级和应用场景整理。

[Is pgvector Free? Pricing & Free Tier Explained](https://images.openai.com/static-rsc-4/KTU1tQE-NuLK2YdSAGLavwIOWcoAINwzbW3yWB6GqfREKQQZmFIR74Ogl7OUm__VuFIivOYfScFl8m3lUAWxJXMahFEU5i6Pzt2f_WtvKEq8XtZOxl2bh5XeQ-ZOahv0QbifY7waoZQ2DE4U23hKFi4kMHgYtc0XJWkT7EJdLnY?purpose=inline)

**1. PostgreSQL + pgvector**

最推荐 Java 开发者先学

- 在 PostgreSQL 中直接存储 Embedding。
- 支持 HNSW、IVFFlat 索引。
- 适合企业 RAG、业务数据库与向量检索结合。

官方教程：

- [pgvector GitHub / README](https://github.com/pgvector/pgvector?utm_source=chatgpt.com)
- [安装教程](https://github.com/pgvector/pgvector?utm_source=chatgpt.com#installation)
- [PostgreSQL 官方文档](https://www.postgresql.org/docs/?utm_source=chatgpt.com)

[Qdrant Logo PNG Vector (SVG) Free Download](https://images.openai.com/static-rsc-4/Ais5_PO1Q56lnD04G32Sa9OvzjljEw3O6tdYc-8PMK7p_5K9QpkMAg5Pmk0uI4UzILesmZm2eR-gVp2kGg1yvxjYFlu6fPcQk4i5V2hvE2OTpew59H-VjVlQKDxKl4VKyLCWREm2VDQxsKr2Pb4spxLXKRRt6ijY6juSYnsWlu4?purpose=inline)

**2. Qdrant**

重点推荐

- 专门为向量检索设计。
- 支持 Metadata Filtering、Hybrid Search。
- 适合企业 RAG 和 AI Agent 长期记忆。

官方教程：

- [Qdrant Documentation](https://qdrant.tech/documentation/?utm_source=chatgpt.com)
- [Quickstart](https://qdrant.tech/documentation/quickstart/?utm_source=chatgpt.com)
- [Basic Tutorials](https://qdrant.tech/documentation/tutorials-basics/?utm_source=chatgpt.com)
- [Qdrant Learn](https://qdrant.tech/learn/?utm_source=chatgpt.com)

  [image](https://www.google.com/s2/favicons?domain=https://qdrant.tech\&sz=32)

  Qdrant+2

[首个国产开源AI数据平台Milvus加入世界顶级开源组织 | 极客公园](https://images.openai.com/static-rsc-4/o3rMQnH-M2owYON3cmf7ltyDuhhtX1QWToEpfLO-hbAsEwupeDey2fGIH9ffBUWLMVcsohiM8jbLxYOh1Ubwf2Myizyk9ZnQc_H--FlYOAMJ6Mytohc3suSVWXZ869baKKWn12Cfej-1q9YXUkDsjOGQaVXW2TSKBFulw8qIDBo?purpose=inline)

**3. Milvus**

- 开源分布式向量数据库。
- 适合大规模数据、海量向量搜索。
- 支持 Python、Java、Go 等客户端。

官方教程：

- [Milvus Documentation](https://milvus.io/docs?utm_source=chatgpt.com)
- [Quickstart](https://milvus.io/docs/quickstart.md?utm_source=chatgpt.com)
- [实战教程](https://milvus.io/docs/tutorials-overview.md?utm_source=chatgpt.com)

  [image](https://www.google.com/s2/favicons?domain=https://milvus.io\&sz=32)

  Milvus Documentation+2

[Free Pinecone Database Logo Vector Download | Logowik](https://images.openai.com/static-rsc-4/ZCcEP9oqgXCc97bY0CkikmEYTNBXB4Q6hl6u3qEZBdKvNCJ_w6MowXrMvs4i0h0J4Z92r2ZKS_Drkrbjx_9O2LUfbY4axlzZKDIe-7Si3G_kEN8GGR3eIBHHSO2O_4vkegc6pDl3eKRgIQF3FNsvLhEuc0fZx61lNkZz6c-vJ3w?purpose=inline)

**4. Pinecone**

- 主要提供托管式向量数据库服务。
- 不需要自己管理数据库集群。
- 适合快速开发和云端 RAG。

官方教程：

- [Pinecone Documentation](https://docs.pinecone.io/?utm_source=chatgpt.com)
- [Getting Started](https://docs.pinecone.io/guides/get-started/overview?utm_source=chatgpt.com)
- [Pinecone Learn](https://www.pinecone.io/learn/?utm_source=chatgpt.com)

[Weaviate Logo PNG Vector (SVG) Free Download](https://images.openai.com/static-rsc-4/ZFpfcIqnVOJz0mo0Kb2ZgPi67e4FJbn-om9pGuJyfw6u0hyEMp1ZsjPTkqZe_xZpXmRezrYST6jat8rXuuzp2fQ3At-2n0M0_YGEC0UQS4Wz24eVR4yANeiIwoSWPB4hhZkickfpgf9Gui7sky-Z3AvG4wS-VEbyVtVXSUBdtzM?purpose=inline)

**5. Weaviate**

- 支持向量检索和关键词混合检索。
- 支持多模态搜索。
- 适合复杂知识库和 AI 搜索。

官方教程：

- [Weaviate Documentation](https://docs.weaviate.io/?utm_source=chatgpt.com)
- [Quickstart](https://docs.weaviate.io/weaviate/quickstart?utm_source=chatgpt.com)
- [Guides & Tutorials](https://docs.weaviate.io/weaviate/guides?utm_source=chatgpt.com)

  [image](https://www.google.com/s2/favicons?domain=https://docs.weaviate.io\&sz=32)

  Weaviate Documentation+2

[GenAI Ops Landscape](https://images.openai.com/static-rsc-4/aQ_ZzGzR1dclTQI6BE2fCc-3vCNC4c2-ynD2akBbAvJ7KmVOwtWWMgW4RJsuuZlbQQe-BViU6ezk5cvPsWbiu28zuJPJam_tzU7PbKZGhuc4kPv8gnSPoVImFZxbwL3xm1qQILFEeHnXc1yuEZQyqrkFocYelphhcfm-719XYOQ?purpose=inline)

**6. Chroma**

- 上手简单。
- 适合本地开发、RAG 原型和实验。
- 支持 Dense、Sparse、Hybrid Search。

官方教程：

- [Chroma Documentation](https://docs.trychroma.com/?utm_source=chatgpt.com)
- [Getting Started](https://docs.trychroma.com/getting-started?utm_source=chatgpt.com)

  [image](https://www.google.com/s2/favicons?domain=https://docs.trychroma.com\&sz=32)

  Chroma Docs

[Logo MongoDB – Logos PNG](https://images.openai.com/static-rsc-4/SbiEDpKtwja1kucgkTVf7sO8obZYMtZg076NUK6_2TnjVkqPY7X5zximOx0uS9y_WNL719aDmcLeXd7Vlh1zksq8cdBrMRE-WwkhE95bja2HOYoId52qZBeQrWeoP6pFDdxX2q583XgJbggXoLcRe4C4g_BmeRtWqkQpxgwyIuk?purpose=inline)

**7. MongoDB Atlas Vector Search**

- 向量和业务文档存储在 MongoDB 生态。
- 支持语义搜索、混合搜索和 RAG。

官方教程：

- [Vector Search Documentation](https://www.mongodb.com/docs/atlas/atlas-vector-search/?utm_source=chatgpt.com)
- [MongoDB University 免费课程](https://learn.mongodb.com/learning-paths/atlas-vector-search?utm_source=chatgpt.com)

  [image](https://www.google.com/s2/favicons?domain=https://learn.mongodb.com\&sz=32)

  MongoDB University+1

[Redis Logo PNG Vector (SVG) Free Download](https://images.openai.com/static-rsc-4/epIZvTJqrn11fZoyLAql3XQvzvr05WTs4k_hS-9tdnMQyi9Nak_EpGx1d16Qeud3z3mmGKrPzkfB8l4M10kTA8OEXwDm6CtTKKvBDOawlkZbKJwF8Jjm3IiHXcBUIohDPkufesDQyxMCNKXpFH79YSUkxtDVtdaR-HKvPqdpBXw?purpose=inline)

**8. Redis Vector Search**

- 低延迟向量搜索。
- 可以结合缓存、实时数据和向量检索。
- 适合实时 AI 应用。

官方教程：

- [Vector Database Tutorial](https://redis.io/docs/latest/get-started/vector-database/?utm_source=chatgpt.com)
- [Vector Search Concepts](https://redis.io/docs/latest/develop/ai/search-and-query/vectors/?utm_source=chatgpt.com)

  [image](https://www.google.com/s2/favicons?domain=https://redis.io\&sz=32)

  Docs+1

[MeteorOps | Elasticsearch Consulting](https://images.openai.com/static-rsc-4/5XJo7RvL5PC2FsaRJ4sr7zlmL4OGYlq1GgxTs7tebmvbzJrXgC_vz0t0ZqZ4npAckbAqP5MyrqMnTKy5C9ZWAX3YkCm1NEMtYqEJz9ioVuBZTBiDiKTQVYMzkR4x7ZgPNqSvOM-pSIzKgYbu9mNyarN037SJ_3GuzaYIS-PM9iw?purpose=inline)

**9. Elasticsearch**

- 强大的全文搜索与向量搜索结合。
- 适合企业搜索、日志搜索和 RAG。

官方教程：

- [Vector Search Documentation](https://www.elastic.co/docs/solutions/search/vector?utm_source=chatgpt.com)
- [10 分钟入门](https://www.elastic.co/docs/solutions/vector-database/vector-full-text-search?utm_source=chatgpt.com)

  [image](https://www.google.com/s2/favicons?domain=https://www.elastic.co\&sz=32)

  Elastic Docs+1

[Opensearch PNG Logo — Download Free Transparent Logo](https://images.openai.com/static-rsc-4/IvcO7CxMMPUvvufAqmUBOTlFcIUNpGjsGCjPoPDNzybD7w2lTpWBR6e7qaKFeT25jijXzIXcewkB1MTuem2YaY2LE73nSXbMGrHCWIM_jqJmu4MlL_aFnsh_GGnPdqEPWL_hQ2878kBA3MtnpMwyBl9FXI8Q-N5ee7ggfyBe3DY?purpose=inline)

**10. OpenSearch**

- 开源搜索和分析引擎。
- 支持 Semantic、Hybrid、Multimodal Search。
- 适合企业级 AI Search。

官方教程：

- [Vector Search Documentation](https://docs.opensearch.org/latest/vector-search/?utm_source=chatgpt.com)
- [Vector Search Tutorials](https://docs.opensearch.org/latest/tutorials/vector-search/index/?utm_source=chatgpt.com)

  [image](https://www.google.com/s2/favicons?domain=https://docs.opensearch.org\&sz=32)

  OpenSearch Documentation+1

## **4. 如何选择 Vector DB？**

| 使用场景                    | 推荐                         |
| ----------------------- | -------------------------- |
| Java + Spring Boot 企业应用 | PostgreSQL + pgvector      |
| 企业级 RAG                 | Qdrant                     |
| 数亿级以上大规模向量检索需求          | Milvus                     |
| 不想管理数据库基础设施             | Pinecone                   |
| 复杂混合搜索和多模态              | Weaviate                   |
| 初学者、本地实验                | Chroma                     |
| 已经使用 MongoDB            | MongoDB Vector Search      |
| 实时检索和缓存                 | Redis                      |
| 企业全文搜索 + AI 搜索          | Elasticsearch / OpenSearch |

以上是场景匹配建议，不是绝对性能排名。实际选型还需要根据向量数量、并发量、过滤条件、延迟要求、成本和运维能力做压测。

## **5. Spring AI 如何连接 Vector DB？**

Spring AI 提供统一的 `VectorStore` 接口，尽量减少更换数据库时的业务代码修改。

官方支持的实现包括：

- PGVector
- Pinecone
- Qdrant
- Milvus
- Chroma
- Redis
- MongoDB Atlas
- Weaviate
- Elasticsearch
- OpenSearch

官方教程：[Spring AI Vector Database Integrations](https://docs.spring.io/spring-ai/reference/api/vectordbs.html?utm_source=chatgpt.com)。

[image](https://www.google.com/s2/favicons?domain=https://docs.spring.io\&sz=32)

Spring Docs+1



## **6. Vector DB 必须掌握的技术知识**

| 技术                 | 作用          |
| ------------------ | ----------- |
| Embedding          | 把文本转成向量     |
| Vector Index       | 建立向量索引      |
| HNSW               | 加速近似最近邻搜索   |
| IVFFlat            | 另一种向量索引方式   |
| Cosine Similarity  | 计算向量相似度     |
| Metadata Filtering | 按属性筛选文档     |
| Hybrid Search      | 结合关键词和向量检索  |
| Reranking          | 对初次检索结果重新排序 |
| Quantization       | 压缩向量、降低存储成本 |

## **7. 给你的学习顺序：30 天**

我建议不要同时学习十种数据库，先学会一套完整的 RAG 系统。

## **30 天 Vector DB 实战路线**

1. **Day 1–7：PostgreSQL + pgvector**
   - 安装 PostgreSQL。
   - 安装 pgvector。
   - 学习 Embedding 存储。
   - 学习 HNSW 和相似度搜索。
2. **Day 8–14：Qdrant**
   - Docker 部署。
   - Collection、Point、Payload。
   - Vector Search。
   - Metadata Filtering。
3. **Day 15–21：Milvus + Pinecone**
   - 理解分布式向量数据库。
   - 学习云端托管数据库。
   - 比较本地部署与云服务。
4. **Day 22–30：Spring AI + RAG**
   - Spring Boot 接入 pgvector。
   - 实现 PDF 文档上传。
   - 实现 Chunking 和 Embedding。
   - 实现 RAG 问答。
   - Docker 部署。

## **8. 最终建议**



优先学习

&#x20;PostgreSQL + pgvector 和 Qdrant。



如果目标是 Java AI Engineer / AI Application Developer，我建议先用：

**Enterprise RAG 项目技术栈**

React + Next.js

Java + Spring Boot + Spring AI

OpenAI Embeddings + RAG

PostgreSQL + pgvector

Docker + AWS

**先把 pgvector 学会，再学 Qdrant。** 这两个足以帮助你建立扎实的 RAG 数据库基础。不要把时间浪费在同时学习十种产品上。
