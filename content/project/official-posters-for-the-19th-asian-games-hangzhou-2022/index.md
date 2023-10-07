---
slides: ""
url_pdf: ""
summary: It adopts the timeless pixel style to directly convey the core
  information of the Hangzhou Asian Games. The poster combines pixel style to
  reflect the "smart technology" of the Hangzhou Asian Games, looking back to
  the past and looking forward to the future. The dynamic process of the whole
  poster reminds us of the pixel-based pictures of old computers and red and
  white game consoles, and we played pixel games together. The 2022 Hangzhou
  Asian Games, let's play together!
url_video: ""
date: 2023-10-07T05:10:13.487Z
external_link: ""
url_slides: ""
title: Official Posters for The 19th Asian Games Hangzhou 2022
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
  filename: featured.png
url_code: ""
---


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