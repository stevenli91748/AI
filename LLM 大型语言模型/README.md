LLM即大型语言模型（Large Language Model），是一种基于深度学习技术的人工智能模型，在自然语言处理领域具有重要地位

* 定义与特点
    定义：LLM是一种具有大规模参数的语言模型，通常基于Transformer架构，通过在海量文本数据上进行无监督或自监督学习，学习语言的统计规律和语义信息，从而能够生成自然流畅的文本、理解和回答各种自然语言问题等。
* 特点
  * 规模大：拥有海量的参数，例如GPT-3拥有1750亿个参数，使得模型能够学习到极其复杂的语言模式和知识。
  * 数据驱动：基于大量的文本数据进行训练，数据来源广泛，涵盖了互联网上的各种文本，如新闻、小说、论文、社交媒体等，从而获取丰富的语言知识和世界知识。
  * 通用性强：可以应用于多种自然语言处理任务，如文本生成、机器翻译、问答系统、文本摘要、情感分析等，无需针对每个任务单独设计模型。
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

* LLM与AIGC
  * LLM是AIGC的重要技术支撑：LLM具备强大的语言理解和生成能力，是实现AIGC在文本领域应用的核心技术。通过在海量文本数据上进行训练，LLM能够学习到语言的模式、语义和逻辑关系，从而生成高质量的文本内容，如文章、故事、对话等。例如ChatGPT就是基于LLM的典型AIGC应用，能与用户进行自然流畅的对话，生成各种类型的文本。
  * AIGC拓展了LLM的应用场景：AIGC涵盖了多种内容形式的生成，除了文本，还包括图像、音频、视频等。虽然LLM本身主要处理文本，但在AIGC的整体框架下，LLM可以与其他技术结合，参与到多模态内容生成中。比如通过与图像生成技术结合，根据文本描述生成相应的图像，实现更丰富的AIGC应用。
* LLM与AI Agent
  * LLM为AI Agent提供语言交互能力：AI Agent需要与用户或环境进行交互，LLM为其提供了自然语言处理的基础，使AI Agent能够理解用户的自然语言指令，并以自然语言进行回应。AI Agent可以借助LLM的语言理解和生成能力，更好地完成信息查询、任务执行等功能，提升与人类交互的效率和质量。
  * AI Agent是LLM的应用载体之一：AI Agent可以将LLM的能力集成到具体的应用场景和任务中，使其具有特定的目标和行为。例如智能客服、智能助手等AI Agent，利用LLM的强大语言处理能力，为用户提供服务和帮助，将LLM的技术价值转化为实际的应用价值。
* AIGC与AI Agent
  * AIGC为AI Agent提供内容生成能力：AI Agent在执行任务过程中，可能需要生成各种类型的内容，AIGC技术能够为其提供相应的支持。例如一个负责营销推广的AI Agent，需要生成广告文案、宣传海报等内容，AIGC中的文本生成和图像生成技术就可以帮助AI Agent完成这些任务。
  * AI Agent推动AIGC的应用落地：AI Agent作为具有自主性和交互性的实体，能够将AIGC生成的内容更好地应用到实际场景中，并根据用户反馈和环境变化，动态调整和优化AIGC的生成结果。比如智能写作助手这类AI Agent，能够根据用户的写作需求，利用AIGC技术生成初稿，并通过与用户的交互不断完善内容。

三者相互关联、相互促进。LLM是基础技术，为AIGC和AI Agent提供了强大的语言处理支持；AIGC基于LLM等技术实现了各种内容的生成，丰富了AI的应用形式；AI Agent则作为应用载体，将LLM和AIGC的能力集成到具体的任务和场景中，使它们的价值得到更充分的体现，共同推动了人工智能技术的发展和应用。

总的来说AI主要由算法、算力、数据组成，算法是核心。LLM是基于Transformer架构的算法成果，属于NLP领域关键技术，赋予AI理解和生成语言的能力。如果把AI AGENT看作人工助手，LLM就是其大脑，提供智能核心。AIGC则基于LLM等技术，生成语言、图像、音频等内容，就像人基于大脑的一些语言和视觉的表达。举个例子：云雀模型是LLM，豆包的问答查询基于此，是AIGC在语言领域的应用；图片生成借助专门模型，也是AIGC。豆包APP里的智能体是AI AGENT，集成云雀能力为用户服务。


![](https://github.com/stevenli91748/AI/blob/master/%E8%87%AA%E7%84%B6%E8%AF%AD%E8%A8%80%E5%A4%84%E7%90%86%E5%AD%A6%E4%B9%A0%E8%B7%AF%E5%BE%84.png)

# 在线书籍
  * [神书  从零构建大型语言模型](https://www.scribd.com/document/763076237/%E4%BB%8E%E9%9B%B6%E6%9E%84%E5%BB%BA%E5%A4%A7%E8%AF%AD%E8%A8%80%E6%A8%A1%E5%9E%8B-%E4%B8%AD%E6%96%87%E7%89%88)

# 博客
[动手学大模型应用开发---github](https://github.com/datawhalechina/llm-universe)|[llm-action](https://github.com/liguodongiot/llm-action)|[3Blue1Brown](https://www.youtube.com/c/3blue1brown)| [Datawhale人工智能培养方案](https://github.com/datawhalechina)|
---|---|---|---|




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
