---
layout: post
title:  "Fix Your Dataset With Cartography!"
date:   2022-03-14 22:27:23 -0400
categories: jekyll update
---

# [DRAFT]

One of my favorite recent papers, [Dataset Cartography: Mapping and Diagnosing Datasets with Training Dynamics](https://arxiv.org/pdf/2009.10795v2.pdf), introduces the concepts of dataset cartography, data maps, and training dynamics. Dataset cartography, like its name suggests, is the art of mapping the data used to train your deep learning model, whereas training dynamics is the process of concisely generating data maps during the model training process rather than through a potentially costly evaluation step.

## Background
Datasets used to train deep learning models have been growing larger and more complex. Have you ever been examining your deep learning ground truth training data and found something that seemed out of place? 
For example, say you're trying to classify your companies app reviews by sentiment: `positive`, `neutral`, and `negative`. 
While examining model errors after an initial pass at model training, you found this sample improperly classified in your validation dataset:

`"I really love this app...not" -> GT: sentiment_positive, Model: sentiment_negative`

The sentiment of this utterance is labeled as positive, despite having some hardcore sarcasm. It might be better for our models if this was labeled as `sentiment_negative`.
While generating large ground truth training datasets some samples can occasionally get overlooked, and can cause potential biases and confusions in the resulting trained models.

What about this example?

`"This app is good, but this app is also bad" -> GT: sentiment_negative, Model: sentiment_neutral`

This looks like a mixed review and may prompt the addition of a new class for our dataset. It is possible to comb through all the labeled data to try and find any of these samples that require more review, but that process is laborious, expensive, and time consuming. We can instead examine the data map to find the samples that are hard for the selected model to differentiate.

## What is a data map and training dynamics?

A data-map is defined here as "a model-based tool for contextualizing examples in a dataset" and can be used to display a distribution of the easy to learn, hard to learn, or ambiguous samples in the data. Coordinates of a sample in a data-map are generated through training dynamics, the response of a model to that point throughout the training process.

## Get to the code


## Sources: 
* [Dataset Cartography: Mapping and Diagnosing Datasets with Training Dynamics](https://aclanthology.org/2020.emnlp-main.746) (Swayamdipta et al., EMNLP 2020)

* [Dataset Cartography Code](https://github.com/allenai/cartography)