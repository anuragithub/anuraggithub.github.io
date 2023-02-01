---
layout: post
title:  The new vision langauge affair
date:   2023-01-23 16:40:16
description: Closer look at various vision-langauge pre-training models (specifically VLP)
tags: computer vision, language models
categories: sample-posts
---
Understanding modalities first!

Computer vision and language modelling co-existed and covered the major percentage of machine learning research ever since the burst of feasible and accessible computation. Tasks involving multiple modalities have been studied/researched for years, but the generalization capabilities of transformer based models have opened a new paradigm to venture to.
Modalities in literal sense refers to the way information is represented. Therefore, multi-modal means a setup having data of different modalities or representations in their crude form. These modalities can be image, text, audio, video etc. There's another term widely used in such context which is cross-modal learning or paradigm, which means learning via utlizing different modalities to understand/generation knowledge representation of the target objective. Multi-modality doesn't necessarily means that all modalities will be exploited to understand the scene/target better.


Pre-training/transfer learning in a nutshell!

In order to achieve strong results or performance using deep learning, usually it takes a vast amount of data related to the task at hand with significant computation capability. Furthermore, general machine learning models have the underlying assumption that the distribution of training and test data is similar in the feature space. These assumptions are often not valid in real-world problems and hence this poses an impending
challenge. Transfer learning or knowledge transfer allows for tackling these challenges. The very traditional work and motivation for the use of transfer learning methodology date back to 19951. Over the past decade, or so has seen many different evolution and forms of this technique. Even with varied names and forms, the core essence of transfer learning is to utilize the knowledge obtained from an initial task or source task and apply it to improve the performance of the learning to a different task
or be a target task.


<hr>
So, the obvious question here is why to use different modalities and what advantage do we get by doing so. This can be answered by mix of techniques and solutions. Depending upon task at hand, using multi-modal and cross-modal can help in achieving better results as shown in recent research in the field. To categorize these to understand well, we use certain aspects to split these models as mentioned in recent paper by Chen et. al 2022.

### Key aspects to split the model types:
<ul>
    <li>Model architecture</li>
    <li>Pre-training objectives</li>
    <li>Downstream tasks</li>
</ul>
Here, we briefly describe these aspects which will be then explored in details. Also, keep in mind there can be overlap between these aspects as models would fit in more than one category.

Model architectures: How one trains the different modal models determines the architecture of VLP models. This also, overlaps with terms discussed before of multi-modal and cross-modal models. Either the model can be single stream i.e takes the feature representations from both the vision and language model and concates them onto the rest of the network, or trains them separately while having cross sharing of features using something like cross-attention.
This will be discussed in detail in upcoming blog.

Pre-training objectives: 
What representations are learnt via network conjointly is primarily determined by the loss function or learning objective. Some of the main ones known in vision-langauge paradigm are as follows:
Completion : Masked image or language modelling in which certain portions of data are attempted to reconstruct given some unmasked ones.
Matching : Collectively using both signals to understand the task at hand better.
Temporal : Distruptions are added by re-ordering certain sequences to make models robust.
Special cases: Visual question answering and captioning objectives.

Downstream tasks:
More often than not, downstream tasks determine the model type. Certain models are trained in two step process. The key terms here are Upstream components which are the ones involved
during the pre-training phase and downstream components are those involved in fine-tuning for specific tasks. For example, you train a vision langauge model to obtain certain feature representations and then use these to perform specific tasks like visual question answering etc.


These categories will be discussed in depth in next ones.
<hr>