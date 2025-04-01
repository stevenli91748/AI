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

# 在线书籍
  * [神书  从零构建大型语言模型](https://www.scribd.com/document/763076237/%E4%BB%8E%E9%9B%B6%E6%9E%84%E5%BB%BA%E5%A4%A7%E8%AF%AD%E8%A8%80%E6%A8%A1%E5%9E%8B-%E4%B8%AD%E6%96%87%E7%89%88)

# 目录
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



# 有用的参考
* [本地快速安装运行史上最强开源LLaMa3大模型](https://liaoxuefeng.com/blogs/all/2024-05-06-llama3/index.html)
