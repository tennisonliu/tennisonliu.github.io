---
title: "Implanted, Neuromorphic EEG Sensor System"
excerpt: "Implanted, neuromorphic EEG sensing system for ambulatory, long-term epilepsy monitoring<br/><img src='/images/500x300.png'>"
collection: research
permalink: /research/project-1
---

At a Glance

First known, neuromorphic implementation of EEG sensor for purposes of long-term, ambulatory monitoring. Neuromorphic paradigm enables low power consumption and ultra low bandwidth wireless transmissino.

Background & Problem Statement

[insert some eeg sensor graphic]

EEG signals are very small (10uV range for external, 100uV for iEEG) and noisy.

Issue is on computation and power consumption, which may not be an issue in clinical settings where everything has wired connection. However, in ambulatory systems, portability requirements demand lower power consumption.

Transmitting raw neural data wirelessly for processing increases power and bandwidth requirements.

Conventional BMI systems focus on reproduction and transmission of recorded signal to remote systems for additional analysis. Propose alternative EEG sensing system that interfaces to an embedded neuromorphic spiking circuit for feature extraction and transmitting low-bandwidth outcome.

Overview of Project
Neural sensing + spiking system which converts sensed signals into spike events. The spiking system bypasses the need for a power-intensive ADC and naturally interfaces with an on-chip Spiking Neural Network. The SNN decodes/classifies the spike train to classify epileptic state for continuous monitoring and only transmits the classification outcome across inductively coupled data links.

[insert system architecture]

System Architecture
[insert circuit schematic]
[insert PCB schematic]

Sensed EEG signals -> amplified by low-noise amplifier circuit -> filtered by cascade of two band-pass filters -> spike event generating circuit [first-order differentiator, threshold detection circuit] -> classification circuit (SNN)/wireless power transfer

Spike event generating circuit generates either positive or negative spike if input signal changes by a fixed positive or negative threshold. Spike rate corresponds to rate of change in input.

Spike train decoded by on-chip SNN to predict/detect seizure onset.


My Contributions
[insert reconstruction test x 2]

* performed literature review on neuro-scientific principles to inform design of neuromorphic circuit
* designed the circuit prototype [incl. amplification, filtering, spiking circuit], first in SPICE using TINA, and then laid out a PCB test circuit
* created software test bench to verify the spike generation circuit, including signal reconstruction, linearity of circuit, signal-to-noise error ratio
* generated spiking dataset from raw EEG recordings of epileptic seizures for simulated training of on-chip spiking neural networks

Outcome
Currently in the process of preparing journal paper for submission.