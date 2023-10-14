---
slides: ""
url_pdf: ""
summary: Query Embeddings using Contrastive Learning without Negative Samples
url_video: ""
date: 2023-10-07T05:07:23.935Z
external_link: ""
url_slides: ""
title: Official Posters for The 4th Asian Para Games Hangzhou 2022
tags:
  - Poster
links:
  - icon: graduation-cap
    icon_pack: fas
    name: Report
    url: https://drive.google.com/file/d/1_-skbKjRM57S6QSk4kMzhOnZT3HgY0ij/view?usp=sharing
image:
  caption: ""
  focal_point: Smart
  filename: featured-01.jpg
url_code: ""
---

Semantic search is an essential topic in Natural Language Processing
(NLP). Mainstream methods usually adopt one same general
large sentence encoder to acquire representations of queries and candidates
and calculate their similarity. However, such methods are still suboptimal
as they ignore the different characteristics of query and candidate corpus.
To this end, we propose Query-BERT, a query embedding specific encoder
to provide high-quality query embedding in a light model way. Inspired
by the success of self-supervised learning (SSL) in computer vision, we
leverage BYOL, a mature image contrastive learning approach without
the need for negative samples, onto query embedding training to acquire
a more robust query representation. Experiments show that under appro-
priate augmentation, our SSL method can reach competitive performance
to the supervised method on Quora question duplicated pairs without big
batch size and negative samples. However, the alignment between Query-
BERT and candidates embedding is not satisfied and demands further
optimization. We hope that this success of transfer learning could moti-
vate people to rethink the appropriate effectiveness utilization of the light
model and the role of domain-specific learning in the machine learning
problem

In the framework comparison, BSL demonstrated better learning ability than
SimSiam. Even the smallest encoder BSL trained could outperform a lot than
well-tuned ALBERT trained by SimSiam, which could be induced to richer learning capacity brought by bi-encoder structure. When substituting MLP
projector with attention projector proved, both encoders trained on BSL and
SimSiam were improved, which indicated that attention projector can more ef-
fectively filter augmentation noise and exact important features from encoding.
In addition, it appeared that exponential moving average can better prevent col-
lapsing and enhance the stability and performance of encoder. Our experiments
show that transfering these computer vision contrastive learning to natural lan-
guage processing task is feasible and successful. Without negative samples par-
ticipated, our query encoder did not collapse and exhibited high quality query
representation.

{{< figure src="projects/qbert/Framework comparison.png" caption="Framework comparison on Quora question duplicated pairs" >}}

In the second part, we trained query encoders on the augmentation data
of MS MARCO Passage Ranking data set to fully unleash the potential of
contrastive learning without negative sampels, and tested them on the same
Quora test set as the first part, whose result can be found in Table 3. With
all augmented data, our finalized architecture in the first part with directional
contrastive loss outperformed selected light augmentation and demonstrated
competitive representation quality to the one trained by supervised mode in
part one. In addition, increasing model size is shown to be a promising way to
acquire better query embedding. Note that straightly using all augmentations
led to worse performance than selected light augmentations, while it performed
better when adopting directional self-supervised learning. Based on that, we
argue that appropriately utilizing all kinds of augmentations in self-supervised
learning can boost model performance than only using light augmentations.

{{< figure src="projects/qbert/Augmentation.png" caption="Augmentation comparison on Quora question duplicated pairs (Unsupervised trained on MS MARCO)" >}}

Query embedding should be different from documents embedding, which leads
us to the motivation of this project, as well as the representation of the results.
On the Quora question duplicated pairs test set, our positive-sample-only con-
trastive learning method demonstrates its superiority and robustness, which can
reach competitive performance to pseudo supervised learning. However, when
aligned with documents embedding, the performance is not satisfied and robust
as it on the query pair test. What indicates here is that our query encoder is
so good at learning query embedding that it is too domain specific to be har-
moniously projected into the document representation space. Here we suggest
that carefully think and develop the use of bi-encoder structure system whether
in NLP or other fields, since reaching expectation respectively does not mean
they could work well as a unity.

Having a much smaller query encoder that can be tuned with unsupervised
learning can be a great advantage to user privacy. We can deploy the small
model on the user devices and update parameters with Federated Learning, 
which is a distributed machine learning paradigm that mathematically ensures user privacy.

{{< figure src="projects/qbert/Online search workflow.png" caption="Online search workflow with trained QBert" >}}
