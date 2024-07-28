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

1. **GQA: Training Generalized Multi-Query Transformer Models from Multi-Head Checkpoints** `EMNLP 2023`

    *Joshua Ainslie, James Lee-Thorp, Michiel de Jong, Yury Zemlyanskiy, Federico Lebrón, Sumit Sanghai* [[Paper](https://arxiv.org/abs/2305.13245)], 2023.05

1. **Reducing Transformer Key-Value Cache Size with Cross-Layer Attention** `Preprint`

    *William Brandon, Mayank Mishra, Aniruddha Nrusimha, Rameswar Panda, Jonathan Ragan Kelly* [[Paper](https://arxiv.org/abs/2405.12981)], 2024.5

1. **You Only Cache Once: Decoder-Decoder Architectures for Language Models** `Preprint`

    *Yutao Sun, Li Dong, Yi Zhu, Shaohan Huang, Wenhui Wang, Shuming Ma, Quanlu Zhang, Jianyong Wang, Furu Wei* [[Paper](https://arxiv.org/abs/2405.05254)] [[Code](https://github.com/microsoft/unilm/tree/master/YOCO)], 2024.5

1. **GoldFinch: High Performance RWKV/Transformer Hybrid with Linear Pre-Fill and Extreme KV-Cache Compression** `Preprint`

    *Daniel Goldstein, Fares Obeid, Eric Alcaide, Guangyu Song, Eugene Cheah* [[Paper](https://arxiv.org/abs/2407.12077)] [[Code](https://github.com/recursal/GoldFinch-paper)], 2024.7

1. **DeepSeek-V2: A Strong, Economical, and Efficient Mixture-of-Experts Language Model** `Preprint`

    *DeepSeek-AI Team* [[Paper](https://arxiv.org/abs/2405.04434)], 2024.5

<p align="right" style="font-size: 14px; color: #555; margin-top: 20px;">
    <a href="#readme-top" style="text-decoration: none; color: #007bff; font-weight: bold;">
        ↑ Back to Top ↑
    </a>
</p>

## Deploy Stage, Inference System

1. **Efficient Memory Management for Large Language Model Serving with PagedAttention** `SOSP 2023`

    *Woosuk Kwon, Zhuohan Li, Siyuan Zhuang, Ying Sheng, Lianmin Zheng, Cody Hao Yu, Joseph E. Gonzalez, Hao Zhang, Ion Stoica* [[Paper](https://dl.acm.org/doi/abs/10.1145/3600006.3613165)] [[Code](https://github.com/vllm-project/vllm)], 2023.10 Pubed

1. **ChunkAttention: Efficient Self-Attention with Prefix-Aware KV Cache and Two-Phase Partition** `ACL 2024`

    *Lu Ye, Ze Tao, Yong Huang, Yang Li* [[Paper](https://arxiv.org/abs/2402.15220)] [[Code](https://github.com/microsoft/chunk-attention)], 2024.2

1. **Cost-Efficient Large Language Model Serving for Multi-turn Conversations with CachedAttention** `ATC 2024`

    *Bin Gao, Zhuomin He, Puru Sharma, Qingxuan Kang, Djordje Jevdjic, Junbo Deng, Xingkun Yang, Zhou Yu, Pengfei Zuo* [[Paper](https://arxiv.org/abs/2403.19708v3)], 2024.3

1. **InfiniGen: Efficient Generative Inference of Large Language Models with Dynamic KV Cache Management** `OSDI 2024`

    *Wonbeom Lee, Jungi Lee, Junghwan Seo, Jaewoong Sim* [[Paper](https://arxiv.org/abs/2403.19708v3)], 2024.6

1. **Mooncake: A KVCache-centric Disaggregated Architecture for LLM Serving** `Preprint`

    *Ruoyu Qin, Zheming Li, Weiran He, Mingxing Zhang, Yongwei Wu, Weimin Zheng, Xinran Xu* [[Paper](https://arxiv.org/abs/2407.00079)], 2024.6

1. **FastDecode: High-Throughput GPU-Efficient LLM Serving using Heterogeneous Pipelines** `Preprint`

    *Jiaao He, Jidong Zhai* [[Paper](https://arxiv.org/abs/2403.11421)], 2024.3

<p align="right" style="font-size: 14px; color: #555; margin-top: 20px;">
    <a href="#readme-top" style="text-decoration: none; color: #007bff; font-weight: bold;">
        ↑ Back to Top ↑
    </a>
</p>

## Post-Train Stage
Work in progress.
### Static Eviction
### Dynamic Eviction
### Merging
### Quantization


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
