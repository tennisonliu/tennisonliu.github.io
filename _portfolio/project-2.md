---
title: "Honours Thesis: Deep Learning Driven Epilepsy Diagnosis"
excerpt: "Novel deep learning algorithm for classifying epileptic conditions from scalp EEG signals.<br/><img src='/images/hybrid-epilepsy-epilepsy.png' width='300'>"
collection: research
permalink: /research/project-2
---

## At a Glance
<div style="text-align: justify">
Novel hybrid bilinear deep neural network achieved state-of-the-art accuracy in epileptic seizure classification using scalp-EEG. Proposed algorithms exhibit generalisation across unseen datasets and high discriminative ability between similar EEG patterns.
</div>

## Background & Problem Statement
<p align="center">
  <img src="/images/hybrid-epilepsy-epilepsy.png" alt="Epilepsy" width="300" style="vertical-align:middle"/>
  <figcaption>Fig.1 - Epilepsy manifested in EEG signals.</figcaption>
</p>
<div style="text-align: justify">
Critical treatment and prognosis procedures for epilepsy start with and rely on the correct identification of epileptic seizure type. Video-EEG is the most common diagnostic tool that neurologists use to support a diagnosis. However, EEG based epilepsy diagnosis is often confounded by several factors: 
</div>
* <div style="text-align: justify">Overlapping clinical and EEG features across different epilepsy types makes identifying key bio-markers difficult</div>
* <div style="text-align: justify">Inherent subjectivity in visual examination (of EEG) contributes to variability in clinical interpretation based on the EEG reader’s level of expertise </div>
* <div style="text-align: justify">Visual examination of video-EEG results in a tedious and time-consuming process particularly where hour’s or day’s worth of EEG needs to be reviewed visually</div>
<div style="text-align: justify">
The uncertainty inherent in contemporary seizure diagnostic tools motivated this investigation into developing novel deep learning algorithms that can classify epileptic seizures at high accuracy.
</div>

## Algorithm

<p align="center">
  <img src="/images/hybrid-epilepsy-bilinearmodel.png" alt="Hybrid Bilinear Model" width="400" style="vertical-align:middle"/>
  <figcaption>Fig.2 - Hybrid Bilinear Model. The feature extractors in the model can be replaced with any ML extractor. Here, I have chosen to use a CNN and ConvLSTM.</figcaption>
</p>

<p align="center">
  <img src="/images/hybrid-epilepsy-cnn.png" width="400" alt="CNN Extractor"/>
  <img src="/images/hybrid-epilepsy-rnn.png" width="400" alt="ConvLSTM Extractor"/> 
  <figcaption>Fig.3a) - CNN Feature Extractor; Fig.3b) - ConvLSTM Feature Extractor</figcaption>
</p>
<div style="text-align: justify">
This study proposes the use of bilinear models for the purpose of seizure-type classification. Bilinear models have been shown to be exceptionally effective at fine-grained recognition and differentiating between similar patterns (e.g. classification of different dog breeds). There is considerable overlap in EEG patterns between certain epilepsy types, which motivated the use of the more discriminative bilinear architecture.
</div>
<div style="text-align: justify">
<i>Fig 2.</i> illustrates the architecture of the hybrid bilinear network - the outputs of the 'base' feature extractors are multiplied through  matrix outer product to derive the bilinear vector. The hybrid-bilinear model investigated in this work employs both CNN and RNN as feature extractors, where one network (ConvLSTM) extracts temporal features and the other (CNN) models spatial features, which are combined into second-order statistics through bilinear pooling. <i>Fig 3.</i> describes the two 'base' feature extractors used in this study. Note that the feature extractors can be replaced with any ML extractor. The training process for the bilinear algorithm is detailed in <i>Fig 4.</i>
</div>

<p align="center">
  <img src="/images/hybrid-epilepsy-training.png" alt="Training Algorithm" width="200" style="vertical-align:middle"/>
  <figcaption>Fig.4 - Bilinear Model Training Steps.</figcaption>
</p>

## Results
<div style="text-align: justify">
The algorithm was trained/evaluated on two datasets - the Temple University Hospital Seizure Corpus (TUH) and the EPILEPSIAE dataset. On the TUH dataset, the hybrid model achieved F1-score of 97.40%, exceeding the previously established benchmark. 
</div>
<div style="text-align: justify">
The same algorithm, without any adjustments to the architecture, was trained and evaluated on the EPILEPSIAE dataset, achieving a comparable performance of 97.00%. The comparable results achieved on EPILEPSIAE demonstrates the generalisation ability of the algorithm. Since EPILEPSIAE is a significantly smaller dataset, the results also demonstrate the ability for the algorithm to learn from smaller amounts of data.
</div>
<div style="text-align: justify">
The bilinear models work well as the bilinear vector obtained by multiplying the output of feature extractors can effectively model interactions between pairs of local features.
Thus, they can discriminate well when the input data is similar and can thus differentiate similar EEG artifacts in different seizure classes.
</div>

## My Contributions
<div style="text-align: justify">
This project was independently proposed and completed by myself for my undergraduate Honour's Thesis. To learn more, please refer to this <a href="https://ieeexplore.ieee.org/abstract/document/9055195">published paper.</a>
</div>