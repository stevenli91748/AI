我们直接把它搭成一个能真正开发、运行、调试 LLM Application 的 AWS 环境。

我建议你这次不要走 Cloud9，因为 AWS 官方已经明确：Cloud9 不再向新客户开放。

我们采用：

Windows + Cursor/VS Code → AWS EC2 Ubuntu → Docker → FastAPI → OpenAI/Bedrock → PostgreSQL/pgvector

先完成一个最小可运行的 LLM API，然后再逐步加入 RAG、Agent、MCP。

目标环境

最终你会得到：

Windows
└── Cursor / VS Code
        │
        │ AWS Session Manager
        ▼
AWS EC2 Ubuntu 24.04
├── Git
├── Python 3
├── Docker
├── FastAPI
├── OpenAI SDK
├── LangChain
├── LlamaIndex
└── MCP
        │
        ├── OpenAI API
        ├── AWS Bedrock
        │
        └── PostgreSQL + pgvector

第一阶段先不要装一大堆东西。

今天只做到：

AWS EC2
   ↓
Ubuntu
   ↓
Docker
   ↓
Python
   ↓
FastAPI
   ↓
LLM API
   ↓
浏览器成功返回答案

第 0 步：准备 AWS

进入：

AWS Console

如果你已经有 AWS Account，直接登录。

Region

建议你使用：

US West (Oregon) — us-west-2

后面做 Bedrock、RDS、ECS 等服务时尽量统一 Region。

第 1 步：创建 EC2

进入：

AWS Console → EC2 → Instances → Launch instance

设置：

Name
llm-dev
OS

选择：

Ubuntu Server 24.04 LTS
64-bit (x86)
Instance type

先选择：

t3.medium

配置：

2 vCPU
4 GiB RAM

这个配置比较适合你后面同时运行：

FastAPI
Docker
Python
RAG
Agent

如果只是测试，可以先用更小实例；如果同时跑 PostgreSQL、Redis、多个容器，再升级。

第 2 步：Storage

Root volume：

30 GB
gp3

如果以后存很多 PDF / Dataset，不要不断扩大 EC2 磁盘。

使用：

S3

存：

PDF
DOCX
TXT
CSV
Images
Datasets
第 3 步：Security Group

这里非常重要。

不要为了开发直接把 SSH 22、FastAPI 8000、PostgreSQL 5432 全开放到 Internet。

我们准备使用：

AWS Systems Manager Session Manager

这样可以通过 AWS 管理 EC2，而不是把 SSH 暴露到公网。

第 4 步：IAM Role

创建 EC2 时：

Advanced details → IAM instance profile

如果还没有 Role：

进入：

IAM → Roles → Create role

选择：

Trusted entity:
AWS service


Use case:
EC2

添加：

AmazonSSMManagedInstanceCore

Role 名：

EC2-LLM-Dev-Role

然后回到 EC2 创建页面选择：

EC2-LLM-Dev-Role
第 5 步：Launch Instance

现在：

Launch instance

等待：

Instance state = Running

然后进入：

EC2
→ Instances
→ llm-dev
第 6 步：进入 Ubuntu

点击：

Connect

选择：

Session Manager

然后：

Connect

如果成功，你会看到类似：

$ whoami
ssm-user

这意味着：

你已经进入 AWS 云端 Linux 开发环境。

第 7 步：检查 Ubuntu

执行：

uname -a

然后：

cat /etc/os-release

应该看到：

Ubuntu
24.04

再执行：

free -h

应该看到大约：

Mem:
3.7Gi

如果你使用 t3.medium。

第 8 步：更新系统

执行：

sudo apt update

然后：

sudo apt upgrade -y

安装开发工具：

sudo apt install -y \
    git \
    curl \
    wget \
    unzip \
    vim \
    htop \
    build-essential

检查：

git --version
curl --version
第 9 步：安装 Python

执行：

sudo apt install -y \
    python3 \
    python3-pip \
    python3-venv

检查：

python3 --version

然后：

pip3 --version
第 10 步：建立第一个 LLM 项目

执行：

mkdir -p ~/projects
cd ~/projects

创建项目：

mkdir llm-app
cd llm-app

创建 Python 虚拟环境：

python3 -m venv .venv

激活：

source .venv/bin/activate

现在执行：

which python

应该指向：

/home/ssm-user/projects/llm-app/.venv/bin/python
第 11 步：安装 FastAPI

执行：

pip install --upgrade pip

然后：

pip install fastapi uvicorn

检查：

pip list


第 12 步：创建 FastAPI

建立目录：

mkdir app

创建：

nano app/main.py

输入：

from fastapi import FastAPI


app = FastAPI(
    title="AWS LLM Application",
    version="1.0.0"
)


@app.get("/")
def root():
    return {
        "message": "AWS LLM Application is running"
    }


@app.get("/health")
def health():
    return {
        "status": "ok"
    }

保存：

CTRL + O
ENTER
CTRL + X
第 13 步：启动 FastAPI

执行：

uvicorn app.main:app --host 0.0.0.0 --port 8000

看到：

Uvicorn running on http://0.0.0.0:8000

说明 FastAPI 已经启动。

但是：

现在不要去 AWS Security Group 开放 8000。

我们下一步通过 Session Manager 做 Port Forwarding。

第 14 步：本地连接 AWS FastAPI

在你的 Windows 电脑上安装：

AWS CLI

然后配置：

aws configure

输入：

AWS Access Key ID
AWS Secret Access Key
Default region:
us-west-2

不过这里我更推荐后续使用 AWS IAM Identity Center / SSO，不要长期使用 root 或裸 Access Key。

第 15 步：Session Manager Port Forwarding

AWS Session Manager 支持端口转发，因此可以把 EC2 的：

8000

映射到你的 Windows：

localhost:8000

AWS 官方文档支持这种 Session Manager 会话方式。

概念上：

Windows
localhost:8000
       │
       │ Session Manager
       ▼
EC2
localhost:8000
       │
       ▼
FastAPI

这样你的 EC2 不需要公开：

8000
第 16 步：浏览器测试

你的 Windows 浏览器访问：

http://localhost:8000

应该看到：

{
    "message": "AWS LLM Application is running"
}

然后：

http://localhost:8000/health

应该：

{
    "status": "ok"
}

再访问：

http://localhost:8000/docs

你应该看到：

FastAPI Swagger UI

🎉 到这里，你已经完成：

AWS
 ↓
EC2
 ↓
Ubuntu
 ↓
Python
 ↓
FastAPI
 ↓
Browser

第 17 步：安装 Docker

停止 FastAPI：

CTRL + C

安装：

sudo apt install -y docker.io

启动：

sudo systemctl enable docker
sudo systemctl start docker

检查：

docker --version

测试：

sudo docker run hello-world

如果出现：

Hello from Docker!

Docker 正常。

第 18 步：让用户可以直接运行 Docker

执行：

sudo usermod -aG docker $USER

然后退出 Session Manager：
↳

exit

重新进入 EC2。

执行：

docker ps

如果不需要：

sudo docker ps

就说明配置成功。

第 19 步：把 FastAPI Docker 化

项目变成：

llm-app/
├── app/
│   └── main.py
├── .venv/
└── Dockerfile

创建：

nano Dockerfile

内容：

FROM python:3.12-slim


WORKDIR /app


COPY requirements.txt .


RUN pip install --no-cache-dir -r requirements.txt


COPY app ./app


EXPOSE 8000


CMD ["uvicorn", "app.main:app", "--host", "0.0.0.0", "--port", "8000"]

创建：

nano requirements.txt

内容：

fastapi
uvicorn[standard]
第 20 步：Build Docker Image

执行：

docker build -t aws-llm-app .

检查：

docker images

应该看到：

aws-llm-app

第 21 步：运行 Container

执行：

docker run -d \
    --name llm-app \
    -p 8000:8000 \
    aws-llm-app

检查：

docker ps

应该看到：

llm-app

查看日志：

docker logs llm-app

应该看到：

Uvicorn running
第 22 步：现在加入 LLM

这一步开始真正进入：

LLM Application Development

安装 OpenAI SDK：

pip install openai

同时加入：

requirements.txt
openai

然后：

docker build -t aws-llm-app .
第 23 步：不要把 API Key 写进 Python

千万不要这样：

client = OpenAI(
    api_key="sk-xxxxxxxx"
)

也不要：

GitHub
   ↓
.env
   ↓
API Key

正确架构：

AWS Secrets Manager
        ↓
      Secret
        ↓
     Container
        ↓
    Environment
        ↓
      LLM

开发阶段可以暂时使用环境变量。

例如：

export OPENAI_API_KEY="你的KEY"

代码：

import os
from openai import OpenAI


client = OpenAI(
    api_key=os.environ["OPENAI_API_KEY"]
)
第 24 步：创建 /chat

你的 FastAPI 最终变成：

GET /
GET /health
POST /chat

架构：

POST /chat
     ↓
FastAPI
     ↓
OpenAI / Bedrock
     ↓
LLM
     ↓
JSON response

这就是一个最基础的：

LLM Application Backend

第 25 步：下一阶段加入 RAG

你的项目会进一步变成：

                    ┌── OpenAI
                    │
FastAPI → LLM Agent ├── Claude
                    │
                    └── Bedrock
                         │
                         ▼
                       RAG
                         │
              ┌──────────┴─────────┐
              ▼                    ▼
         PostgreSQL             S3
         + pgvector

RAG：

PDF
 ↓
Document Loader
 ↓
Chunking
 ↓
Embedding
 ↓
pgvector
 ↓
Similarity Search
 ↓
Context
 ↓
LLM
 ↓
Answer

第 26 步：最终 AWS 架构

你最终可以升级到：

                   GitHub
                      │
                      ▼
              GitHub Actions
                      │
                      ▼
                  AWS ECR
                      │
                      ▼
              ECS Fargate
                      │
                      ▼
                  FastAPI
                      │
          ┌───────────┼────────────┐
          ▼           ▼            ▼
       Bedrock      OpenAI       Claude
          │
          ▼
        Agent
          │
      ┌───┴────┐
      ▼        ▼
     RAG      MCP
      │
      ▼
 RDS PostgreSQL
    + pgvector
      │
      ▼
      S3
      │
      ▼
 CloudWatch

这就已经不是“学习 AWS”，而是一个相当标准的 production-oriented LLM Application architecture。

我建议我们按 7 个阶段做
阶段	内容	结果
Phase 1	EC2 + Ubuntu + Python	云开发机
Phase 2	Docker + FastAPI	API Server
Phase 3	OpenAI / Bedrock	LLM App
Phase 4	PostgreSQL + pgvector	RAG
Phase 5	LangChain / LlamaIndex	AI Framework
Phase 6	Agent + MCP	AI Agent
Phase 7	ECR + ECS + GitHub Actions	Production
现在先做 Phase 1

你现在只需要完成：

AWS Account
    ↓
EC2 Ubuntu 24.04
    ↓
IAM Role
    ↓
Systems Manager
    ↓
进入 Ubuntu
    ↓
安装 Python

先不要创建 RDS、ECS、ECR、Bedrock，也不要买 GPU。

这样不会把 AWS 搞得过于复杂，也能避免不必要的费用。

如果你已经打开 AWS Console，我建议我们就按这个顺序一步一步实操；你完成一个步骤，把 AWS 页面截图或结果贴给我，我可以直接告诉你下一步点哪里、输入什么。


