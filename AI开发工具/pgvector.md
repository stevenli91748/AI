# **pgvector 是什么？官方学习教程（2026）**

推荐 Java AI Engineer 学习

**pgvector 是 PostgreSQL 的一个开源扩展（Extension），让 PostgreSQL 可以存储 Embedding 向量，并执行向量相似度搜索。**

简单理解：

- PostgreSQL：存储普通业务数据，例如用户、订单、产品。
- pgvector：让 PostgreSQL 同时存储 AI 向量。
- RAG：利用 pgvector 找到与用户问题相关的文档，再交给 LLM 回答。

它不是独立数据库，而是 PostgreSQL 的扩展。

[image](https://www.google.com/s2/favicons?domain=https://github.com\&sz=32)

GitHub+1



## **1. pgvector 能做什么？**

假设你建立了一个企业 PDF 知识库。

**PDF 文档**

公司制度、产品手册、技术文档

**Embedding Model**

把文字转换成数字向量

**PostgreSQL + pgvector**

存储向量、建立索引、相似度搜索

**RAG Retrieval**

找到最相关的文档内容

**LLM**

根据检索结果生成答案

例如：

用户问：「公司的员工医疗保险有哪些规定？」

pgvector 根据问题的 Embedding，搜索最相关的公司制度文档。

然后把找到的内容交给 GPT 或 Claude 回答。

## **2. pgvector 的核心功能**

| 功能                 | 作用                 |
| ------------------ | ------------------ |
| Vector Data Type   | 存储向量               |
| Similarity Search  | 搜索相似向量             |
| Cosine Distance    | 计算余弦距离             |
| L2 Distance        | 计算欧几里得距离           |
| Inner Product      | 计算内积               |
| HNSW               | 高性能近似向量搜索索引        |
| IVFFlat            | 另一种近似向量搜索索引        |
| Metadata Filtering | 结合 SQL 条件过滤        |
| Hybrid Search      | 结合 PostgreSQL 全文搜索 |

pgvector 支持精确最近邻搜索和近似最近邻搜索，并提供 HNSW 和 IVFFlat 两种索引。

[image](https://www.google.com/s2/favicons?domain=https://github.com\&sz=32)

GitHub+1



## **3. pgvector 两种重要索引**

**HNSW（Hierarchical Navigable Small World）**

重点学习

- 使用多层图结构搜索向量。
- 通常具有较好的速度与召回率平衡。
- 建立索引比较慢，内存使用较高。
- 可以在表中还没有数据时创建索引。

SQL：

```
CREATE INDEX ON documents
USING hnsw (embedding vector_cosine_ops);
```

**IVFFlat（Inverted File Flat）**

- 将向量划分为多个聚类列表。
- 建立索引通常较快，内存开销较低。
- 需要先有一定数量的数据再建立索引。
- 需要调整 lists 和 probes 参数。

SQL：

```
CREATE INDEX ON documents
USING ivfflat (embedding vector_cosine_ops)
WITH (lists = 100);
```

两种索引都属于近似搜索，速度与召回率之间需要权衡。官方建议先使用默认参数，再根据实际数据和测试结果调整。

[image](https://www.google.com/s2/favicons?domain=https://github.com\&sz=32)

GitHub+1



## **4. pgvector 官方学习教程（2026）**

[image](https://www.google.com/s2/favicons?domain=https://github.com\&sz=32)

**1. pgvector 官方 GitHub**

必学

官方 README 包含安装、SQL、向量搜索、索引和性能优化。

[pgvector 官方教程](https://github.com/pgvector/pgvector?utm_source=chatgpt.com)

**2. PostgreSQL 官方文档**

学习 SQL、表结构、索引、事务和查询优化。

[PostgreSQL Documentation](https://www.postgresql.org/docs/?utm_source=chatgpt.com)

**3. PostgreSQL 官方教程**

[SQL Tutorial](https://www.postgresql.org/docs/current/tutorial.html?utm_source=chatgpt.com)

**4. PostgreSQL 下载**

[Download PostgreSQL](https://www.postgresql.org/download/?utm_source=chatgpt.com)

**5. Docker 官方文档**

学习 Docker 部署 PostgreSQL。

[Docker Documentation](https://docs.docker.com/?utm_source=chatgpt.com)

**6. Spring AI Vector Database**

学习 Spring AI 如何连接 pgvector。

[Spring AI PGVectorStore](https://docs.spring.io/spring-ai/reference/api/vectordbs/pgvector.html?utm_source=chatgpt.com)

**7. LangChain4j RAG**

学习 Java 如何使用向量数据库构建 RAG。

[LangChain4j RAG Tutorial](https://docs.langchain4j.dev/tutorials/rag/?utm_source=chatgpt.com)

## **5. 实战：安装 pgvector**

推荐使用 Docker，方便搭建开发环境。

**第一步：启动 PostgreSQL + pgvector**

```
docker run -d \
  --name pgvector-db \
  -e POSTGRES_USER=aiuser \
  -e POSTGRES_PASSWORD=ai123456 \
  -e POSTGRES_DB=ai_db \
  -p 5432:5432 \
  pgvector/pgvector:pg17
```

官方 Docker 镜像：

[pgvector Docker Hub](https://hub.docker.com/r/pgvector/pgvector?utm_source=chatgpt.com)

**第二步：启用扩展**

```
CREATE EXTENSION IF NOT EXISTS vector;
```

**第三步：创建向量表**

这里用 3 维向量演示，实际项目应该根据 Embedding 模型的输出维度设置。

```
CREATE TABLE documents (
    id BIGSERIAL PRIMARY KEY,
    content TEXT,
    embedding VECTOR(3)
);
```

**第四步：插入数据**

```
INSERT INTO documents (content, embedding)
VALUES
('Java Spring Boot Tutorial',
 '[0.1, 0.2, 0.3]'),

('Python FastAPI Tutorial',
 '[0.2, 0.3, 0.4]'),

('AI Machine Learning',
 '[0.8, 0.7, 0.6]');
```

**第五步：查询相似向量**

```
SELECT
    id,
    content,
    embedding <=> '[0.1, 0.2, 0.3]' AS distance
FROM documents
ORDER BY embedding <=> '[0.1, 0.2, 0.3]'
LIMIT 2;
```

`<=>` 表示 Cosine Distance，距离越小，向量越相似。

其他常见运算符：

| 运算符   | 含义                     |
| ----- | ---------------------- |
| `<->` | L2 欧几里得距离              |
| `<=>` | Cosine Distance        |
| `<#>` | Negative Inner Product |
| `<+>` | L1 Distance            |

这些是 pgvector 官方支持的向量距离运算符。

[image](https://www.google.com/s2/favicons?domain=https://github.com\&sz=32)

GitHub+1



**第六步：创建 HNSW 索引**

```
CREATE INDEX documents_embedding_idx
ON documents
USING hnsw (embedding vector_cosine_ops);
```

至此，你已经完成了最基础的向量存储和检索。

## **6. Spring AI 如何连接 pgvector？**

Java AI 应用可以使用 Spring AI 的 `PgVectorStore`。

Maven 依赖：

```
<dependency>
    <groupId>org.springframework.ai</groupId>
    <artifactId>spring-ai-starter-vector-store-pgvector</artifactId>
</dependency>
```

配置示例：

```
spring:
  datasource:
    url: jdbc:postgresql://localhost:5432/ai_db
    username: aiuser
    password: ${DB_PASSWORD}

  ai:
    vectorstore:
      pgvector:
        initialize-schema: true
        index-type: HNSW
        distance-type: COSINE_DISTANCE
```

Java 使用示例：

```
@Autowired
private VectorStore vectorStore;

public void saveDocument() {

    Document document = new Document(
        "Spring AI is a Java AI framework."
    );

    vectorStore.add(List.of(document));
}

public List<Document> search(String query) {

    return vectorStore.similaritySearch(
        SearchRequest.builder()
            .query(query)
            .topK(5)
            .build()
    );
}
```

Spring AI 会通过配置的 EmbeddingModel 生成向量，并使用 VectorStore 保存和检索。实际项目还要配置 Embedding Model 和对应的 API Key。

官方参考：[Spring AI PGVectorStore 文档](https://docs.spring.io/spring-ai/reference/api/vectordbs/pgvector.html?utm_source=chatgpt.com)。

## **7. 30 天 pgvector 学习计划**

| 时间        | 学习内容                             | 实战目标      |
| --------- | -------------------------------- | --------- |
| Day 1–5   | PostgreSQL、SQL                   | 创建数据库和数据表 |
| Day 6–10  | Vector、Embedding                 | 存储文本向量    |
| Day 11–15 | Cosine、L2、Inner Product          | 实现相似度搜索   |
| Day 16–20 | HNSW、IVFFlat                     | 建立向量索引    |
| Day 21–25 | Metadata Filtering、Hybrid Search | 实现混合检索    |
| Day 26–30 | Spring AI + RAG                  | 开发企业知识库   |

## **8. 最值得做的 GitHub 项目**

[Oumar Ben Lol - Portfolio | Ingénieur IA & Développeur Full Stack](https://images.openai.com/static-rsc-4/e2nuRd3epX4m0RKmMmdGcBimQepQXd6DU42aNCMopYYJlji6D01nVgRQPsN1gavP888WJDwgdMnUBJPnXIaKUOIIVJI1zQsD7qCII9mO9Wq7PN9zQdkLpqhNuvSwoywvnR4xv54Qyc8IVTsyo3iVWJ6tZ9LE22HLgol-L_AMIqs?purpose=inline)

[oumarbenlol.com](https://oumarbenlol.com/projects/?utm_source=chatgpt.com)

**Enterprise AI Knowledge Base**

技术架构：

- Frontend：React + Next.js
- Backend：Java + Spring Boot
- AI Framework：Spring AI
- LLM：OpenAI API
- Embedding：OpenAI Embeddings
- Vector DB：PostgreSQL + pgvector
- Deployment：Docker + AWS

核心功能：

1. 上传 PDF、Word 文件。
2. 自动解析和 Chunking。
3. 调用 Embedding API。
4. 保存向量到 pgvector。
5. HNSW 相似度搜索。
6. RAG 生成答案。
7. 显示引用的原始文档。

**我的建议：** 对 Java AI Engineer 来说，pgvector 是非常值得优先掌握的技术。你不必一开始学习所有 Vector DB，先掌握 PostgreSQL + pgvector + Spring AI + RAG，就可以完成一个完整的企业级 AI 知识库项目。

后续可以再学习 Qdrant 和 Milvus，理解专用向量数据库与 PostgreSQL 扩展之间的区别。
