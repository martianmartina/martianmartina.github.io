---
layout: page
title: Recursive Hierarchical Language Modeling
description: Intern at Ant Group, ongoing
img: assets/img/r2d2_long.jpg
importance: 1
category: Research
---
#### TL;DR:
 Augmenting Transformers with multi-grained contextualized representations from recursive composition.

## Structures between Words
We present Recursive Composition Augmented Transformer (ReCAT), a novel recursive encoding layer capable of learning unsupervised contextualized constituent representations in **logarithmic** time, which can be jointly pretrained with Transformers at a large scale.

<div class="row justify-content-sm-center">
    <div class="col-sm-12 mt-3 mt-md-0">
        {% include figure.html path="assets/img/r2d2_long.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Up-and-down composition iterations and following self-attention mechanisms.
</div>

On span-level tasks in the Ontonotes dataset, ReCAT significantly outperforms a vanilla Transformer, under the same pretrained settings. Moreover, the performance of our model is even comparable with that of BERT, with a much smaller pretrained dataset, i.e. wikitext-103.

<div class="row justify-content-sm-center">
    <div class="col-sm-6 mt-3 mt-md-0">
        {% include figure.html path="assets/img/predtree.jpeg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-6 mt-3 mt-md-0">
        {% include figure.html path="assets/img/goldtree.jpeg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Our unsupervised parse trees that align well with human knowledge.
</div>

## Structures within Words

Witnessing the impressive unsupervised parsing capabilities of the R2D2 model, I begin to wonder whether it can also discover structures within words to improve tokenization by exploiting linguistic properties. 

To verify the idea, I am developing a novel tokenizer that tokenizes according to an unsupervised morphological parser and considering future work of extending it to an open-vocabulary language model with latent trees which can make the whole training process completely end-to-end and better optimized. 

Stay tuned!