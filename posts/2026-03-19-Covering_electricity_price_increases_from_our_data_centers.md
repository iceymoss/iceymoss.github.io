---
title: Covering electricity price increases from our data centers
topics: AI Infrastructure, Energy Efficiency, Cost Optimization
date: 2026-03-19T12:13:59+08:00
Link: https://www.anthropic.com/news/covering-electricity-price-increases
Source: Hacker News
---

随着全球能源价格持续上涨，大型AI模型训练与推理的电力成本已成为科技公司的重大运营挑战。Anthropic 面临其数据中心电力支出显著增加的压力，这直接影响了 Claude 等大语言模型的运营经济性。

核心应对方案聚焦于多层级技术优化：在硬件层面，采用能效比更高的定制化 AI 加速器（如 TPU v5e 或类似架构），并通过动态电压频率调整（DVFS）技术实时匹配算力需求与功耗；在软件与算法层面，优化模型推理服务，通过更高效的注意力机制实现、模型量化（如 INT8 量化）以及请求批处理（Request Batching）来提升单位能耗的计算吞吐量；在基础设施层，利用智能负载均衡器将计算任务动态调度至电价更低的区域或时段（即“跟随月亮”或“跟随风电”策略），并可能结合使用可再生能源采购协议（PPA）。

其技术价值在于，通过软硬件协同设计，在不大幅牺牲模型性能（如延迟和准确性）的前提下，系统性降低单位计算任务的能耗与成本。这为行业提供了可借鉴的可持续AI运营范式，表明未来大模型竞争的焦点将部分从纯性能指标转向包含能效比的综合经济性指标。此举也响应了日益严格的 ESG 要求，推动了绿色计算在AI领域的具体实践。