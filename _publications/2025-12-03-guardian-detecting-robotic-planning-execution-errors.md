---
title: "Guardian: Detecting Robotic Planning and Execution Errors with Vision-Language Models"
collection: publications
permalink: /publication/2025-guardian-detecting-robotic-planning-execution-errors
excerpt: 'TLDR; Guardian introduces an automatic robot failure synthesis approach that generates diverse planning and execution failures with fine-grained reasoning traces. We train a VLM that achieves state-of-the-art performance on failure detection benchmarks and effectively improves task success rates in both simulation and real robots.'
date: 2025-12-03
venue: 'CoRL 2025 Workshop Robot Data'
paperurl: 'https://arxiv.org/abs/2512.01946'
citation: 'Paul Pacaud, Ricardo Garcia, Shizhe Chen, and Cordelia Schmid'
header:
  teaser: gteaser.png
---
TLDR; Guardian introduces an automatic robot failure synthesis approach that generates diverse planning and execution failures with fine-grained reasoning traces. We train a VLM that achieves state-of-the-art performance on failure detection benchmarks and effectively improves task success rates in both simulation and real robots.

Robust robotic manipulation requires reliable failure detection and recovery. Although current Vision-Language Models (VLMs) show promise, their accuracy and generalization are limited by the scarcity of failure data. To address this data gap, we propose an automatic robot failure synthesis approach that procedurally perturbs successful trajectories to generate diverse planning and execution failures. This method produces not only binary classification labels but also fine-grained failure categories and step-by-step reasoning traces in both simulation and the real world. With it, we construct three new failure detection benchmarks: RLBench-Fail, BridgeDataV2-Fail, and UR5-Fail, substantially expanding the diversity and scale of existing failure datasets. We then train Guardian, a VLM with multi-view images for detailed failure reasoning and detection. Guardian achieves state-of-the-art performance on both existing and newly introduced benchmarks. It also effectively improves task success rates when integrated into a state-of-the-art manipulation system in simulation and real robots, demonstrating the impact of our generated failure data.

P. Pacaud, R. Garcia, S. Chen and C. Schmid, "Guardian: Detecting Robotic Planning and Execution Errors with Vision-Language Models," arXiv:2512.01946, 2025.
