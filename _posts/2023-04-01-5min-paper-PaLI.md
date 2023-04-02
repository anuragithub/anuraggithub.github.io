---
layout: post
title:  5-Minute Papers :- PaLI
date:   2023-01-23 16:40:16
description: PaLI by google-research is a jointly-scaled multilingual Language-Image Model
tags: computer vision, language models
categories: sample-posts
---
### TL;DR

PaLI(Pathways Langauge and Image Model) introduces as class of vision-language models that are scalable and flexible in its interface.
Flexibility depicts the ability of the model to perform various types of downstream tasks like image captioning, visual question answering, and scene-text understanding. It outperforms existing SOTAs even with being trained with lesser number of parameters, and excels at many tasks even in multi-lingual setups. 
New Additions: 
* Largest ViT model till date i.e. ViT-e 
* Multi-lingual support
* Mix of pre-training tasks enabling model with wide range of downstream capabilities.
* Scalable and re-usable modular components.
* Mix of single and dual stream architecture.
<hr>

#### Architecture
{% include figure.html path="assets/img/pali_arch.png" class="img-fluid rounded z-depth-1" %}
Major Components:
* ViT for image encoding (ViT-e)
* Text Encoder-Decoder transformers architecture (pre-trained mT5)
* No task based head, but prompts are used to differentiate between the tasks

<hr>
#### Pre-training and Fine-tuning process
For both the pre-training and fine-tuning, same model is used. The model accepts input as an image and a text string, generated text string as outputs. As mentioned before, there are task specific heads used in the model, but instead text-based prompts are used to indicate the type of task at hand. 

<hr>
#### Prompt-based tasks mixture
To incorporate diverse tasks, the text-based prompts corresponding to different tasks is used. Examples of few are listed, more exhaustive description can be found be in the original [paper](https://arxiv.org/pdf/2209.06794v2.pdf).

* Captioning task
SplitCap on WebLI alt-text data
Prompt: "Generate the alt-text in <lang> at <pos>: <cap1> <extra_id_0>
Target: <cap2>

* English and Cross-Lingual VQA
Triplets => <Image, [question], [answer]>
Prompt: "Answer in EN: [question] <extra_id_0i>"
Target: [answer]

<hr>

#### Experiments and Results
As per the paper, PaLI outperforms the current SOTAs across various benchmarks in various downstream tasks. Summary of performance in Image captioning and VQA is displayed below:
{% include figure.html path="assets/img/pali_results.png" class="img-fluid rounded z-depth-1" %}

#### References
Original Paper: [arxiv](https://arxiv.org/pdf/2209.06794v2.pdf)
Google blog: [blog](https://ai.googleblog.com/2022/09/pali-scaling-language-image-learning-in.html)