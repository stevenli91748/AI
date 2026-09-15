# Bun + Elysia + React 19 + TanStack 全栈架构详解

这套技术栈的核心思想是：使用 Bun 统一 JavaScript/TypeScript 开发环境，Elysia 构建后端 API，React 19 构建前端界面，TanStack 负责前端路由、服务端数据缓存和状态管理。

它适合构建现代化的全栈 Web 应用，例如 AI 聊天系统、LLM 应用平台、SaaS 管理后台和实时数据应用。

但首先要明确一个重要问题：

TanStack 不是一个单独的路由和状态管理框架，而是一组相互独立、可以组合使用的工具。 其中 TanStack Router 负责路由，TanStack Query 负责服务端数据状态，TanStack Store 或其他状态库可以负责客户端状态。

## 一、整体架构

## 浏览器 Browser

React 19 + TypeScript

组件、表单、交互、UI 渲染

HTTP / JSON / SSE / WebSocket

### 前端应用层

TanStack Router

路由、参数、页面加载、导航

TanStack Query

API 请求、缓存、重试、失效刷新

React 状态

表单、弹窗、局部 UI 状态

TanStack Form（可选）

复杂表单、字段校验

## Bun Runtime + Elysia Backend

HTTP 服务、路由、参数校验、认证、业务逻辑

Elysia

API 路由、插件、类型推导

业务服务层

Service、权限、领域逻辑

### 数据与外部服务

PostgreSQL

Redis

LLM API

这里有一个容易忽略的架构细节：Bun 是后端的运行时，但也可以同时承担前端开发服务器、TypeScript 执行、包管理和构建任务。它不等于 Elysia，也不等于整个应用。


## 二、四个核心技术分别负责什么？

![Mastering Bun API Endpoints](https://images.openai.com/static-rsc-4/SM_SO2cZ20uxn7GLixWi0UchLBR-Cra9NQt4A0KXyLHvoXX3EIihdra_TLAowIwJP6gYVzPoXh1ThwyqLxYifKSqo6cn6VP7KDXjIirrSPZ4wZldu8Ja4ka-Mo2G5Nu22N1Bn-wBppfHl4xOoF9Cw_YVAAAqXkbAKpwLN7R7vqc?purpose=inline)

1. Bun

---

运行时与开发工具链

执行 TypeScript/JavaScript，安装依赖，运行测试，构建前端资源。Bun 使用 JavaScriptCore 引擎，并提供 Node.js 兼容能力，但并非所有 Node.js 行为都完全兼容。

![](https://www.google.com/s2/favicons?domain=https://bun.com\&sz=32)

Bun+1

![First Look At ElysiaJS. Building Modern APIs in the new Bun… | by Nishant Aanjaney Jalan | CodeX | Medium](https://images.openai.com/static-rsc-4/0f9uEtzTWYgoMlbiPPlEATHbcpEAft7pOT4RpX6dfSyoKL97XlwVuj5yauBDE922J-QdXG3hw-Zrs9VDdWzQ8PM73L4M5IF3bbSHB4Ux3H1AIiooY3bgWa0G9a5W1p1ZAj2uhugTWnQLMzos64_Ol1JTTw-qCI4pI-WA8ad0eH0?purpose=inline)

2. Elysia

---

后端 HTTP 框架

定义 API 路由、校验请求、执行业务逻辑、调用数据库和外部服务。它利用 TypeScript 类型系统提供较强的请求和响应类型推导。

![React Programming Course: Master Front-End Development ncr](https://images.openai.com/static-rsc-4/HN13ZE5p_tLVwapSS8g_Z1TFA0Qdc7TyxWMon-Pv4CTzkX8RZ5UwSqensns2VA60hokq-eCXBitKT10h7_ewzUEGfLIXHfBqePrFORPwIz2ddWAf2wr_GBgwstSNBaJKs-A8Zc_axiz9XMUrLJHiPum3af8Vu4dxR2Bb1v3KgWI?purpose=inline)

3. React 19

---

前端 UI 层

使用组件、Hooks 和 JSX 构建页面，处理用户输入、交互与界面更新。React 本身不负责完整的 URL 路由、API 缓存或后端业务。

![毎週数百万回ダウンロードされる人気JavaScriptライブラリ群「TanStack」にサプライチェーン攻撃、問題のあるバージョンをインストールした開発環境では認証情報流出の恐れ - GIGAZINE](https://images.openai.com/static-rsc-4/klaoVLscIXH6m0GOYIjcoLURRwykLS--2bRDl03P9CxQk71mJy4VAN1rHNL0bWGfaNtrQnnXcsw1XiZkh1t1zqzcAZ5NCFhCMF862QiMrXjPIPAqEukBU4LsrofKhbY9_3-mKKs_7w0IW7u1jSxsvEo5Qwf73iy3s8o8D1fMUMQ?purpose=inline)

4. TanStack

---

前端应用基础设施

通过 Router、Query、Form 等独立库，处理路由、数据请求、缓存、表单及页面数据加载。

## 三、为什么选择 Bun + Elysia？

这两个技术不是重复关系，而是上下层关系。

```
Bun Runtime
    │
    ├── 执行 TypeScript
    ├── 提供 HTTP 服务能力
    ├── 运行 Elysia
    │      ├── API 路由
    │      ├── 请求校验
    │      ├── 认证授权
    │      └── 业务逻辑
    │
    └── 运行测试、安装依赖、构建
```

### 1. Bun：运行时和工具链

在传统 Node.js 项目中，通常需要组合：

|
功能

|

传统 Node.js 项目

|

Bun 项目

|
| --- | --- | --- |
|

JavaScript 运行时

|

Node.js

|

Bun

|
|

包管理

|

npm / pnpm

|

bun install↳

|
|

TypeScript 执行

|

tsx / ts-node 等

|

原生转译执行

|
|

测试

|

Jest / Vitest 等

|

Bun Test

|
|

构建

|

esbuild / Vite 等

|

Bun Bundler 或 Vite

|

Bun 的优势是减少工具链组合和配置成本。它还支持工作区，适合前后端放在同一个 monorepo 中。

![](https://www.google.com/s2/favicons?domain=https://bun.com\&sz=32)

Bun+2

需要注意：Bun 原生转译 TypeScript 不代表它会进行完整的静态类型检查。生产项目仍应使用 `tsc --noEmit` 或等效工具进行类型检查。

![](https://www.google.com/s2/favicons?domain=https://bun.net.cn\&sz=32)

Bun Docs - Bun 运行环境+1

### 2. Elysia：轻量、类型优先的后端框架

Elysia 的典型开发模式是通过链式 API 定义路由：

TypeScript

```
import { Elysia, t } from "elysia";

const app = new Elysia()
  .get("/api/health", () => ({
    status: "ok",
  }))
  .post(
    "/api/users",
    ({ body }) => ({
      id: crypto.randomUUID(),
      name: body.name,
    }),
    {
      body: t.Object({
        name: t.String(),
      }),
    },
  )
  .listen(3000);
```

这里的核心是：

* `get()`：定义 GET 接口。

* `post()`：定义 POST 接口。

* `t.Object()`：声明并校验请求数据结构。

* `body`：从经过校验的请求中获取数据。

* `listen()`：启动 HTTP 服务。

这种设计适合 TypeScript 全栈开发，因为接口定义、请求类型和响应类型可以集中在后端代码中。

但要注意，Elysia 的类型推导不能代替身份认证、权限校验、业务规则和数据库约束。类型安全不等于业务安全。


## 四、React 19 + TanStack：前端如何分工？

TanStack 不是一个整体框架。推荐先理解下面四个库的边界。

## TanStack Router

路由

管理 URL、页面层级、动态参数、搜索参数、导航和页面加载。

例如：

`/projects/123` → 项目详情页面。

`?tab=files` → 当前页面打开文件标签。

## TanStack Query

服务端状态

管理 API 请求、数据缓存、后台刷新、重试、分页、乐观更新和缓存失效。

例如：项目详情、用户资料、订单列表。

## TanStack Form

表单

管理复杂表单的字段状态、校验、提交及错误信息。

例如：注册、用户资料编辑、项目创建。

## TanStack Store

客户端状态

可用于需要独立响应式状态容器的场景。但不需要因为采用 TanStack 就强制使用 Store。

官方文档：

* TanStack Router 文档 

* TanStack Query 文档 

* TanStack Form 文档 

* TanStack Store 文档 

### 1. 最关键的区别：服务端状态与客户端状态

这是整套架构中最重要的设计原则。

|
状态类型

|

推荐管理方式

|

示例

|
| --- | --- | --- |
|

URL 状态

|

TanStack Router

|

当前项目 ID、搜索条件、分页

|
|

服务端状态

|

TanStack Query

|

用户信息、项目列表、订单数据

|
|

组件局部状态

|

React `useState`

|

弹窗开关、输入框展开

|
|

复杂表单状态

|

TanStack Form

|

字段值、验证错误、提交状态

|
|

跨组件客户端状态

|

Context / Zustand / TanStack Store

|

主题、复杂工作流状态

|

例如，一个项目管理页面：

* 当前项目 ID 存在 URL。

* 项目详情来自 API，使用 Query 缓存。

* 编辑弹窗是否打开，使用 React 状态。

* 编辑表单字段，使用 Form。

* 不需要把项目详情再复制到一个全局 Zustand Store 中。

否则很容易产生两个数据源：Query 中的项目数据已经更新，而全局 Store 仍然保留旧值。

## 五、完整请求流程：从用户点击到数据库

以一个 AI 聊天应用为例。

1. 用户进入聊天页面

   浏览器 URL 为 `/chat/123`，TanStack Router 匹配路由，并读取聊天 ID。

2. 页面获取历史消息

   TanStack Query 根据 `["chat", "123", "messages"]` 查询缓存；缓存不存在或需要刷新时，调用后端 API。

3. React 渲染聊天记录

   Query 将消息数据提供给 React 组件，React 更新聊天界面。

4. 用户发送消息

   React 处理输入和按钮点击，通过 API Client 向 Elysia 发送 POST 请求。

5. Elysia 处理请求

   校验输入、检查用户身份和权限、执行聊天业务逻辑。

6. 调用 LLM 并保存数据

   后端调用 OpenAI 或其他模型 API，将用户消息及模型回复保存到数据库。

7. 返回结果并刷新页面数据

   后端返回响应，前端更新消息列表，并根据需要失效 Query 缓存。

这套流程有一个优势：前端不需要知道数据库结构，也不需要知道 LLM API 密钥。

前端只需要调用自己的后端 API。

### 实际的代码调用关系

```
ChatPage.tsx
    │
    ├── useParams()
    │     └── chatId = "123"
    │
    ├── useQuery()
    │     └── api.chat.getMessages(chatId)
    │               │
    │               ▼
    │         GET /api/chats/123/messages
    │               │
    │               ▼
    │            Elysia
    │               │
    │               ▼
    │          ChatService
    │               │
    │               ▼
    │          PostgreSQL
    │
    └── useMutation()
          └── api.chat.sendMessage(...)
```


## 六、推荐的项目目录结构

对于中型以上的全栈应用，建议使用 Monorepo，将前端、后端、共享类型分开管理。

my-fullstack-app/

apps/

web/

src/routes/ — TanStack Router 路由

src/components/ — React 组件

src/features/ — 页面业务模块

src/lib/api.ts — API Client

src/lib/query.ts — Query 配置

api/

src/routes/ — Elysia API 路由

src/services/ — 业务服务

src/repositories/ — 数据访问

src/plugins/ — 认证、日志等插件

src/index.ts — 服务启动入口

packages/

contracts/ — 共享 API 类型与契约

config/ — 共享 TypeScript 配置

ui/ — 可复用 React 组件（可选）

package.json、bun.lock、tsconfig.json

### 为什么要分开 contracts？

因为共享类型不应该让浏览器直接依赖后端实现。

例如，后端可以使用 Elysia 定义请求和响应类型，然后通过受控的共享包暴露给前端。

```
Backend Elysia
      │
      ▼
  API Contracts
      │
      ▼
Frontend API Client
      │
      ▼
  React Components
```

不要把数据库实体、数据库连接、环境变量或者服务端密钥直接导入前端。

## 七、Elysia 与 TanStack Router 如何选择？

这里有两种不同的路由，不能混为一谈。

|
对比

|

TanStack Router

|

Elysia Router↳

|
| --- | --- | --- |
|

运行位置

|

浏览器或全栈服务端

|

后端

|
|

负责什么

|

页面路由

|

HTTP API 路由

|
|

典型路径

|

`/dashboard`

|

`/api/users`

|
|

主要对象

|

页面、组件、URL 参数

|

请求、响应、业务逻辑

|
|

是否互相替代

|

否

|

否

|

如果使用 React 19 + TanStack Router + Elysia，完全可以同时拥有：

```
浏览器页面：
/dashboard
/projects/123
/chat/123

后端 API：
/api/projects
/api/projects/123
/api/chats/123/messages
```

用户访问 `/projects/123`，由 TanStack Router 决定显示哪个 React 页面；该页面再调用 Elysia 的 `/api/projects/123` 获取数据。

## 八、生产环境架构：CSR、SSR 与部署

这是选型时必须考虑的部分。

### 方案 A：React SPA + Elysia API

React 19 + TanStack Router / Query

Elysia API + Bun

PostgreSQL / Redis / LLM

适合：

* AI 聊天应用

* 内部管理系统

* SaaS 控制台

* 需要登录的业务系统

前端可以构建为静态资源，由 CDN 或静态托管服务提供；后端作为独立的 Bun 服务运行。

这是我对初学者和大多数业务应用最推荐的方案。

### 方案 B：TanStack Start 全栈 SSR

如果需要服务端渲染、SEO、服务端页面加载和完整的 React 全栈体验，可以考虑 TanStack Start。

TanStack Start 与 TanStack Router 有直接关系，但它不是简单地把 Elysia 替换成另一个路由库，而是提供自己的全栈应用模型。

Bun 官方部署指南也提供了 TanStack Start 的 Bun 部署方式，但其 Bun 专用部署说明要求 React 19 或更高版本。

![](https://www.google.com/s2/favicons?domain=https://tanstack.com\&sz=32)

TanStack Start React Docs+1

适合：

* SEO 要求较高的网站

* 内容平台

* 需要 SSR 的产品网站

* 希望前后端采用统一全栈框架的项目

如果你的项目已经采用 Elysia 作为独立后端，那么没有必要仅仅为了 SSR 就强行迁移到 TanStack Start。两者可以根据业务需要组合，但需要明确谁负责页面渲染、API 和服务端数据加载。

## 九、这套架构的优势与风险

优势

* 前后端统一 TypeScript，降低接口类型不一致的问题。

* Bun 工具链简洁，适合快速开发和统一管理依赖。

* Elysia 适合构建轻量 API 服务。

* TanStack Router 和 Query 分工清晰，便于维护大型前端应用。

* Monorepo 便于共享类型、测试和代码复用。

风险与注意事项

* Bun 对 Node.js 的兼容性仍需针对项目依赖进行验证。

* TanStack Query 缓存必须设计失效规则，避免显示过期数据。

* Elysia 的类型校验不等于认证、授权或数据库约束。

* 需要区分前端状态、服务端状态和 URL 状态。

* 生产环境要验证数据库驱动、监控、日志、部署和故障恢复。

## 十、最终技术选型建议

如果你要开发一个现代化的 AI 应用，我建议采用以下组合：

|
层级

|

推荐技术

|
| --- | --- |
|

Runtime

|

Bun

|
|

后端框架

|

Elysia

|
|

前端 UI

|

React 19

|
|

前端路由

|

TanStack Router↳

|
|

服务端数据缓存

|

TanStack Query↳

|
|

表单

|

TanStack Form（需要时）

|
|

API 类型安全

|

Elysia Eden Treaty 或共享契约

|
|

数据库

|

PostgreSQL↳

|
|

ORM

|

Drizzle ORM

|
|

缓存

|

Redis（需要时）

|
|

测试

|

Bun Test + 前端组件测试

|
|

部署

|

Docker + AWS↳

|

Elysia 的类型系统可以与 Eden Treaty 结合，让前端以类型安全的方式调用后端 API；但这不意味着运行时就不需要验证请求和响应。

结论： 这套架构最有价值的地方，不是单纯追求 Bun 的运行速度，而是建立一条清晰的全栈开发链路：Bun 统一工具环境，Elysia 提供类型化 API，React 19 负责界面，TanStack 负责页面路由与数据状态。对于你要开发的 AI / LLM 应用，它是一个值得学习和实践的现代 TypeScript 全栈方案。
