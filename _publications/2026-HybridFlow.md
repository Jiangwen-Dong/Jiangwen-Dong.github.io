---
title: "HybridFlow: Adaptive Task Scheduling for Fast and Token-Efficient LLM Inference in Edge-Cloud Collaboration"
collection: publications
category: conferences
permalink: /publication/2026-hybridflow
excerpt: "HybridFlow introduces an adaptive task scheduling framework for efficient LLM inference across edge-cloud environments, optimizing both latency and token usage."
date: 2026-01-20
venue: "ICML"
paperurl: "https://arxiv.org/abs/2512.22137"
citation: 'Dong, Jiangwen, Jiayu Li, and Wanyu Lin. "HybridFlow: Adaptive Task Scheduling for Fast and Token-Efficient LLM Inference in Edge-Cloud Collaboration." ICML 2026.'
---

HybridFlow introduces an adaptive task scheduling framework for efficient LLM inference across edge-cloud environments, optimizing both latency and token usage.

## Framework

<div class="pub-figure">
  <img src="/images/hybridflow-fig1.png" alt="HybridFlow framework overview">
  <p class="pub-figure-caption"><span class="pub-figure-label">Figure 1:</span> HybridFlow operates in two tightly coupled stages: (1) Task Decomposition & Parallel Execution — an edge-side planner decomposes a complex query into a DAG of interdependent subtasks; (2) Resource-Aware Subtask Routing — a lightweight learned router adaptively assigns each subtask to either the edge SLM or the cloud LLM based on a benefit–cost utility score.</p>
</div>

<div class="pub-figure">
  <img src="/images/hybridflow-fig2.png" alt="HybridFlow comparative pipeline">
  <p class="pub-figure-caption"><span class="pub-figure-label">Figure 2:</span> Comparative inference pipeline illustrating how HybridFlow uniquely integrates dependency-aware planning with parallel execution, contrasting it with purely sequential (CoT, DoT) or aggressively parallel (SoT, PASTA) baselines.</p>
</div>
