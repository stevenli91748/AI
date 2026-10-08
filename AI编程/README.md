# 参考书
  * [英文软件开发教程系列](https://www.youtube.com/@BroCodez/courses)
  * [Markdown：大语言模型时代的通用语言](https://weread.qq.com/web/reader/750324c0813aba690g01140e)
  * [白话AI编程：从入门到实践](https://weread.qq.com/web/reader/f9832840813abb79bg014e82kc81322c012c81e728d9d180)
  * [Claude Code橙皮书：AI编程实战](https://weread.qq.com/web/reader/2a132590813abbb26g019d57kc81322c012c81e728d9d180)
# 目录
* AI 应用主流技术架构
  * [美国 AI 全栈应用主流技术架构（2026）]()
* ClaudeCode的所有能力，其实可以归入3个层次，工程的三层架构---prompt（提示词）​、context（上下文）​、harness（承载Claude Code运行的整个外部环境——CLAUDE.md、skill、hook、MCP、project结构都在这一层)
  * 提示词工程---  它有效，但每次都需要你手动输入，每次都从零开始
    * 系统提示词
      * [system-prompts-and-models-of-ai-tools 例子](https://github.com/x1xhlol/system-prompts-and-models-of-ai-tools)  
  * [context（上下文工程)---Claude Code在回答之前所“看到”的所有信息，包括CLAUDE.md文件、项目的文件结构、Git提交历史、package.json中的依赖列表等。这些信息不需要你每次重复提供，Claude Code会自动读取](https://weread.qq.com/web/reader/2a132590813abbb26g019d57kc51323901dc51ce410c121b)
  * harness（承载Claude Code运行的整个外部环境——CLAUDE.md、skill、hook、MCP、project结构都在这一层,ClaudeCode提供了3种扩展机制，分别解决不同层面的问题。：你搭建的自动化环境。skill把常用工作流封装成可复用的指令；hook让特定事件自动触发操作；MCP可以连接外部服务；Agent Teams让多个Claude Code智能体并行协作。这一层的特点是一旦搭建完成，就一直工作，不需要你每次手动触发)
    * [CLAUDE.md](https://weread.qq.com/web/reader/2a132590813abbb26g019d57kc20321001cc20ad4d76f5ae)
    * claude code的扩展能力---skill、hook与MCP这3种扩展机制，让Claude Code从一个终端工具变成一个可以无限生长的工作台
      * [skill （Markdown指令包，领域知识，可复用工作流，skill教ClaudeCode怎么做事）](https://weread.qq.com/web/reader/2a132590813abbb26g019d57k9bf32f301f9bf31c7ff0a60)
        * 知识型skill：告诉Claude Code“这个项目里的事情应该怎么做”​，比如API规范、编码风格、项目约定
        * 工作流型skill：告诉Claude Code“遇到特定任务按什么步骤执行”​，比如/fix-issue（修复bug的标准流程）​、/review-pr（代码审查流程）​。这类skill更像SOP（标准操作流程）​，有明确的步骤
          和检查点
          * 工作流型skill的关键配置：禁止自动触发:  disable-model-invocation: true
      * [hook (shell 脚本钩子，格式化，LINT, 安全，hook在关键节点自动执行检查,不是建议，是强制执行,CLAUDE.md是建议，hook是强制执行 )](https://weread.qq.com/web/reader/2a132590813abbb26g019d57k9bf32f301f9bf31c7ff0a60)
      * [MCP (外部工具连接器，数据库，API，第三方工具，MCP把外面的世界接进来)](https://weread.qq.com/web/reader/2a132590813abbb26g019d57k9bf32f301f9bf31c7ff0a60)
        * 实用的MCP资源整合平台
          * 国内 
            * ModelScope MCP广场---阿里巴巴旗下的开源社区
            * 阿里云百炼MCP
            * 百度MCP广场
            * 火山引擎MCP---字节跳动旗下的MCP平台
          * 国外
            *  MCP.so：这是由国内知名独立开发者idoubi（艾逗笔）开发的网站，是目前全球访问量较大的MCP资源整合平台之一，收录了大量MCP Server
            *  Smithery.ai：这个平台的核心功能是Leaderboard
            *  ·Anthropic官方仓库：前面介绍过，MCP是由Anthropic提出的，可想而知这个官方仓库的含金量。
            *  ·Reddit的MCP子社区：Reddit是一个全球知名的社交新闻聚合与讨论平台，用户可根据自己的兴趣加入不同主题的子社区
    * project结构 
* Rules
  * 实用的Rules资源平台
    * [这个项目收录了多技术领域的大量优质Rules Sample，包括但不限于前端框架和库、后端、移动开发、数据库、API，以及特定编程语言等](https://github.com/PatrickJS/awesome-cursorrules) 
    * [这个项目收录Rules的逻辑与常规分类有所不同，它按照开发中的具体环节或流程来分类](https://github.com/steipete/agent-rules)
    * [知名的两个资源站 https://cursor.directory/](https://cursor.directory/)
    * [知名的两个资源站 https://cursorlist.com/](https://cursorlist.com/)
    * Reddit
    * 稀土掘金
* [plugin](https://weread.qq.com/web/reader/2a132590813abbb26g019d57k9bf32f301f9bf31c7ff0a60)
* [Command--- Claude Code读取提示词之前，command先运行一些shell命令，把结果嵌入](https://weread.qq.com/web/reader/2a132590813abbb26g019d57k9bf32f301f9bf31c7ff0a60)
* [worktree---worktree允许你手动管理多个并行智能体](https://weread.qq.com/web/reader/2a132590813abbb26g019d57kc7432af0210c74d97b01b1c)
* [subagent---subagent可以为主智能体调用专家](https://weread.qq.com/web/reader/2a132590813abbb26g019d57kc7432af0210c74d97b01b1c)
* [Agent Teams---多个智能体可以互相通信、协调分工](https://weread.qq.com/web/reader/2a132590813abbb26g019d57kc7432af0210c74d97b01b1c)
* [ 远程控制](https://weread.qq.com/web/reader/2a132590813abbb26g019d57kc7432af0210c74d97b01b1c)
* [ 异步执行](https://weread.qq.com/web/reader/2a132590813abbb26g019d57kc7432af0210c74d97b01b1c)
* 版本控制
  * [单机模式](https://weread.qq.com/web/reader/f9832840813abb79bg014e82kc20321001cc20ad4d76f5ae)
  * [联网模式](https://weread.qq.com/web/reader/f9832840813abb79bg014e82kc20321001cc20ad4d76f5ae)   
