# **PostgreSQL 是什么？官方学习资源（2026）**

**PostgreSQL 是一个免费、开源的关系型数据库管理系统（RDBMS）。**

简单理解：PostgreSQL 就是用来存储、管理、查询和处理应用程序数据的数据库。

例如，你开发一个 AI ChatGPT 应用：

- 用户注册、登录信息 → PostgreSQL
- 用户聊天记录 → PostgreSQL
- 用户上传的文档信息 → PostgreSQL
- RAG 文档向量数据 → PostgreSQL + pgvector
- AI Agent 运行记录 → PostgreSQL

[Exploring PostgreSQL Data Directory](https://images.openai.com/static-rsc-4/Sxxtl-9KYfSRb_htGi7nkszJTXelhE2AjP3eiL5Bcdc3nrdnQa-pC58i0muO3DIrrkaMAdWUY_rQn_VNVmF7DmZkiPfAfIH06sXB3WnMAPCaotWUB8C7JpJ4AAsHWvrtR-JrR3JMrJ_6Vg7UgM9F27Vdrjo91yzKtCkZ1DyRK2g?purpose=inline)

## **一、PostgreSQL 和 MySQL 有什么区别？**

| 比较      | PostgreSQL   | MySQL  |
| ------- | ------------ | ------ |
| 类型      | 关系型数据库       | 关系型数据库 |
| 开源      | 是            | 是      |
| SQL 支持  | 非常强          | 非常强    |
| JSON 支持 | JSON / JSONB | JSON   |
| 复杂查询    | 很强           | 很强     |
| 向量搜索    | pgvector 扩展  | 需要其他方案 |
| AI 应用   | 非常适合         | 也可以    |
| 企业应用    | 广泛使用         | 广泛使用   |

**我的建议：2026 年学习 AI 应用开发，优先学习 PostgreSQL。**

## **二、PostgreSQL 核心知识体系**

建议分成 8 个阶段学习。

| 阶段 | 学习内容                | 必须掌握                                  |
| -- | ------------------- | ------------------------------------- |
| 1  | Database Basics     | Database、Schema、Table                 |
| 2  | SQL Basics          | SELECT、INSERT、UPDATE、DELETE           |
| 3  | SQL Advanced        | JOIN、GROUP BY、HAVING                  |
| 4  | Database Design     | Primary Key、Foreign Key、Normalization |
| 5  | Advanced SQL        | CTE、Window Functions、Subqueries       |
| 6  | Performance         | Index、EXPLAIN、Query Optimization      |
| 7  | Advanced PostgreSQL | JSONB、Transactions、Triggers           |
| 8  | AI Database         | pgvector、Vector Search、RAG            |

## **三、官方学习资源**

以下都是值得收藏的官方资源。

[Postgresql Logo PNG Transparent With Clear Background ID 473068 |  TOPpng](https://images.openai.com/static-rsc-4/x6sDZ8oKI9URixQ5E82vqCQV1aR38qK7E8n0HKggx6_cD8G7QtlPuHlyO99GalHPJOycjs41bPgfrRTqdHFqayPWJl57hxNttQynREzHXSUSsui_zVAB_ssyc1xdm_msJ5GiDzf23C9Z2RuuoyVCc6J0AbuAqX5Aul_x1J78q2I?purpose=inline)

**1. PostgreSQL 官方网站**

官方

[postgresql.org](https://www.postgresql.org/?utm_source=chatgpt.com)

**2. PostgreSQL 官方文档（最重要）**

[PostgreSQL Official Tutorial](https://www.postgresql.org/docs/current/tutorial.html?utm_source=chatgpt.com)

学习数据库创建、SQL、JOIN、事务、索引等。

[image](https://www.google.com/s2/favicons?domain=https://www.postgresql.org\&sz=32)

PostgreSQL+1



**3. PostgreSQL 官方安装下载**

[Download PostgreSQL](https://www.postgresql.org/download/?utm_source=chatgpt.com)

**4. PostgreSQL SQL 命令参考**

[SQL Commands Reference](https://www.postgresql.org/docs/current/sql-commands.html?utm_source=chatgpt.com)

**5. PostgreSQL 官方 Wiki**

[PostgreSQL Wiki](https://wiki.postgresql.org/?utm_source=chatgpt.com)

**6. pgAdmin 数据库管理工具**

[pgAdmin 官方网站](https://www.pgadmin.org/?utm_source=chatgpt.com)

**7. pgvector 官方 GitHub**

[pgvector](https://github.com/pgvector/pgvector?utm_source=chatgpt.com)

AI 向量数据库和 RAG 项目非常重要。

## **四、必须掌握的 SQL 示例**

先学习以下基本操作。

**1. 创建数据库**

```
CREATE DATABASE ai_platform;
```

**2. 创建用户表**

```
CREATE TABLE users (
    id SERIAL PRIMARY KEY,
    username VARCHAR(100),
    email VARCHAR(255),
    created_at TIMESTAMP DEFAULT NOW()
);
```

**3. 插入数据**

```
INSERT INTO users (username, email)
VALUES ('Tom', 'tom@gmail.com');
```

**4. 查询数据**

```
SELECT * FROM users;
```

**5. 更新数据**

```
UPDATE users
SET username = 'John'
WHERE id = 1;
```

**6. 删除数据**

```
DELETE FROM users
WHERE id = 1;
```

## **五、PostgreSQL 在 AI Engineer 技术栈中的位置**

这是建议掌握的完整技术架构：

**Frontend**

Next.js + React + TypeScript

**Backend**

Python + FastAPI

**AI Application**

OpenAI API + LangChain + LangGraph + RAG

**PostgreSQL**

用户、业务、聊天记录

**pgvector**

Embeddings、向量检索

**AWS Deployment**

Docker + AWS RDS + ECS

## **六、建议的 30 天学习计划**

| 时间        | 学习任务                       |
| --------- | -------------------------- |
| Day 1–3   | 安装 PostgreSQL、pgAdmin      |
| Day 4–7   | SQL 基础 CRUD                |
| Day 8–10  | JOIN、GROUP BY              |
| Day 11–14 | Database Design、关系模型       |
| Day 15–18 | Index、Transactions         |
| Day 19–21 | JSONB、CTE、Window Functions |
| Day 22–24 | Python + SQLAlchemy        |
| Day 25–27 | FastAPI + PostgreSQL       |
| Day 28–30 | pgvector + RAG             |

## **七、建议完成的实战项目**

[Browse thousands of User Management Dashboard images for design inspiration | Dribbble](https://images.openai.com/static-rsc-4/P1rJCZsnyGz4ekeLMWNQvnn4BQJ7iQbl-wweBc3Ah8v79dykhAiWKOHLpfVbGMTg8U_G7pSh9h0z3tFIKShpBL-KoHjDrhvnjIFxlU8IpN2xvD8bHHOBe7VsYOKYdCouNoyLqiVCIiqwp5EZvZuxY-hh0fBVakwAZB-n0pxjOT8?purpose=inline)

**项目 1：用户管理系统**

PostgreSQL + FastAPI + CRUD + JWT

初级

[Botizo - AI Chatbot Hub UI by Pixem Studio on Dribbble](https://images.openai.com/static-rsc-4/m-rnGOCxB5Q6b_jinzrXuR2YI-xVrU95ydg-6I6DdPdbY36A3jpiqH80KB6rS8IfoKiFHKaQdHJzj72xsMNs7jezWGFGUTG74FuhDk6SIJc-a2pnD2_a7SVxcTXD_dox--k877yKqs2Uhv_zQHqt1WiX1HQ350COG-GTLJsIFEw?purpose=inline)

**项目 2：AI Chatbot**

Next.js + FastAPI + PostgreSQL + OpenAI API

中级

[Loading...](https://images.openai.com/static-rsc-4/zkFIFbValkmOFw7EXZKKVvQe2Ghc8u9ibz2LB99seOl1fHr3V7GgR3HESqDGrswFy44LWWFFrtEo0aTgXRqyexzewJGP3c1Q0uVoLfxGdjthDqJxnk_mEmDOxhXAzyTu7DurusNnBD2ezWAeBVYlE7z44r0kOEb2ykw2j1T7aXA?purpose=inline)

**项目 3：RAG Knowledge Base**

PostgreSQL + pgvector + LangChain + FastAPI

高级

**最后给你一个学习建议：**

如果目标是美国 AI Engineer / AI Application Developer，建议把以下技术作为重点：

1. Python + FastAPI
2. PostgreSQL + SQLAlchemy
3. Next.js + TypeScript
4. OpenAI API
5. LangGraph + RAG
6. pgvector
7. Docker + AWS

这套技术栈可以支持你开发完整的企业级 AI 应用。
