---
title: "Honours Thesis: Deep Learning Driven Epilepsy Diagnosis"
excerpt: "Novel deep learning algorithm for classifying epileptic conditions from scalp EEG signals<br/><img src='/images/500x300.png'>"
collection: research
permalink: /research/project-2
---

At a Glance



Background & Problem Statement

Critical treatment and prognosis procedures all rely and start with the correct identification of epileptic seizure type. Video-EEG is the most common diagnostic tool that neurologists use to support a diagnosis. However, EEG based epilepsy diagnosis is often confounded by several factors: 
* inherent subjectivity in visual examination also contributes to variability in clinical interpretation based on the EEG reader’s level of expertise
* overlapping clinical and EEG features across different epilepsy types makes identifying key bio-markers difficult
* neurologists then visually examine these video-EEG records, resulting in a tedious and time-consuming process particularly where hour’s or day’s worth of EEG needs to be reviewed visually

The uncertainty inherent in contemporary seizure diagnostic tools motivated investigation into developing novel deep learning algorithms that can classify epileptic seizures at high accuracy.

Algorithm

This study proposes the use of bilinear models for the purpose of seizure-type classification. Bilinear models have been shown to be exceptionally effective at fine-grained recognition and differentiating between similar objects (e.g. classification of different dog breeds)

The hybrid model employs both CNN and RNN as feature extractors, where one network (ConvLSTM)
extracts temporal features and the other (CNN) models spatial features, which are combined into second-order statistics through bilinear pooling

Results
On the TUH dataset, the CNN and RNN alone do remarkably well, achieving F1-score of 95.50% and 95.80% on the STFT data, respectively. The symmetric bilinear models further improved the
classification performance by achieving 96.70% and 96.90% and the hybrid model achieves the best performance with F1-score of 97.40%.

EPILEPSIAE dataset, achieving F1-score of 87.3% and 89.0% on the base CNN and RNN models, respectively. The B-CNN model achieved 93.7% while the B-RNN achieved 94.9%. Once again, the hybrid model achieves the best performance of 97.0%.

Ability to generalise and learn from smaller amounts of data.

The bilinear models work well as the bilinear vector obtained by multiplying the output of feature extractors can effectively model interactions between pairs of local features.
Thus, they can discriminate well when the input data is similar and can thus differentiate similar EEG artifacts in different seizure classes

My Contributions
This project was independently proposed and completed by myself for my undergraduate Honour's Thesis.

Outcome
