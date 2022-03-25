---
layout: post
title:  "Fix Your Dataset With Cartography!"
date:   2022-03-14 22:27:23 -0400
categories: jekyll update
---

# Fix Your Dataset With Cartography! [DRAFT]

One of my favorite recent papers is [Dataset Cartography: Mapping and Diagnosing Datasets with Training Dynamics](https://arxiv.org/pdf/2009.10795v2.pdf)


## What is dataset cartography?
Datesets used to train deep learning models have been growing larger and more complex. Have you ever been examining your deep learning ground truth training data and found something that seemed out of place? 
For example, say youre trying to classify your companies app reviews into different sentiments `positive`, `neutral`, and `negative`. 
While examining model errors after an initial pass at model training, you found this sample impropperly classified in your validation dataset:

`"I really love this app...not" -> GT: sentiment_positive, Model: sentiment_negative`

The sentiment of this utterance is labeled as positive, despite having some hardore sarcasm. It might be better for our models if this was labeled as `sentiment_negative`.
While generating large ground truth training datasets some samples can occasionally get overlooked, and can cause potential biases and confusions in the resulting trained models.

What about this example?

`"This app is good, but this app is also bad" -> GT: sentiment_negative, Model: sentiment_neutral`

This looks like a mixed review and may prompt the addition of a new class for our dataset

Dataset cartography, like its name suggests, is the art of mapping the data used to train your deep learning model.

## What is a datamap?

A datamap displays a distribution of the easy to learn, hard to learn, or ambiguous samples in the data.

## How to map your dataset


## Sources: 
* [Dataset Cartography: Mapping and Diagnosing Datasets with Training Dynamics](https://aclanthology.org/2020.emnlp-main.746) (Swayamdipta et al., EMNLP 2020)

* [Dataset Cartography Code](https://github.com/allenai/cartography)