如果按企业级 AI 问答（AI Q&A）方案来分类，目前主流大约可以分为 8 种。不同方案适用于不同的业务场景。

1. 纯 LLM 问答（最简单）
用户
   │
GPT-5 / Claude / Gemini
   │
回答

特点：

不需要数据库
不需要知识库
适合通用知识问答

例如：

ChatGPT
Claude
Gemini

优点

开发最快
成本低

缺点

不知道企业内部知识
容易产生幻觉（Hallucination）
2. Prompt Engineering
用户
   │
Prompt Template
   │
LLM

在 Prompt 中加入：

角色
输出格式
示例（Few-shot）
规则

适合：

客服
文案
SQL 生成
代码生成
3. RAG（Retrieval-Augmented Generation）
用户
    │
Embedding
    │
Vector Database
    │
Top K Documents
    │
LLM

这是目前企业最常见的知识库问答方案。

适合：

企业知识库
PDF
Word
Confluence↳
SharePoint↳
Wiki

优点：

可以回答企业内部信息
不需要重新训练模型
4. Agent 问答
User

↓

LLM

↓

Planner

↓

Tool

↓

Answer

Agent 可以：

查询数据库
调用 API
搜索网页
执行代码
调用多个工具

适合：

AI 助手
企业 Copilot
自动办公
5. MCP（Model Context Protocol）
LLM

↓

MCP Client

↓

MCP Server

↓

Database/API/File

MCP 负责统一连接各种外部资源，让模型安全、标准化地访问数据和工具。

适合：

企业内部系统
ERP
CRM
GitHub
文件系统
数据库
6. SQL 问答（Text-to-SQL）
Question

↓

LLM

↓

SQL

↓

Database

↓

Answer

例如：

用户问：

去年销售额最高的产品是什么？

模型生成 SQL，查询数据库后返回答案。

适合：

BI
数据分析
报表
7. GraphRAG（图谱增强问答）
Knowledge Graph

↓

Graph Search

↓

LLM

比普通 RAG 更适合复杂关系推理。

适合：

医疗
金融
法律
制造业
科研
8. 多 Agent 问答（Multi-Agent）
User
      │
Coordinator
 ┌────┼────┐
Agent1 Agent2 Agent3
      │
 Final Answer

多个 Agent 分工合作，例如：

搜索 Agent
SQL Agent
编程 Agent
总结 Agent

适合复杂企业工作流。

各方案对比
方案	难度	企业使用率	是否推荐
纯 LLM	⭐	★★★★★	✓ 入门必学
Prompt Engineering	⭐	★★★★★	✓ 必学
RAG	⭐⭐⭐	★★★★★	✓ 企业核心
Agent	⭐⭐⭐	★★★★★	✓ 企业核心
MCP	⭐⭐⭐	★★★★☆	✓ 越来越重要
Text-to-SQL	⭐⭐⭐	★★★★☆	✓ 数据分析场景
GraphRAG	⭐⭐⭐⭐	★★☆☆☆	特定行业
Multi-Agent	⭐⭐⭐⭐	★★★☆☆	复杂场景
目前美国企业最常见的架构

很多生产环境不会只采用一种方案，而是组合使用，例如：

用户
   │
前端（Web / Mobile）
   │
AI Agent
   │
├── RAG（知识库）
├── MCP（连接工具）
├── Text-to-SQL（查询数据库）
├── Web Search（联网搜索）
└── LLM（生成最终回答）

这种组合能够同时利用企业知识、实时数据和业务系统，是目前许多企业 AI 助手的典型架构。

如果你的目标是学习企业 AI 应用开发

建议按以下顺序掌握：

Prompt Engineering↳
LLM API（如 OpenAI、Claude、Gemini）↳
RAG
AI Agent
MCP
Text-to-SQL↳
Evaluation（模型评测）
Multi-Agent↳
GraphRAG（按需学习）

这条路线覆盖了当前美国大多数企业级 AI 问答系统的核心技术栈。
