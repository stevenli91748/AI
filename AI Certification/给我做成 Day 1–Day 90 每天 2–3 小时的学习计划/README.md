可以。下面我按你目前的目标——美国 AI Engineer / AI Application Engineer——重新设计，不走纯考试路线，而是：

2–3 小时/天 = 证书 40% + Coding 40% + 项目/面试 20%。

我也核对了 2026 年官方认证资料：AWS AI Practitioner 的考试范围包括 AI/ML、GenAI、Foundation Models、Responsible AI、安全与治理；NVIDIA NCA-GENL 包括 LLM、Prompt Engineering、Python、LLM 集成部署；NVIDIA Agentic AI Professional 则要求更强的 Agent、多 Agent、部署、评估和治理能力。 

**一个重要调整：**90 天内我建议真正冲刺 AWS AI Practitioner + NVIDIA NCA-GENL；Agentic AI Professional 先完成项目和知识准备，不建议仅靠 90 天死磕证书，因为 NVIDIA 官方明确把它定位为有生产级 Agent 项目经验的 Professional 认证。 

90天 AI Engineer 证书 + 实战学习计划

一、最终目标

90天结束时，你应该具备：

* Python AI Application Development
* FastAPI
* LLM API
* Prompt Engineering
* Embedding
* Vector Database
* RAG
* LangChain
* LangGraph
* AI Agent
* Tool Calling
* MCP
* Multi-Agent
* PostgreSQL
* Docker
* AWS Bedrock
* AWS S3 / Lambda / IAM
* AI Evaluation
* AI Security
* GitHub 项目开发
* AI Engineer 面试能力

目标证书：

1. AWS Certified AI Practitioner
2. NVIDIA Certified Associate – Generative AI & LLMs
3. 为 NVIDIA Certified Professional – Agentic AI 做知识和项目准备

AWS Generative AI Developer – Professional 作为 90 天后的进阶目标。该认证目前重点包括 Foundation Model、RAG、Agentic AI、Prompt Engineering、生产部署、成本优化、测试和安全。(Amazon Web Services, Inc.⁠￼)

⸻

每天固定学习结构

每天 2–3 小时：

30–45 min   官方课程 / 理论
60–75 min   Python Coding
30–45 min   项目
15–30 min   面试题 / 复习

每天必须有 Git commit。

推荐：

ai-engineer-90days/
├── week01-python-ai/
├── week02-llm/
├── week03-rag/
├── week04-aws/
├── week05-fastapi/
├── week06-langchain/
├── week07-agent/
├── week08-langgraph/
├── week09-mcp/
├── week10-multi-agent/
├── week11-production/
├── week12-interview/
└── capstone/

⸻

WEEK 1 — Python AI 工程基础

Day 1

学习

* Python 环境
* venv
* pip
* Git
* GitHub
* VS Code
* Jupyter

官方课程

Python 官方教程：

https://docs.python.org/3/tutorial/

Python

def hello_ai(name: str) -> str:
    return f"Hello {name}, welcome to AI Engineering!"
print(hello_ai("AI Engineer"))

作业

建立：

ai-engineer-90days/
└── week01/
    └── day01.py

面试题

什么是 Python virtual environment？为什么 AI 项目应该使用 venv？

⸻

Day 2

学习

* list
* dict
* tuple
* set
* comprehension
* function

Python

documents = [
    {"id": 1, "text": "AWS is a cloud platform"},
    {"id": 2, "text": "RAG connects LLMs with external knowledge"},
]
for doc in documents:
    print(doc["text"])

作业

实现：

filter_documents()
search_documents()
count_words()

面试题

List 和 Tuple 有什么区别？

⸻

Day 3

学习

* class
* dataclass
* typing
* exception

Python

from dataclasses import dataclass
@dataclass
class Document:
    id: int
    text: str
doc = Document(1, "AI Engineer")
print(doc)

作业

建立 Document 类。

面试题

为什么 AI 应用大量使用 type hints？

⸻

Day 4

学习：

* JSON
* CSV
* pathlib
* file I/O

import json
data = {
    "model": "llm",
    "temperature": 0.2
}
with open("config.json", "w") as f:
    json.dump(data, f, indent=2)

作业：写 JSON loader。

面试题：JSON 和 Python dict 有什么区别？

⸻

Day 5

学习：

* requests
* REST API
* HTTP
* GET
* POST
* headers

import requests
response = requests.get(
    "https://api.github.com"
)
print(response.status_code)

作业：调用一个公开 REST API。

面试题：REST API 中 GET 和 POST 的区别？

⸻

Day 6

学习：

* Git
* GitHub
* branch
* commit
* pull request

Python：

def add(a: int, b: int) -> int:
    return a + b
print(add(10, 20))

作业：GitHub 建立第一个 AI Engineer repository。

面试题：Git merge 和 rebase 区别？

⸻

Day 7 — WEEK 1 PROJECT

项目：Document Analyzer

输入：

document.txt

输出：

characters
words
sentences
keywords
summary statistics

Python

from pathlib import Path
text = Path("document.txt").read_text()
words = text.split()
print("Characters:", len(text))
print("Words:", len(words))
print("Lines:", len(text.splitlines()))

本周必须完成

GitHub：

week01-python-ai

⸻

WEEK 2 — LLM 基础

Day 8

学习：

* AI
* ML
* Deep Learning
* Generative AI
* LLM

官方：

https://aws.amazon.com/ai/generative-ai/

作业：画 AI → ML → DL → GenAI → LLM 关系图。

面试题：LLM 和传统 Machine Learning 有什么区别？

⸻

Day 9

学习：

* Token
* Context Window
* Temperature
* Top-p
* Max Tokens

Python：

text = "Large Language Model"
tokens = text.split()
print(tokens)
print(len(tokens))

作业：研究 tokenization。

面试题：为什么 token 数量影响 API 成本？

⸻

Day 10

学习 Transformer：

Input
 ↓
Embedding
 ↓
Attention
 ↓
Feed Forward
 ↓
Output

面试题：

什么是 Self-Attention？

⸻

Day 11

学习：

* Encoder
* Decoder
* Transformer
* GPT

面试题：

GPT 为什么属于 decoder-only architecture？

⸻

Day 12

学习 Prompt Engineering：

Role
Task
Context
Constraints
Output Format

Python：

prompt = """
You are an AI engineer.
Explain RAG to a beginner.
Return the answer as 5 bullet points.
"""
print(prompt)

作业：写 10 个 Prompt。

⸻

Day 13

学习：

* Zero-shot
* One-shot
* Few-shot
* Structured Output

Python：

prompt = """
Classify the following text.
Categories:
- technical
- business
- other
Return JSON only.
Text:
AWS Bedrock provides foundation models.
"""

⸻

Day 14 — WEEK 2 PROJECT

项目：LLM Prompt Lab

实现：

prompt/
├── zero_shot.py
├── few_shot.py
├── json_output.py
└── prompt_templates.py

要求比较：

temperature=0
temperature=0.7
temperature=1.0

⸻

WEEK 3 — Embedding + Vector Database

Day 15

学习：

* Embedding
* Semantic Search
* Cosine Similarity

Python：

import numpy as np
a = np.array([1, 2, 3])
b = np.array([1, 2, 4])
similarity = np.dot(a, b) / (
    np.linalg.norm(a) * np.linalg.norm(b)
)
print(similarity)

⸻

Day 16

学习：

* Vector
* Dimension
* Similarity Search

面试题：

为什么不能简单使用 keyword search 替代 embedding search？

⸻

Day 17

学习：

* Chunking
* Chunk Size
* Overlap

Python：

def chunk_text(text, size=100, overlap=20):
    chunks = []
    start = 0
    while start < len(text):
        end = start + size
        chunks.append(text[start:end])
        start += size - overlap
    return chunks

⸻

Day 18

学习：

* Chroma
* FAISS
* pgvector

重点掌握：

Document
 ↓
Chunk
 ↓
Embedding
 ↓
Vector DB
 ↓
Similarity Search

⸻

Day 19

学习 PostgreSQL + pgvector。

作业：

建立：

documents
embeddings
metadata

⸻

Day 20

实现 Semantic Search。

Python：

def top_k(results, k=3):
    return sorted(
        results,
        key=lambda x: x["score"],
        reverse=True
    )[:k]

⸻

Day 21 — WEEK 3 PROJECT

Mini RAG v1

PDF/TXT
 ↓
Chunk
 ↓
Embedding
 ↓
Vector DB
 ↓
Search
 ↓
Top-K Documents

这是第一个非常重要的 GitHub 项目。

⸻

WEEK 4 — AWS + Bedrock

AWS AI Practitioner 官方考试重点正是 AI/ML、GenAI、Foundation Models、Responsible AI、安全和治理。(AWS Documentation⁠￼)

官方：

https://aws.amazon.com/certification/certified-ai-practitioner/

Day 22

学习：

* AWS Region
* AZ
* IAM
* S3
* EC2
* Lambda

⸻

Day 23

学习：

* Bedrock
* Foundation Models
* Model inference
* Model selection

⸻

Day 24

学习：

* S3
* IAM
* boto3

Python：

import boto3
s3 = boto3.client("s3")
response = s3.list_buckets()
for bucket in response["Buckets"]:
    print(bucket["Name"])

⸻

Day 25

学习 Bedrock API。

import boto3
bedrock = boto3.client("bedrock-runtime")
# 实际模型调用时根据当前 Bedrock model/API schema 配置 request body

作业：完成一次 Bedrock inference。

⸻

Day 26

学习：

* IAM policy
* Least privilege
* encryption
* secrets

面试题：

为什么不能把 AWS access key 写进 GitHub？

⸻

Day 27

学习：

* CloudWatch
* Lambda
* API Gateway

⸻

Day 28 — WEEK 4 PROJECT

AWS RAG

User
 ↓
API
 ↓
Lambda
 ↓
Bedrock
 ↓
S3
 ↓
Vector DB

⸻

WEEK 5 — FastAPI

Day 29

安装：

pip install fastapi uvicorn

代码：

from fastapi import FastAPI
app = FastAPI()
@app.get("/")
def home():
    return {"message": "AI Engineer API"}

运行：

uvicorn main:app --reload

⸻

Day 30

学习：

* GET
* POST
* Request
* Response
* Pydantic

from pydantic import BaseModel
class Question(BaseModel):
    text: str

⸻

Day 31

实现：

POST /ask

⸻

Day 32

实现：

POST /documents
GET /documents
DELETE /documents/{id}

⸻

Day 33

连接 PostgreSQL。

⸻

Day 34

加入 LLM。

FastAPI
 ↓
LLM
 ↓
Response

⸻

Day 35 — WEEK 5 PROJECT

AI Chat API

FastAPI
+
PostgreSQL
+
LLM

必须部署到 GitHub。

⸻

WEEK 6 — RAG Production

Day 36

学习完整 RAG：

Load
 ↓
Split
 ↓
Embed
 ↓
Store
 ↓
Retrieve
 ↓
Prompt
 ↓
Generate

⸻

Day 37

学习 LangChain。

官方：

https://python.langchain.com/

⸻

Day 38

LangChain：

* Document
* Retriever
* Prompt
* Chain

⸻

Day 39

学习 LlamaIndex。

官方：

https://www.llamaindex.ai/

⸻

Day 40

比较：

LangChain
vs
LlamaIndex

面试题：

什么时候使用 LangChain？什么时候使用 LlamaIndex？

⸻

Day 41

学习：

* Reranking
* Metadata filtering
* Hybrid search

⸻

Day 42 — WEEK 6 PROJECT

Enterprise RAG v2

要求：

PDF
 ↓
Chunk
 ↓
Embedding
 ↓
PostgreSQL/pgvector
 ↓
Retriever
 ↓
Reranker
 ↓
LLM
 ↓
Answer + Sources

⸻

WEEK 7 — AI Agent

Day 43

学习：

LLM
+
Tools
+
Memory
+
Planning

⸻

Day 44

Tool Calling。

def get_weather(city: str):
    return f"Weather for {city}"

⸻

Day 45

学习：

* Function Calling
* Structured Output

⸻

Day 46

Agent：

User
 ↓
LLM
 ↓
Tool
 ↓
Result
 ↓
LLM
 ↓
Answer

⸻

Day 47

学习：

* Memory
* Short-term memory
* Long-term memory

⸻

Day 48

学习 Agent Security：

* prompt injection
* tool abuse
* data leakage

⸻

Day 49 — WEEK 7 PROJECT

Personal AI Agent

Agent 能：

Search
Calculator
Database
Weather
Document Search

⸻

WEEK 8 — LangGraph

NVIDIA 的 NCA-GENL 官方学习内容已经覆盖 LangChain/LangGraph 等 LLM 应用开发方向。(NVIDIA⁠￼)

Day 50

学习：

* Graph
* Node
* Edge
* State

⸻

Day 51

建立：

START
 ↓
Agent
 ↓
Tool
 ↓
Agent
 ↓
END

⸻

Day 52

学习 conditional routing。

⸻

Day 53

学习 Agent memory。

⸻

Day 54

学习 Human-in-the-loop。

⸻

Day 55

学习 Agent evaluation。

⸻

Day 56 — WEEK 8 PROJECT

LangGraph Research Agent

User
 ↓
Planner
 ↓
Research Agent
 ↓
Search
 ↓
Summarizer
 ↓
Reviewer
 ↓
Final Answer

⸻

WEEK 9 — MCP

Day 57

学习：

* MCP
* MCP Server
* MCP Client
* Tools
* Resources

⸻

Day 58

建立第一个 MCP Tool。

def calculate(a: float, b: float):
    return a + b

⸻

Day 59

数据库 MCP Tool。

Agent
 ↓
MCP
 ↓
PostgreSQL

⸻

Day 60

File System Tool。

⸻

Day 61

API Tool。

⸻

Day 62

Security：

Authentication
Authorization
Input Validation
Rate Limit

⸻

Day 63 — WEEK 9 PROJECT

MCP AI Agent

LLM
 ↓
Agent
 ↓
MCP
 ├── Database
 ├── File
 ├── API
 └── Calculator

⸻

WEEK 10 — Multi-Agent

Day 64

学习 Multi-Agent Architecture。

⸻

Day 65

建立 Supervisor Agent。

Supervisor
 ├── Research
 ├── Coding
 └── Data

⸻

Day 66

Research Agent。

⸻

Day 67

Coding Agent。

⸻

Day 68

Data Agent。

⸻

Day 69

Agent communication。

⸻

Day 70 — WEEK 10 PROJECT

Multi-Agent Enterprise Assistant

最终：

                  User
                   ↓
              Supervisor
             /     |     \
            ↓      ↓      ↓
        Research  Code   Data
            \      |      /
             \     |     /
               Final

⸻

WEEK 11 — Production AI

AWS Generative AI Developer – Professional 官方考试目前重点包括 RAG、Foundation Models、Agentic AI、Prompt Engineering、生产效率、测试、验证、故障排查和安全。(AWS Documentation⁠￼)

Day 71

Docker。

FROM python:3.12
WORKDIR /app
COPY requirements.txt .
RUN pip install -r requirements.txt
COPY . .
CMD ["uvicorn", "main:app", "--host", "0.0.0.0"]

⸻

Day 72

Docker Compose：

FastAPI
PostgreSQL
Redis

⸻

Day 73

AWS ECS / Lambda。

⸻

Day 74

CI/CD。

GitHub
 ↓
GitHub Actions
 ↓
Docker
 ↓
AWS

⸻

Day 75

Logging。

⸻

Day 76

Monitoring。

⸻

Day 77

AI Evaluation：

Accuracy
Relevance
Faithfulness
Latency
Cost

⸻

WEEK 12 — Certification + Interview

Day 78

AWS AI Practitioner：

AI/ML Fundamentals。

⸻

Day 79

GenAI。

⸻

Day 80

Foundation Models。

⸻

Day 81

Responsible AI。

⸻

Day 82

Security / Governance。

⸻

Day 83

AWS Practice Questions。

⸻

Day 84 — AWS MOCK EXAM

目标：

≥ 80%

低于 80%：

重新学习错题。

⸻

WEEK 13 — NVIDIA NCA-GENL

NVIDIA NCA-GENL 目前为 Associate 级别，50–60 道题、60 分钟、$125，认证有效期两年。官方考试内容包括 ML/神经网络、Prompt Engineering、数据分析、实验、软件开发、Python LLM libraries 以及 LLM integration/deployment。(NVIDIA⁠￼)

Day 85

ML + Neural Network。

⸻

Day 86

Transformer + LLM。

⸻

Day 87

Prompt Engineering。

⸻

Day 88

Python + LLM Applications。

⸻

Day 89

LLM Integration + Deployment。

⸻

Day 90

FINAL PROJECT + MOCK INTERVIEW

完成：

Enterprise Multi-Agent AI Platform

最终架构：

                         User
                           ↓
                      FastAPI API
                           ↓
                     Supervisor
                    /     |      \
                   ↓      ↓       ↓
              Research   RAG    Data
                Agent    Agent   Agent
                   \       |      /
                    \      |     /
                       Tools
                         ↓
                        MCP
                         ↓
          ┌──────────────┼──────────────┐
          ↓              ↓              ↓
      PostgreSQL       AWS S3       External API
          ↓
       pgvector
          ↓
        RAG
          ↓
       LLM/Bedrock
          ↓
       Evaluation
          ↓
      Monitoring

⸻

每周必须完成的 GitHub 项目

周	项目	重要程度
Week 1	Document Analyzer	★★
Week 2	Prompt Lab	★★
Week 3	Mini RAG	★★★
Week 4	AWS RAG	★★★
Week 5	FastAPI AI API	★★★
Week 6	Enterprise RAG	★★★★★
Week 7	AI Agent	★★★★
Week 8	LangGraph Agent	★★★★★
Week 9	MCP Agent	★★★★★
Week 10	Multi-Agent	★★★★★
Week 11	Production AI	★★★★★
Week 12–13	Final Project	★★★★★

⸻

90天必须掌握的 Python

你最终至少应该能够独立写：

# API
FastAPI
# Data
Pandas
NumPy
# LLM
OpenAI / Anthropic / Gemini APIs
# RAG
Embeddings
Vector Search
# AI Framework
LangChain
LangGraph
LlamaIndex
# Agent
Tool Calling
MCP
Multi-Agent
# Database
PostgreSQL
pgvector
# Cloud
boto3
AWS Bedrock
# Production
Docker
pytest
logging

⸻

90天面试题核心清单

Python

1. List vs Tuple？
2. Generator 是什么？
3. Decorator 是什么？
4. async/await 怎么工作？
5. Pydantic 为什么适合 API？

LLM

6. Transformer 是什么？
7. Attention 是什么？
8. Token 是什么？
9. Temperature 是什么？
10. Context Window 是什么？

RAG

11. 为什么需要 RAG？
12. Chunk Size 怎么确定？
13. Overlap 有什么作用？
14. Embedding 是什么？
15. Vector DB 怎么工作？
16. Cosine Similarity 是什么？
17. Reranking 为什么需要？
18. RAG hallucination 怎么降低？

Agent

19. Agent 和普通 LLM Chain 区别？
20. Tool Calling 是什么？
21. Agent Memory 怎么设计？
22. Multi-Agent 为什么需要 Supervisor？
23. Agent 如何防止 Prompt Injection？
24. MCP 解决什么问题？

Production

25. 如何部署 LLM Application？
26. 如何降低 Token Cost？
27. 如何监控 LLM？
28. 如何测试 RAG？
29. 如何评估 Agent？
30. 如何保护 API Key？

⸻

证书考试顺序

第一个

AWS Certified AI Practitioner

官方考试范围：AI/ML、GenAI、Foundation Models、Responsible AI、安全和治理。(AWS Documentation⁠￼)

官方入口：

AWS Certified AI Practitioner 官方页面⁠￼

⸻

第二个

NVIDIA Certified Associate – Generative AI & LLMs

官方学习/考试：

NVIDIA NCA-GENL 官方页面⁠￼

官方推荐课程包括 Deep Learning、Transformer NLP、Prompt Engineering、LLM Application Development 等。(NVIDIA⁠￼)

⸻

第三个

NVIDIA Certified Professional – Agentic AI

不要把它当成90天必须拿下的证书。

先把：

Agent
LangGraph
MCP
Multi-Agent
Evaluation
Observability
Deployment
Security

全部做成项目。

NVIDIA 官方目前将 NCP-AAI 定位为 Professional 级别，考试 60–70 题、120 分钟，重点包括 Agent architecture、development、multi-agent interaction、deployment、governance 等。(NVIDIA⁠￼)

官方：

NVIDIA Agentic AI Professional 官方页面⁠￼

⸻

90天之后

下一阶段建议：

AWS AI Practitioner
        ↓
NVIDIA NCA-GENL
        ↓
AI Engineer Job
        ↓
AWS GenAI Developer Professional
        ↓
NVIDIA Agentic AI Professional

AWS GenAI Developer Professional 目前是 75 题、180 分钟、$300，并且官方明确要求更偏生产级 GenAI 开发经验，所以放在后面更合理。(Amazon Web Services, Inc.⁠￼)

⸻

最重要的执行规则

每天不要只看课程。

必须遵守：

学 40%
写代码 40%
项目 20%

每天至少：

git add .
git commit -m "Day XX: ..."
git push

90天结束时，你的 GitHub 不应该只是：

tutorial/
notebook/
hello-world/

而应该有：

01-document-analyzer
02-prompt-lab
03-rag-system
04-fastapi-ai
05-enterprise-rag
06-langgraph-agent
07-mcp-agent
08-multi-agent-platform
09-production-ai

其中 Enterprise RAG + LangGraph Agent + MCP Multi-Agent 三个项目，是最值得放到美国 AI Engineer 简历上的项目。

