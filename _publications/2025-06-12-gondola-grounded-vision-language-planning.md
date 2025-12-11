---
title: "Gondola: Grounded Vision Language Planning for Generalizable Robotic Manipulation"
collection: publications
permalink: /publication/2025-gondola-grounded-vision-language-planning
excerpt: 'TLDR; Gondola introduces a grounded vision-language planning model that uses multi-view images to generate precise action plans with segmentation masks for generalizable robotic manipulation, achieving state-of-the-art performance on the GemBench benchmark.'
date: 2025-06-12
venue: 'CoRL 2025 LEAP Workshop'
paperurl: 'https://arxiv.org/abs/2506.11261'
citation: 'Shizhe Chen, Ricardo Garcia, Paul Pacaud, and Cordelia Schmid'
---
TLDR; Gondola introduces a grounded vision-language planning model that uses multi-view images to generate precise action plans with segmentation masks for generalizable robotic manipulation, achieving state-of-the-art performance on the GemBench benchmark.

Robotic manipulation faces a significant challenge in generalizing across unseen objects, environments and tasks specified by diverse language instructions. While recent methods incorporate large language models (LLMs) for planning, they often fall short in generating grounded plans in visual environments. We introduce Gondola, a novel grounded vision-language planning model based on LLMs for generalizable robotic manipulation. Gondola takes multi-view images and history plans to produce the next action plan with interleaved texts and segmentation masks of target objects and locations. To support training, we construct three types of datasets using the RLBench simulator: robot grounded planning, multi-view referring expression, and pseudo long-horizon task datasets. Gondola outperforms the state-of-the-art LLM-based method across all four generalization levels of the GemBench dataset, including novel placements, rigid objects, articulated objects and long-horizon tasks.

S. Chen, R. Garcia, P. Pacaud and C. Schmid, "Gondola: Grounded Vision Language Planning for Generalizable Robotic Manipulation," arXiv:2506.11261, 2025.
