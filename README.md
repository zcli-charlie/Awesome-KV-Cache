<a name="readme-top"></a>

<div align="center">
  <a href="https://github.com/zcli-charlie/Awesome-KV-Cache/stargazers"><img src="https://img.shields.io/github/stars/zcli-charlie/Awesome-KV-Cache?style=for-the-badge" alt="Stargazers"></a>
  <a href="https://github.com/zcli-charlie/Awesome-KV-Cache/network/members"><img src="https://img.shields.io/github/forks/zcli-charlie/Awesome-KV-Cache?style=for-the-badge" alt="Forks"></a>
  <a href="https://github.com/zcli-charlie/Awesome-KV-Cache/graphs/contributors"><img src="https://img.shields.io/github/contributors/zcli-charlie/Awesome-KV-Cache?style=for-the-badge" alt="Contributors"></a>
  <a href="https://github.com/zcli-charlie/Awesome-KV-Cache/blob/main/LICENSE"><img src="https://img.shields.io/github/license/zcli-charlie/Awesome-KV-Cache?style=for-the-badge" alt="MIT License"></a>
</div>

<p align="center">
    <img src="assets/Main.png" width="80%" style="align:center;"/>
</p>

<h1 align="center">Awesome KV Caching (WIP)</h1>

<p align="center">
    <b> Curated collection of papers and resources on how to build a efficient KV Cache system for LLM inference service.</b>
</p>

<!-- <details>
  <summary>🗂️ Table of Contents</summary>
  <ol>
    <li><a href="#survey">Survey</a></li>
    <li><a href="#analysis">Analysis</a></li>
    <li><a href="#ltechnique">Technique</a>
      <ul>
        <li><a href="#llm">🔤 Reasoning in Large Language Models - <em>An Emergent Ability</em></a></li>
        <li><a href="#lm">🤏 Scaling Smaller Language Models to Reason</a></li>
        <li><a href="#mllm">🧠 Multimodal Reasoning in Large Language Models</a></li>
      </ul>
    </li>
    <li><a href="#benchmark">Benchmark</a></li>
    <li><a href="#other-useful-resources">Other Useful Resources</a></li>
    <li><a href="#other-awesome-lists">Other Awesome Lists</a></li>
    <li><a href="#contributing">Contributing</a></li>
  </ol>
</details> -->

The template is derived from <b><a href=https://github.com/atfortes/Awesome-LLM-Reasoning>
Awesome-LLM-Reasoning</a></b>. Still **Work In Progress**.

## Pre-Train Stage, Structural Modification

1. **Long-Context Language Modeling with Parallel Context Encoding** `ACL 2024`

   *Howard Yen, Tianyu Gao, Danqi Chen* [[Paper](https://arxiv.org/abs/2402.16617)] [[Code](https://github.com/princeton-nlp/CEPE)], 2024.2

   <!-- Re-introduce Encoder module to comprise long context. -->

1. **GQA: Training Generalized Multi-Query Transformer Models from Multi-Head Checkpoints** `EMNLP 2023`

    *Joshua Ainslie, James Lee-Thorp, Michiel de Jong, Yury Zemlyanskiy, Federico Lebrón, Sumit Sanghai* [[Paper](https://arxiv.org/abs/2305.13245)], 2023.05

    <!-- Reuse KV Cache across attention heads. -->

1. **Reducing Transformer Key-Value Cache Size with Cross-Layer Attention** `Preprint`

    *William Brandon, Mayank Mishra, Aniruddha Nrusimha, Rameswar Panda, Jonathan Ragan Kelly* [[Paper](https://arxiv.org/abs/2405.12981)], 2024.5

    <!-- Reuse KV Cache across layers. -->

1. **You Only Cache Once: Decoder-Decoder Architectures for Language Models** `Preprint`

    *Yutao Sun, Li Dong, Yi Zhu, Shaohan Huang, Wenhui Wang, Shuming Ma, Quanlu Zhang, Jianyong Wang, Furu Wei* [[Paper](https://arxiv.org/abs/2405.05254)] [[Code](https://github.com/microsoft/unilm/tree/master/YOCO)], 2024.5

    <!-- Use a linear model to generate KV Cache for all layer at once. -->

1. **GoldFinch: High Performance RWKV/Transformer Hybrid with Linear Pre-Fill and Extreme KV-Cache Compression** `Preprint`

    *Daniel Goldstein, Fares Obeid, Eric Alcaide, Guangyu Song, Eugene Cheah* [[Paper](https://arxiv.org/abs/2407.12077)] [[Code](https://github.com/recursal/GoldFinch-paper)], 2024.7

    <!-- Use a linear model to generate KV Cache for all layer at once, but even more extreme. -->

1. **DeepSeek-V2: A Strong, Economical, and Efficient Mixture-of-Experts Language Model** `Preprint`

    *DeepSeek-AI Team* [[Paper](https://arxiv.org/abs/2405.04434)], 2024.5

    <!-- Instead reusing, mapping the KV Cache into latent space. -->

<p align="right" style="font-size: 14px; color: #555; margin-top: 20px;">
    <a href="#readme-top" style="text-decoration: none; color: #007bff; font-weight: bold;">
        ↑ Back to Top ↑
    </a>
</p>

## Deploy Stage, Inference System

### Lossless Method

1. **Efficient Memory Management for Large Language Model Serving with PagedAttention** `SOSP 2023`

    *Woosuk Kwon, Zhuohan Li, Siyuan Zhuang, Ying Sheng, Lianmin Zheng, Cody Hao Yu, Joseph E. Gonzalez, Hao Zhang, Ion Stoica* [[Paper](https://dl.acm.org/doi/abs/10.1145/3600006.3613165)] [[Code](https://github.com/vllm-project/vllm)], 2023.10 Pubed

    <!-- Manage KV Cache like paged memory. -->

1. **ChunkAttention: Efficient Self-Attention with Prefix-Aware KV Cache and Two-Phase Partition** `ACL 2024`

    *Lu Ye, Ze Tao, Yong Huang, Yang Li* [[Paper](https://arxiv.org/abs/2402.15220)] [[Code](https://github.com/microsoft/chunk-attention)], 2024.2

    <!-- Use a prefix-tree to manage and reuse KV Cache across decoding requests. -->

1. **FastDecode: High-Throughput GPU-Efficient LLM Serving using Heterogeneous Pipelines** `Preprint`

    *Jiaao He, Jidong Zhai* [[Paper](https://arxiv.org/abs/2403.11421)], 2024.3

    <!-- Utilize modern CPU to help the computation of attention. -->


1. **Infinite-LLM: Efficient LLM Service for Long Context with DistAttention and Distributed KVCache** `Preprint`

    *Bin Lin, Chen Zhang, Tao Peng, Hanyu Zhao, Wencong Xiao, Minmin Sun, Anmin Liu, Zhipeng Zhang, Lanbo Li, Xiafei Qiu, Shen Li, Zhigang Ji, Tao Xie, Yong Li, Wei Lin* [[Paper](https://arxiv.org/abs/2401.02669v2)], 2024.1

    <!-- Fully utilize the ability of a distributed inference system. -->

1. **Mooncake: A KVCache-centric Disaggregated Architecture for LLM Serving** `Preprint`

    *Ruoyu Qin, Zheming Li, Weiran He, Mingxing Zhang, Yongwei Wu, Weimin Zheng, Xinran Xu* [[Paper](https://arxiv.org/abs/2407.00079)], 2024.6

    <!-- A KV-Cache-centric disaggregated architecture that designed and used by a major AI company. -->

### Lossy Method

1. **InfiniGen: Efficient Generative Inference of Large Language Models with Dynamic KV Cache Management** `OSDI 2024`

    *Wonbeom Lee, Jungi Lee, Junghwan Seo, Jaewoong Sim* [[Paper](https://arxiv.org/abs/2406.19707)], 2024.6

    <!-- Speculate important tokens for attention then pre-fetch them from slower but larger memory. -->

1. **Cost-Efficient Large Language Model Serving for Multi-turn Conversations with CachedAttention** `ATC 2024`

    *Bin Gao, Zhuomin He, Puru Sharma, Qingxuan Kang, Djordje Jevdjic, Junbo Deng, Xingkun Yang, Zhou Yu, Pengfei Zuo* [[Paper](https://arxiv.org/abs/2403.19708v3)], 2024.3

    <!-- Manage and reuse KV Cache in a hierarchical system on multiple storage devices. -->

1. **InfLLM: Training-Free Long-Context Extrapolation for LLMs with an Efficient Context Memory** `Preprint`

    *Chaojun Xiao, Pengle Zhang, Xu Han, Guangxuan Xiao, Yankai Lin, Zhengyan Zhang, Zhiyuan Liu, Maosong Sun* [[Paper](https://arxiv.org/abs/2402.04617)], 2024.2

    <!-- Offload most KV-Cache to CPU, left only a few Keys for smart retrieval. -->

1. **Mnemosyne: Parallelization Strategies for Efficiently Serving Multi-Million Context Length LLM Inference Requests Without Approximations** `Preprint`

    *Amey Agrawal, Junda Chen, Íñigo Goiri, Ramachandran Ramjee, Chaojie Zhang, Alexey Tumanov, Esha Choukse* [[Paper](https://arxiv.org/pdf/2409.17264)], 2024.9

1. **Post-Training Sparse Attention with Double Sparsity** `Preprint`

    *Shuo Yang, Ying Sheng, Joseph E. Gonzalez, Ion Stoica, Lianmin Zheng* [[Paper](https://arxiv.org/abs/2408.07092)], 2024.8

<p align="right" style="font-size: 14px; color: #555; margin-top: 20px;">
    <a href="#readme-top" style="text-decoration: none; color: #007bff; font-weight: bold;">
        ↑ Back to Top ↑
    </a>
</p>

## Post-Train Stage

### Static Eviction

1. **Longformer: The Long-Document Transformer** `Preprint`

    *Iz Beltagy, Matthew E. Peters, Arman Cohan* [[Paper](https://arxiv.org/abs/2004.05150)], 2020.4

1. **Efficient Streaming Language Models with Attention Sinks** `ICLR 2024`

    *Guangxuan Xiao, Yuandong Tian, Beidi Chen, Song Han, Mike Lewis* [[Paper](https://arxiv.org/abs/2309.17453)], 2023.9

1. **LM-Infinite: Zero-Shot Extreme Length Generalization for Large Language Models** `NAACL 2024`

    *Chi Han, Qifan Wang, Hao Peng, Wenhan Xiong, Yu Chen, Heng Ji, Sinong Wang* [[Paper](https://aclanthology.org/2024.naacl-long.222/)], 2023.12

1. **RazorAttention: Efficient KV Cache Compression Through Retrieval Heads** `Preprint`

    *Hanlin Tang, Yang Lin, Jing Lin, Qingsen Han, Shikuan Hong, Yiwu Yao, Gongyi Wang* [[Paper](https://arxiv.org/abs/2407.15891)], 2024.7

### Dynamic Eviction

1. **H2O: Heavy-Hitter Oracle for Efficient Generative Inference of Large Language Models** `NeurIPS 2023`

    *Zhenyu Zhang, Ying Sheng, Tianyi Zhou, Tianlong Chen, Lianmin Zheng, Ruisi Cai, Zhao Song, Yuandong Tian, Christopher Ré, Clark Barrett, Zhangyang "Atlas" Wang, Beidi Chen* [[Paper](https://proceedings.neurips.cc/paper_files/paper/2023/hash/6ceefa7b15572587b78ecfcebb2827f8-Abstract-Conference.html)], 2023.4

1. **Scissorhands: Exploiting the Persistence of Importance Hypothesis for LLM KV Cache Compression at Test Time** `NeurIPS 2023`

    *Zichang Liu, Aditya Desai, Fangshuo Liao, Weitao Wang, Victor Xie, Zhaozhuo Xu, Anastasios Kyrillidis, Anshumali Shrivastava* [[Paper](https://proceedings.neurips.cc/paper_files/paper/2023/hash/a452a7c6c463e4ae8fbdc614c6e983e6-Abstract-Conference.html)], 2023.4

1. **PyramidInfer: Pyramid KV Cache Compression for High-throughput LLM Inference** `ACL 2024`

    *Dongjie Yang, XiaoDong Han, Yan Gao, Yao Hu, Shilin Zhang, Hai Zhao* [[Paper](https://arxiv.org/abs/2405.12532)], 2024.2

1. **Keyformer: KV Cache reduction through key tokens selection for Efficient Generative Inference** `MLSys 2024`

    *Muhammad Adnan, Akhil Arunkumar, Gaurav Jain, Prashant Nair, Ilya Soloveychik, Purushotham Kamath* [[Paper](https://proceedings.mlsys.org/paper_files/paper/2024/hash/48fecef47b19fe501d27d338b6d52582-Abstract-Conference.html)], 2024.3

1. **Model Tells You What to Discard: Adaptive KV Cache Compression for LLMs** `ICLR 2024 Oral`

    *Suyu Ge, Yunan Zhang, Liyuan Liu, Minjia Zhang, Jiawei Han, Jianfeng Gao* [[Paper](https://arxiv.org/abs/2310.01801)], 2023.10

1. **SparQ Attention: Bandwidth-Efficient LLM Inference** `Preprint`

    *Luka Ribar, Ivan Chelombiev, Luke Hudlass-Galley, Charlie Blake, Carlo Luschi, Douglas Orr* [[Paper](https://arxiv.org/abs/2312.04985)], 2023.12

1. **Finch: Prompt-guided Key-Value Cache Compression** `TACL`

    *Giulio Corallo, Paolo Papotti* [[Paper](https://arxiv.org/abs/2408.00167)], 2024.8

1. **A2SF: Accumulative Attention Scoring with Forgetting Factor for Token Pruning in Transformer Decoder** `Preprint`

    *Hyun-rae Jo, Dongkun Shin* [[Paper](https://arxiv.org/abs/2407.20485)], 2024.7

1. **ThinK: Thinner Key Cache by Query-Driven Pruning** `Preprint`

    *Yuhui Xu, Zhanming Jie, Hanze Dong, Lei Wang, Xudong Lu, Aojun Zhou, Amrita Saha, Caiming Xiong, Doyen Sahoo* [[Paper](https://arxiv.org/abs/2407.21018)], 2024.7

1. **LazyLLM: Dynamic Token Pruning for Efficient Long Context LLM Inference** `Preprint`

    *Qichen Fu, Minsik Cho, Thomas Merth, Sachin Mehta, Mohammad Rastegari, Mahyar Najibi* [[Paper](https://arxiv.org/abs/2407.14057)], 2024.7

1. **SirLLM: Streaming Infinite Retentive LLM** `ACL 2024`

    *Yao Yao, Zuchao Li, Hai Zhao* [[Paper](https://arxiv.org/abs/2405.12528)], 2024.2

1. **A Simple and Effective $L_2$ Norm-Based Strategy for KV Cache Compression** `ACL 2024`

    *Alessio Devoto, Yu Zhao, Simone Scardapane, Pasquale Minervini* [[Paper](https://arxiv.org/abs/2406.11430)], 2024.6

### Merging

1. **Dynamic Memory Compression: Retrofitting LLMs for Accelerated Inference** `ICML 2024`

    *Piotr Nawrot, Adrian Łańcucki, Marcin Chochowski, David Tarjan, Edoardo M. Ponti* [[Paper](https://arxiv.org/abs/2403.09636)], 2024.1

1. **Effectively Compress KV Heads for LLM** `Preprint`

    *Hao Yu, Zelan Yang, Shen Li, Yong Li, Jianxin Wu* [[Paper](https://arxiv.org/abs/2406.07056)], 2024.6

1. **D2O: Dynamic Discriminative Operations for Efficient Generative Inference of Large Language Models** `Preprint`

    *Yuxin Zhang, Yuxuan Du, Gen Luo, Yunshan Zhong, Zhenyu Zhang, Shiwei Liu, Rongrong Ji * [[Paper](https://arxiv.org/abs/2406.13035)], 2024.6

1. **CaM: Cache Merging for Memory-efficient LLMs Inference** `ICML 2024`

    *Yuxin Zhang, Yuxuan Du, Gen Luo, Yunshan Zhong, Zhenyu Zhang, Shiwei Liu, Rongrong Ji * [[Paper](https://openreview.net/forum?id=LCTmppB165)], 2024.1

1. **Model Tells You Where to Merge: Adaptive KV Cache Merging for LLMs on Long-Context Tasks** `Preprint`

    *Zheng Wang, Boxiao Jin, Zhongzhi Yu, Minjia Zhang* [[Paper](https://arxiv.org/abs/2407.08454)], 2024.7

1. **MiniCache: KV Cache Compression in Depth Dimension for Large Language Models** `Preprint`

    *Akide Liu, Jing Liu, Zizheng Pan, Yefei He, Gholamreza Haffari, Bohan Zhuang* [[Paper](https://arxiv.org/abs/2405.14366)], 2024.5

1. **Anchor-based Large Language Models** `ACL 2024`

    *Jianhui Pang, Fanghua Ye, Derek Fai Wong, Xin He, Wanshun Chen, Longyue Wang* [[Paper](https://arxiv.org/abs/2402.07616)], 2024.2

### Quantization

1. **KVQuant: Towards 10 Million Context Length LLM Inference with KV Cache Quantization** `Preprint`

    *Coleman Hooper, Sehoon Kim, Hiva Mohammadzadeh, Michael W. Mahoney, Yakun Sophia Shao, Kurt Keutzer, Amir Gholami* [[Paper](https://arxiv.org/abs/2401.18079)], 2024.1

1. **No Token Left Behind: Reliable KV Cache Compression via Importance-Aware Mixed Precision Quantization** `Preprint`

    *June Yong Yang, Byeongwook Kim, Jeongin Bae, Beomseok Kwon, Gunho Park, Eunho Yang, Se Jung Kwon, Dongsoo Lee* [[Paper](https://arxiv.org/abs/2402.18096)], 2024.2

1. **QAQ: Quality Adaptive Quantization for LLM KV Cache** `Preprint`

    *Shichen Dong, Wen Cheng, Jiayu Qin, Wei Wang* [[Paper](https://arxiv.org/abs/2403.04643)], 2024.3

1. **GEAR: An Efficient KV Cache Compression Recipe for Near-Lossless Generative Inference of LLM** `Preprint`

    *Hao Kang, Qingru Zhang, Souvik Kundu, Geonhwa Jeong, Zaoxing Liu, Tushar Krishna, Tuo Zhao* [[Paper](https://arxiv.org/abs/2403.05527)], 2024.3

1. **FlexGen: High-Throughput Generative Inference of Large Language Models with a Single GPU** `PMLR 2023`

    *Ying Sheng, Lianmin Zheng, Binhang Yuan, Zhuohan Li, Max Ryabinin, Beidi Chen, Percy Liang, Christopher Re, Ion Stoica, Ce Zhang* [[Paper](https://openreview.net/forum?id=RRntzKrBTp)], 2023.3

1. **WKVQuant: Quantizing Weight and Key/Value Cache for Large Language Models Gains More** `PMLR 2023`

    *Yuxuan Yue, Zhihang Yuan, Haojie Duanmu, Sifan Zhou, Jianlong Wu, Liqiang Nie* [[Paper](https://arxiv.org/abs/2402.12065)], 2024.2

1. **SKVQ: Sliding-window Key and Value Cache Quantization for Large Language Models** `COLM 2024`

    *Haojie Duanmu, Zhihang Yuan, Xiuhong Li, Jiangfei Duan, Xingcheng Zhang, Dahua Lin* [[Paper](https://arxiv.org/abs/2405.06219)], 2024.5

# Benchmark

Work in progress.
| Field | Benchmarks |
| :----------------------------------------------: | :---------------------------------------------- |
| Efficiency | |
| Retrieval  | |
| Reasoning  | |

<p align="right" style="font-size: 14px; color: #555; margin-top: 20px;">
    <a href="#readme-top" style="text-decoration: none; color: #007bff; font-weight: bold;">
        ↑ Back to Top ↑
    </a>
</p>

## Other Awesome Lists

- **[Awesome-LLM-Reasoning](https://github.com/atfortes/Awesome-LLM-Reasoning)**  Curated collection of papers and resources on how to unlock the reasoning ability of LLMs and MLLMs.
- **[Awesome-Controllable-Generation](https://github.com/atfortes/Awesome-Controllable-Generation)**  Collection of papers and resources on Controllable Generation using Diffusion Models.
- **[Chain-of-ThoughtsPapers](https://github.com/Timothyxxx/Chain-of-ThoughtsPapers)**  A trend starts from "Chain-of-Thought Prompting Elicits Reasoning in Large Language Models".
- **[LM-reasoning](https://github.com/jeffhj/LM-reasoning)**  Collection of papers and resources on Reasoning in Large Language Models.
- **[Prompt4ReasoningPapers](https://github.com/zjunlp/Prompt4ReasoningPapers)**  Repository for the paper "Reasoning with Language Model Prompting: A Survey".
- **[ReasoningNLP](https://github.com/FreedomIntelligence/ReasoningNLP)**  Paper list on reasoning in NLP
- **[Awesome-LLM](https://github.com/Hannibal046/Awesome-LLM)**  Curated list of Large Language Model.
- **[Awesome LLM Self-Consistency](https://github.com/SuperBruceJia/Awesome-LLM-Self-Consistency)**  Curated list of Self-consistency in Large Language Models.
- **[Deep-Reasoning-Papers](https://github.com/floodsung/Deep-Reasoning-Papers)**  Recent Papers including Neural-Symbolic Reasoning, Logical Reasoning, and Visual Reasoning.

<p align="right" style="font-size: 14px; color: #555; margin-top: 20px;">
    <a href="#readme-top" style="text-decoration: none; color: #007bff; font-weight: bold;">
        ↑ Back to Top ↑
    </a>
</p>



## Contributing

- Add a new paper or update an existing paper, thinking about which category the work should belong to.
- Use the same format as existing entries to describe the work.
- Add the abstract link of the paper (`/abs/` format if it is an arXiv publication).

**Don't worry if you do something wrong, it will be fixed for you!**

### Contributors

<a href="https://github.com/zcli-charlie/Awesome-KV-Cache/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=zcli-charlie/Awesome-KV-Cache" />
</a>

<!-- ### Star History

[![Star History Chart](https://api.star-history.com/svg?repos=zcli-charlie/Awesome-KV-Cache&type=Timeline)](https://star-history.com/#zcli-charlie/Awesome-KV-Cache&Timeline) -->
