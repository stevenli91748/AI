* 按照2026美国现在的企业开发方式学习，我建议你的技术路线直接变成：

Next.js → FastAPI → PostgreSQL → LLM API → RAG → Tool Calling → MCP → Skills → Agent → Workflow → LangGraph → Production

这比单纯学习“LangChain Agent”更符合现在的企业 AI Application 架构方向。


* 核心技术
  * Transformer架构：是LLM的基础架构，它引入了自注意力机制（Self-Attention），能够并行计算并高效处理长序列数据，捕捉文本中的长期依赖关系，相比传统的循环神经网络（RNN）和卷积神经网络（CNN），在语言理解和生成方面具有更大的优势。
  * 预训练-微调范式
    * 预训练：在大规模无监督文本数据上进行预训练，学习语言的通用特征和知识，例如学习单词、短语、句子之间的关系，理解语言的语法、语义和语用规则等。
    * 微调：在预训练的基础上，针对具体的任务和领域，使用少量的有标注数据进行微调，使模型适应特定任务的需求，提高在具体任务上的性能。
    
* 主要应用
  * 内容创作：可以生成文章、故事、诗歌、代码等各种文本内容，为创作者提供灵感和辅助。
  * 智能客服：能够理解用户的问题并给出准确、自然的回答，提高客服效率和用户满意度。
  * 机器翻译：将一种语言翻译成另一种语言，凭借其强大的语言理解和生成能力，提升翻译质量和效率。
  * 智能助手：如语音助手等，能够与用户进行自然流畅的对话，帮助用户完成各种任务，如查询信息、设置提醒等。

* LLM、AIGC、AI AGENT之间的关系
LLM（Large Language Model，大型语言模型）、AIGC（AI Generated Content，人工智能生成内容）、AI Agent（智能体）之间存在着紧密而又相互区别的关系，具体如下：



**AI Agent , MCP , RAG 三者关系**
**RAG = 检索增强生成,它解决的问题：LLM(GPT) 不知道你的企业内部数据, 通过它把企业内部数据放到Vector Database中，并跟据 “用户提问“ 通过Vector Search找到相关内容，把相关内容作为GPT的输入输据**
**MCP= AI 与外部工具通信的标准协议,MCP 提供统一方式**


**Agent->MCP->Oracle->RAG ( PDF原始数据->切块Chunk->Embedding->Vector Database->用户提问->Vector Search->找到相关内容 )->LLM（GPT）->回答**



# [AI 开发工具](https://github.com/stevenli91748/AI/blob/master/AI%E5%BC%80%E5%8F%91%E5%B7%A5%E5%85%B7/2026%E5%B9%B4Vibe%20Coding%20%E5%BC%80%E5%8F%91%E5%B7%A5%E5%85%B7.md)

# 自然语言 LLM 学习路径

![自然语言 LLM 学习路径](https://github.com/stevenli91748/AI/blob/master/%E8%87%AA%E7%84%B6%E8%AF%AD%E8%A8%80%E5%A4%84%E7%90%86%E5%AD%A6%E4%B9%A0%E8%B7%AF%E5%BE%84.png )

# 在线书籍
  * [神书  从零构建大型语言模型](https://www.scribd.com/document/763076237/%E4%BB%8E%E9%9B%B6%E6%9E%84%E5%BB%BA%E5%A4%A7%E8%AF%AD%E8%A8%80%E6%A8%A1%E5%9E%8B-%E4%B8%AD%E6%96%87%E7%89%88)

由于AI大模型的发展日新月异，所以选取的书籍基本都是新近出版的，而且尽量在较新的书籍中选择豆瓣评分高的。

LangChain
李特丽：《LangChain入门指南：构建高可复用、可扩展的LLM应用程序》【2024出版】
李多多：《LangChain编程》【2024出版】
张海立：《LangChain实战：从原型到生产，动手打造 LLM 应用》【2024出版】
刘伟舟：《LangChain简明讲义：从0到1构建LLM应用程序》【2024出版】

AI大模型
张奇：《大规模语言模型：从理论到实践》【2024出版】
奥利维耶·卡埃朗：《大模型应用开发极简入门》【2024出版】
杨青：《大语言模型：原理与工程实践》【2024出版】
熊涛：《大语言模型：基础与前沿》【2024出版】
刘阳：《多模态大模型：新一代人工智能技术范式》【2024出版】
[法]丹尼斯·罗斯曼：《基于GPT-3、ChatGPT、GPT-4等Transformer架构的自然语言处理》【2024出版】
郝少春：《ChatGPT原理与应用开发》【2024出版】
王晓华：《从零开始大模型开发与微调：基于PyTorch与ChatGLM》【2023.11出版】
黄佳：《GPT图解大模型是怎样构建的》【2023.12出版】
尤洋：《实战AI大模型》【2023.11出版】

# 学习例子项目
* 开发工具
  * 前端开发工具
    *  
  * [AI编程幻觉终结者 TDD+重构驱动的单元测试实战课2026---解压密码:itdjs.com@#.20260207](https://www.itdjs.com/8664/html)
  * Claude Code
    * [AI编程革命！Claude Code Workflow自动生成Harness！彻底抹平Harness Engineering技术鸿沟！ultrawork自动召唤cc神级功能自动多Agent编程开发！](https://www.youtube.com/watch?v=8gOOlBcdrIo)
    * [程序员必备设计神器！Claude Code原生支持Claude Design！一个/design命令，从UI原型到代码同步，全流程演示，AI设计到开发终于闭环了！小白也能做精美UI！挑战Figma！](https://www.youtube.com/watch?v=5jXwHYfccvw)
  * java AI
    * [体系课Java+AI全栈开发工程师2026---课程用AI全程辅助开发  解压密码itdjs.com@#20260801 ](https://www.itdjs.com/9107/html) 
    * [ LLM大模型智能引擎实战–SpringAI+RAG+MCP+实时搜索](https://www.itdjs.com/7952/html) 
    * [Java大模型工程能力必修,LangChain4j实战AI智能体](https://www.itdjs.com/8212/html)
    * []()
* AI 数学
  * [深入AI/大模型必修数学体系2026](https://www.itdjs.com/8639/html) 
* [动手学大模型应用开发例子1](https://datawhalechina.github.io/llm-universe/#/)
* [动手学大模型应用开发例子2](https://www.cnblogs.com/longronglang/category/2442713.html)
* [知乎AI大模型应用专家实战训练营十八期2026 对大模型技术全面讲解 ](https://www.itdjs.com/9034/html)
* AI API
  * [ 众创AI大模型应用开发实战---完成 AI大模型开发环境搭建 OpenAI接口调用、工具适配 想要入门 AI 大模型应用开发的编程新手](https://www.itdjs.com/9048/html)
  * [Gemini3.0 实战训练营234期合集2026---](https://www.itdjs.com/8890/html)
* CURSOR
  * [零基础学Cursor从需求到上线全流程实战](https://www.itdjs.com/8895/html)
  * []() 
* 私有化部署
  * [51CTO-DeepSeek+dify+ollama三剑客，从理论到实战  解决私有化部署、成本控制、中文场景适配等难题](https://www.itdjs.com/9065/html)
  * [本地快速安装运行史上最强开源LLaMa3大模型](https://liaoxuefeng.com/blogs/all/2024-05-06-llama3/index.html)
* OpenClaw
  * [OpenClaw+Hermes 双模型：AI 私有化部署与实战落地](https://www.itdjs.com/9012/html)
  * [产品经理的AI分身：用OpenClaw实现一人顶三人的高效工作法](https://www.itdjs.com/9016/html)
  * [小龙虾openclaw-Al一人公司实战训练营-从部署到创收](https://www.itdjs.com/8829/html)
* 多模态
  * [多模态大模型训练营](https://www.itdjs.com/8939/html)
  * []()
* RAG
  * [RAG全栈技术从基础到精通 ，打造高精准AI应用](https://www.itdjs.com/7527/html)
  * [AI智能体（Agent）开发实战：工业级项目案例驱动课2026---课程融合LangGraph多智能体开发框架与GraphRAG知识图谱方案](https://www.itdjs.com/8846/html)
  * [工业级实战：从传统RAG到Agentic RAG的进阶优化！](https://www.youtube.com/watch?v=UZs_yOKcw7A)
* Llama3
  * [Llama3大模型原理代码精讲与部署微调评估实战](https://www.itdjs.com/8460/html)
  * [LLama实战本地CPU推理大语言模型-C++开发实战](https://www.itdjs.com/8139/html)
* AI Agent
  * [26年Agent开发工程师需要什么能力](https://www.youtube.com/watch?v=oBy94l_48CQ) 
  * [工业级实战：从传统RAG到Agentic RAG的进阶优化！](https://www.youtube.com/watch?v=UZs_yOKcw7A) 
  * [AI Agent+MCP从0到1打造商业级编程智能体2026---从零写一个能自己规划任务、自己调工具、自己写代码、自己部署上线的编程智能体](https://www.itdjs.com/8049/html)
  * [AI智能体（Agent）开发实战：工业级项目案例驱动课2026---融合LangGraph多智能体开发框架与GraphRAG知识图谱方案](https://www.itdjs.com/8846/html)
  * [Agent Skills 做知识库检索，能比传统 RAG 效果更好吗？](https://www.youtube.com/watch?v=YL-BgiruIe0)
  * [构建生产级Agent Memory的系统架构](https://www.youtube.com/watch?v=rDTUDnPwUa0)
  * [Agent记忆框架怎么选？5大Agent Memory项目工程级横向对比，哪一种才是未来Agent记忆的标准答案 ？](https://www.youtube.com/watch?v=BVwpVRpbph4)
  * [从Workflow到Agent, 你真正需要的是---解析Agent的发展路径是如何演进的](https://www.youtube.com/watch?v=nBvtDzr6ijc)
* 提示词工程+大模型NLP应用+AI对话产品
  * [大模型AI应用开发企业级项目实战（提示词工程+大模型NLP应用+AI对话产品）](https://www.itdjs.com/8850/html)
  * [AI时代人人必修课-提示词工程+大语言模型 多场景实战](https://www.itdjs.com/7091/html)
* LLM推理优化
  * [ LLM推理优化与部署实战2026](https://www.itdjs.com/8761/html)
* N8N
  * [N8N AI自动化大师课：从零构建企业级工作流---从 0 到 1 带你搭建完整的自动化系统](https://www.itdjs.com/8596/html)  
* MCP
  * [大模型MCP技术实战课2025---系统拆解AI智能体开发全流程！从Agent底层逻辑、Function Call优化策略，到MCP环境搭建与服务端开发，手把手带你构建高可用客户端和服务端架构。深入剖析复杂智能体的数据库设计、多服务协同（SQL/Python）、并行/串行调用等硬核技术](https://www.itdjs.com/8199/html)
  * [MCP+GraphRAG+LLM的智能体全栈开发](https://www.itdjs.com/8172/html)
  * [MCP 从入门到多场景全链路实战](https://www.itdjs.com/8156/html)
  * [用过上百款编程MCP，只有这15个真正好用，Claude Code与Codex配置MCP详细教程](https://www.youtube.com/watch?v=UW5iQGE3264)
* 微调
  * [领域大模型微调案例课](https://www.itdjs.com/8116/html)
  * [如何把你的 DeepSeek R1 微调为某个领域的专家？（理论篇）](https://www.youtube.com/watch?v=cgRDs1iUDSM)
  * [如何把你的 DeepSeek R1 微调为某个领域的专家？（实战篇）](https://www.youtube.com/watch?v=pYAARaPG48k)
  * [想微调特定领域的大模型，数据集究竟要怎么搞](https://www.youtube.com/watch?v=C7euxRVw3JQ)
  * [如何把领域文献批量转换为可供模型微调的数据集](https://www.youtube.com/watch?v=usYzmXLvXXc)
  * [Easy Dataset 最新功能解读，以及几个数据集构建实战案例](https://www.youtube.com/watch?v=BZDXu9yGxJg)
  * [手把手教你从零微调一个专属领域大模型，零基础也能学会](https://www.youtube.com/watch?v=sE12haEVREY)
  * [LLaMA Factory微调教程（4） 如何观测模型的微调过程？微调后的模型如何合并导出和部署？](https://www.youtube.com/watch?v=UNhotbyZdf0)
  * [LLaMA Factory微调教程（3） 微调模型的各种参数到底怎么搞？如何优化显存消耗](https://www.youtube.com/watch?v=ducyWMh-aIg)
  * [LLaMA Factory微调教程（2） LLaMA Factory 微调教程：如何构建高质量数据集？](https://www.youtube.com/watch?v=wTW0NccRXtI)
  * [LLaMA Factory微调教程（1） 纯本地！零代码！一站式完整数据集准备到模型微调全流程！](https://www.youtube.com/watch?v=0-CdIF7n4-4)
* AI大模型全栈测试
  * [AI大模型全栈测试课程2025](https://www.itdjs.com/8009/html)   

* 三高（高性能、高可用、高扩展性）AI工程体系
  * [Ai工程化项目实战营2026---通过构建“三高”（高性能、高可用、高扩展性）AI工程体系，目标是全面提升你的AI项目研发与工程化能力  解压密码:itdjs.com@#20260202](https://www.itdjs.com/8647/html)
# 博客

[白白说大模型](https://www.youtube.com/@%E7%99%BD%E7%99%BD%E8%AF%B4%E5%A4%A7%E6%A8%A1%E5%9E%8B)|[马克的技术工作坊](https://www.youtube.com/@%E9%A9%AC%E5%85%8B%E7%9A%84%E6%8A%80%E6%9C%AF%E5%B7%A5%E4%BD%9C%E5%9D%8A)|[AI超元域](https://www.youtube.com/@AIsuperdomain)|[code秘密花园](https://www.youtube.com/@garden-conard)|
---|---|---|---|

[我开源了一个 Skill，把项目经验沉淀成可复用的知识](https://www.youtube.com/watch?v=HcbjFO1mRIw)|
---|


[动手学大模型应用开发---github](https://github.com/datawhalechina/llm-universe)|[llm-action](https://github.com/liguodongiot/llm-action)|[3Blue1Brown](https://www.youtube.com/c/3blue1brown)| [Datawhale人工智能培养方案](https://github.com/datawhalechina)|[面向开发者的LLM手册](https://datawhalechina.github.io/llm-cookbook/#/)|
---|---|---|---|---|

[githut 上最多人的LLM学习课程](https://github.com/mlabonne/llm-course)|[AI大模型学习资料](https://www.cnblogs.com/bigai/articles/18187946)|[GitHub狂飙3万star的LLM公开资料 - 大模型入门教程](https://zhuanlan.zhihu.com/p/686277638)|
---|---|---|

# 目前推荐 3 个机构。 小白 ai+咪咕+手写 ai+聚客  
  * [小飞有点东西---python学习视频  每个视频只有几分钟，通俗易懂](https://space.bilibili.com/1803865534?spm_id_from=333.337.0.0)
  * 小白 ai：  包含一系列让你明白 ai 的原理
    * [入门篇：90 分钟！清华博士带你一口气搞懂人工智能和神经网络](https://www.bilibili.com/video/BV1atCRYsE7x/?clienttype=8&version=7.57.0.102&from=win32_yunguanjia&spm_id_from=333.337.search-card.all.click&vd_source=8aac1f6a5918d89a4405394c75c127ef&channel=00000000000000000000000040000001&privilege=&pri_extra=)
  * [从编解码和词嵌入开始，一步一步理解 Transformer，注意力机制(Attention)的本质是卷积神经网络(CNN)](https://www.bilibili.com/video/BV1XH4y1T76e/?clienttype=8&version=7.57.0.102&from=win32_yunguanjia&spm_id_from=333.788.player.switch&vd_source=8aac1f6a5918d89a4405394c75c127ef&channel=00000000000000000000000040000001&privilege=&pri_extra=
  * [手写 ai  提取码: rqsh](https://pan.baidu.com/s/1rNUrfQEhzrlnjS-fcu9Xsw#list/path=%2F&parentPath=%2Fsharelink4252786448-618212488618893)
  * [18-LLM-模型  提取码: q55u](https://pan.baidu.com/s/1ANUBJGZbXx3wDajQoDEAvQ#list/path=%2F&parentPath=%2Fsharelink4252786448-1058866667290512)
  * 聚客AI
    * [聚客AI官网](https://www.guangjuke.com/)
    * [聚客AI最详细的大模型学习路线！手把手教你最高效的大模型学习方法](https://www.bilibili.com/video/BV12oUXYsEbp/?spm_id_from=333.337.search-card.all.click&vd_source=2e815885181376606e6c241ba03c8907)
    * [重磅 【聚客AI】 大模型项目实战，顶尖的大模型项目，老师非常有经验](https://www.bilibili.com/video/BV1vKKpefEfC/?spm_id_from=333.337.search-card.all.click)
* [大模型基础: 一文了解大模型基础知识](https://github.com/datawhalechina/so-large-lm?tab=readme-ov-file)
* [开源的中文大语言模型，以规模较小、可私有化部署、训练成本较低的模型为主，包括底座模型，垂直领域微调及应用，数据集与教程等](https://github.com/HqWu-HITCS/Awesome-Chinese-LLM)
* [别再花钱学大模型了，推荐几个免费高质量大模型学习平台](https://zhuanlan.zhihu.com/p/1900586391215268776)
* [9个学习AI的网站（免费自学人工智能必备）](https://www.xue8nav.com/2090.html)
* [自学 AI 大模型的学习路线推荐---强](https://www.bilibili.com/video/BV12uY7eiEpG?spm_id_from=333.788.recommend_more_video.14&vd_source=2e815885181376606e6c241ba03c8907)
* [AI大模型学习路线](https://www.bilibili.com/video/BV15Y6JYWE6u/?spm_id_from=333.337.search-card.all.click&vd_source=2e815885181376606e6c241ba03c8907)
* [一个月吃透人工智能学习路线---唐宇迪](https://www.bilibili.com/video/BV1p4NGerEwJ?spm_id_from=333.788.videopod.episodes&vd_source=2e815885181376606e6c241ba03c8907&p=2)
* [2025年最新大模型学习路线，零基础到精通一条龙（基础/进阶/实战）](https://www.bilibili.com/video/BV1K8QVYHEoP/?spm_id_from=333.1007.tianma.53-2-208.click&vd_source=2e815885181376606e6c241ba03c8907)
* [8年经验告诉你，学AI的顺序千万别搞反了！初学者必看，少走弯路](https://www.bilibili.com/video/BV1Ya4heiEUq/?spm_id_from=333.337.search-card.all.click&vd_source=2e815885181376606e6c241ba03c8907)
  * [聚客AI官网](https://www.guangjuke.com/)
  * [聚客AI最详细的大模型学习路线！手把手教你最高效的大模型学习方法](https://www.bilibili.com/video/BV12oUXYsEbp/?spm_id_from=333.337.search-card.all.click&vd_source=2e815885181376606e6c241ba03c8907)
  * [重磅 【聚客AI】 大模型项目实战，顶尖的大模型项目，老师非常有经验](https://www.bilibili.com/video/BV1vKKpefEfC/?spm_id_from=333.337.search-card.all.click)
* [ZOMI酱---AI 很多大模型的新技术讲解 非常好](https://space.bilibili.com/517221395/lists)
* LangChain
  * [LangChain官方网站 ](https://www.langchain.asia/)
  * [LangChain中文网1](https://www.langchain.com.cn/)
  * [LangChain中文网2](http://docs.autoinfra.cn/)
  * [从零玩转Langchain4j！揭秘SpringBoot集成核心技巧，让你的AI应用效率翻倍！](https://www.bilibili.com/video/BV19k97Y1E48/?spm_id_from=333.1391.0.0&p=2&vd_source=2e815885181376606e6c241ba03c8907)
* AI Agent
  * [12项Agent智能体开发框架入门与选型](https://www.bilibili.com/video/BV16NBJYRE3s/?spm_id_from=333.337.search-card.all.click&vd_source=2e815885181376606e6c241ba03c8907)  

* AI 大模型的学习路线推荐
  * [AI 大模型---算法方向](https://github.com/stevenli91748/AI/blob/master/LLM%20%E5%A4%A7%E5%9E%8B%E8%AF%AD%E8%A8%80%E6%A8%A1%E5%9E%8B/AI%20%E5%A4%A7%E6%A8%A1%E5%9E%8B---%E7%AE%97%E6%B3%95%E6%96%B9%E5%90%91.md)
  * [AI 大模型---工程落地方向 ](https://github.com/stevenli91748/AI/blob/master/LLM%20%E5%A4%A7%E5%9E%8B%E8%AF%AD%E8%A8%80%E6%A8%A1%E5%9E%8B/AI%20%E5%A4%A7%E6%A8%A1%E5%9E%8B---%E5%B7%A5%E7%A8%8B%E8%90%BD%E5%9C%B0%E6%96%B9%E5%90%91.md)

# 目录
* AI 大模型的学习路线推荐
  * [吴恩达老师LLM学习路径](https://github.com/stevenli91748/AI/blob/master/LLM%20%E5%A4%A7%E5%9E%8B%E8%AF%AD%E8%A8%80%E6%A8%A1%E5%9E%8B/%E5%90%B4%E6%81%A9%E8%BE%BE%E8%80%81%E5%B8%88LLM%E5%AD%A6%E4%B9%A0%E8%B7%AF%E5%BE%84/README.md)
  * [AI 大模型---算法方向](https://github.com/stevenli91748/AI/blob/master/LLM%20%E5%A4%A7%E5%9E%8B%E8%AF%AD%E8%A8%80%E6%A8%A1%E5%9E%8B/AI%20%E5%A4%A7%E6%A8%A1%E5%9E%8B---%E7%AE%97%E6%B3%95%E6%96%B9%E5%90%91.md)
  * [AI 大模型---工程落地方向 ](https://github.com/stevenli91748/AI/blob/master/LLM%20%E5%A4%A7%E5%9E%8B%E8%AF%AD%E8%A8%80%E6%A8%A1%E5%9E%8B/AI%20%E5%A4%A7%E6%A8%A1%E5%9E%8B---%E5%B7%A5%E7%A8%8B%E8%90%BD%E5%9C%B0%E6%96%B9%E5%90%91.md)
  
0. 环境配置
   * [建立环境的三种方法](https://simplelearn.tw/anaconda-navigator-virtual-environment/)  
1. 基础知识准备（第 1 周）---掌握 Python 编程，理解神经网络基本结构和训练机制
* ✅ 编程能力---学习 Python，熟练掌握基础语法、数据结构（list/dict/set）、函数与类，学习 Numpy、Pandas、Matplotlib 基础，便于处理数据和可视化
     * [pandas](https://github.com/stevenli91748/AI/tree/master/Python/pandas) 
     * [Matplotlib](https://github.com/stevenli91748/AI/tree/master/Python/Matplotlib)
     * [NumPy](https://github.com/stevenli91748/AI/tree/master/Python/NumPy)       
* ✅ 数学基础---线性代数：矩阵运算、特征值分解，概率论与统计：条件概率、贝叶斯公式、最大似然估计，微积分：偏导数、链式法则，推荐资源：3Blue1Brown 视频（直观）+ 李宏毅机器学习课前几章

  🗓️ 第 1 周：Python 与深度学习基础（Day 1-7）

        ✅ 每周任务： Python 入门与 Numpy、Pandas、Matplotlib 基础（可用：菜鸟教程 + 知乎专栏）
  
            天数	学习内容
            Day 1	Python 基础语法、变量、分支、循环
            Day 2	函数、列表/字典/集合操作
            Day 3	Numpy 基础，矩阵运算
            Day 4	Pandas 读写 CSV、基本统计分析
            Day 5	Matplotlib 数据可视化
            Day 6	PyTorch 张量、模型定义、前向传播
            Day 7	复习 + 写一个简单的 MLP 模型用于分类 MNIST（含训练与验证）

2. 深度学习基础（第 2 周）
* ✅ 理解神经网络---感知机 → 多层感知机（MLP）→ 前馈神经网络（FNN），反向传播与梯度下降优化器（SGD、Adam）
* ✅ 熟悉框架---PyTorch（推荐） 或 TensorFlow，会用 torch.nn, torch.optim, torch.utils.data 编写基础模型训练
* ✅ 学习资源---《Deep Learning》by Ian Goodfellow（理论），李宏毅《深度学习》课程（系统），FastAI 或 HuggingFace 的入门教程（实践）

  🗓️ 第 2 周：深度学习进阶与优化（Day 8-14）

     ✅ 每周任务：学习神经网络原理（推荐：李宏毅深度学习课前几讲），学会用 PyTorch 写一个 MLP 并在 MNIST 上训练

      🗓️ 第 2 周：深度学习进阶与优化（Day 8-14）

            天数	学习内容
            Day 8	神经网络反向传播原理
            Day 9	Loss 函数、优化器（SGD/Adam）原理
            Day 10	使用 PyTorch 训练 MLP 并使用 TensorBoard 监控
            Day 11	使用 DataLoader 和自定义 Dataset
            Day 12	模型保存、加载、断点训练
            Day 13	写一个完整的分类项目（结构 + 参数调优）
            Day 14	复习 + 小项目：CIFAR-10 图像分类
  

3. 语言模型基础
* ✅ 理解 NLP 任务---Tokenization、Word Embedding、Sequence Modeling，LSTM / GRU 简介（可略），Transformer 架构（重点）
* ✅ Transformer 细节---Self-Attention，Positional Encoding，Multi-head Attention，LayerNorm / Residual
* ✅ 推荐资料---Illustrated Transformer（可视化讲解），Attention Is All You Need（原论文），Stanford CS224n（自然语言处理课程）

  🗓️ 第 3 周：NLP 入门与 Transformer 理解（Day 15-21）

     ✅ 每周任务： 掌握 NLP 基础与 Transformer 架构， 理解 Attention、Embedding、位置编码等机制

        天数	学习内容
        Day 15	NLP 任务简介 + Tokenizer 原理
        Day 16	Word Embedding：Word2Vec / BERT embedding
        Day 17	Transformer 架构总览
        Day 18	Self-Attention 与多头注意力机制
        Day 19	Positional Encoding、LayerNorm、残差连接
        Day 20	实现一个简化版 Transformer（Encoder）
        Day 21	复习 + 用 Transformers 库加载 GPT2 并推理文本生成
 

4. 大模型架构与训练机制
* ✅ 构建 LLM 的关键模块---Decoder-only Transformer（GPT 架构），Masked Self-Attention，Causal Language Modeling（CLM）
* ✅ 训练大模型要点---预训练 vs 微调，数据并行、模型并行（Megatron、Deepspeed），Mixed Precision、Gradient Checkpointing

  🗓️ 第 4 周：HuggingFace 快速上手（Day 22-28）

    ✅ 每周任务： 阅读“Attention is All You Need”前半部分, 跟着 Illustrated Transformer 做可视化学习, 用 PyTorch 实现简化版的 Transformer（可参考 Harvard NLP 的教程）,
                 用 HuggingFace 加载一个 GPT2 模型并进行推理

        天数	学习内容
        Day 22	HuggingFace Transformers 库结构概览
        Day 23	使用 Pretrained 模型 + Tokenizer 推理
        Day 24	文本分类任务微调（Trainer + Dataset）
        Day 25	文本生成任务微调（Causal LM）
        Day 26	掌握 LoRA 机制进行参数高效微调
        Day 27	用小数据做一次微调（SST2）
        Day 28	复习 + 小项目：训练一个对话模型并保存

  🗓️ 第 5 周：实战 HuggingFace 与微调 LLM

        🧠 目标：
        学会使用 HuggingFace Transformers 进行微调， 掌握 Tokenizer、数据准备、训练流程
        
        ✅ 每周任务：学习 HuggingFace 教程（HuggingFace Course），微调一个 GPT2 或 LLaMA 模型做摘要/问答（LoRA 或 QLoRA），理解模型训练日志、保存和加载

 

5. 开源项目实战

* ✅ 推荐实战项目---HuggingFace Transformers: 熟悉 AutoModelForCausalLM, Trainer，LLaMA、GPT-NeoX、RWKV：了解模型结构与微调流程，LoRA / QLoRA 微调方法，适合资源有限场景

  🗓️ 第 6 周：项目实战整合（Day 36-42）

        天数	学习内容
        Day 29	端到端流程梳理：准备数据 → 微调 → 推理
        Day 30	开发数据收集脚本并构造训练集
        Day 31	使用自己的数据训练简易问答模型
        Day 32	训练调试，分析 loss 曲线与 overfitting 现象
        Day 33	推理、部署、打包工具整合
        Day 34	项目收尾：封装 API，打包 demo 工程
        Day 35	项目演示 + 总结（写文档）



6. 部署与应用
* ✅ 模型推理部署---ONNX、TorchScript，HuggingFace Inference Endpoints、FastAPI 接口部署，GPU 加速、量化推理（INT8）
* ✅ 应用场景---Chatbot、文档总结、代码补全、问答系统

  🗓️ 第 7 周：部署与优化（Day 29-35）

    🧠 目标：掌握模型导出、量化与部署方法

    ✅ 每周任务：使用 transformers + gradio 创建一个简单聊天网页，了解模型导出 ONNX、TorchScript，尝试使用 quantization 推理加速（bitsandbytes 或 GGML）

    天数	学习内容
    Day 36	模型推理优化：int8 量化，混合精度
    Day 37	导出 ONNX / TorchScript 模型
    Day 38	使用 Gradio 创建推理界面
    Day 39	FastAPI + Transformers 构建 API 服务
    Day 40	模型部署到本地/服务器
    Day 41	测试部署性能，响应时间分析
    Day 42	复习 + 小项目：部署你的聊天机器人到本地网页



7. 进阶阅读与研究方向（可选）
* ✅ MoE（Mixture of Experts）
* ✅ RAG（Retrieval Augmented Generation）
* ✅ 多模态模型（图文理解）、Agent 系统（LangChain）
* ✅ RLHF（强化学习人类反馈）

  🗓️ 第 8 周	阅读论文（MoE、RAG、RLHF 各一篇）
  
        🧠 目标：整合从训练到部署的流程,初探前沿方向（MoE, RAG, RLHF）

        ✅ 每周任务：实现一个端到端的聊天系统 demo（数据 → 微调 → 部署）,阅读一篇前沿论文：RAG 或 RLHF, 浏览 LLaMA、GPT-NeoX、RWKV 的开源实现,
                    实现简单版检索增强生成（RAG）对比 GPT2 与 LLaMA 的结构与推理性能,使用 LangChain 实现简单智能助手，集成向量数据库（如 FAISS）
                    模拟 RLHF 数据训练一个奖励模型，完整复习全流程，输出总结笔记




# 有用的参考
* [本地快速安装运行史上最强开源LLaMa3大模型](https://liaoxuefeng.com/blogs/all/2024-05-06-llama3/index.html)
