---
title: "Implanted, Neuromorphic EEG Sensor System"
excerpt: "Implanted, neuromorphic EEG sensing system for ambulatory, long-term epilepsy monitoring.<br/><img src='/images/neuromorphic-eeg-overview.png' width='300'>"
collection: research
permalink: /research/project-1
---

<i>Note: some details have been left out as this is a work in progress.</i>

## At a Glance
<div style="text-align: justify">
First neuromorphic EEG sensor, designed for purposes of long-term, ambulatory seizure monitoring. The neuromorphic design enables low power consumption and ultra-low bandwidth wireless transmission.
</div>

## Background & Problem Statement

<p align="center">
  <img src="/images/neural-recording.png" alt="Neural Recording" width="300" height="300" style="vertical-align:middle"/>
  <figcaption>Fig.1 - Typical Electrophysiological Methods.</figcaption>
</p>

<div style="text-align: justify">
Some of the main challenges in ambulatory EEG monitoring systems are computation and power consumption. Most EEG headsets are designed to be used in clinical settings where everything has a wired connection. However, ambulatory EEG systems are  critical in many neurological studies, including epilepsy and stroke. In ambulatory/wearable/implanted systems, portability requirements demand lower power consumption and smaller design footprint.
</div>
<div style="text-align: justify">
Conventional brain-machine interface focus on reproduction and transmission of recorded signal for additional off-chip analysis. Transmitting raw neural data wirelessly for processing increases power and bandwidth requirements. 
</div>

## Overview of Project
<p align="center">
  <img src="/images/neuromorphic-eeg-overview.png" alt="Neuromorphic EEG Sensor System Overview" width="600" style="vertical-align:middle"/>
  <figcaption>Fig.2 - System Overview.</figcaption>
</p>
<p align="center">
  <img src="/images/neuromorphic-eeg-arch.png" alt="Neuromorphic EEG Sensor System Architecture" style="vertical-align:middle"/>
  <figcaption>Fig.3 - Close Up of On-Sensor Chip: Neuromorphic Spiking Circuit & SNN.</figcaption>
</p>

<div style="text-align: justify">
This project proposes a novel, implantable EEG sensing system. By leveraging neuromorphic principles and on-chip decoding, the proposed system greatly reduces power and bandwidth requirements. <i>Fig 2.</i> depicts the entire system, the electrodes are placed below the scalp but above the skull bone. The electrodes are interfaced with a neuromorphic spiking circuit, where the raw signals are converted to a spike train. The spike train is then classified by an on-chip spiking neural network (SNN), with the low-bandwidth outcome transmitted wirelessly. <i>Fig 3.</i> depicts the functional schematic of the on-sensor chip.
</div>
<div style="text-align: justify">
The spiking system bypasses the need for a power-intensive ADC and naturally interfaces with an on-chip SNN. The SNN decodes the spike train to classify epileptic state for continuous monitoring and only transmits the classification outcome across inductively coupled data links.
</div>

## System Architecture

<p align="center">
  <img src="/images/neuromorphic-eeg-circuit-schematics.png" alt="Circuit-level Schematics"/>
  <figcaption>Fig.4 - Circuit-level Schematics (Proof-of-concept).</figcaption>
</p>

<div style="text-align: justify">
This section will focus largely on the on-sensor chip. <i>Fig 4.</i> describes the circuit-level simulations (proof-of-concept) for the spiking circuit. The sensed EEG signals are amplified by a low-noise amplifier circuit and then filtered by a cascade of two filters. The filtered signal is then passed into a spiking circuit. The spiking circuit passes the amplified signal through a first-order differentiator and compares the derivative to a set threshold. If the derivative exceeds the threshold, a positive/negative spike is generated. 
</div>
<div style="text-align: justify">
Specifically, spikes are generated if the rate of change in the input signal exceeds a positive or negative threshold - i.e. the spike rate corresponds to rate of change in input. <i>Fig 5.</i> highlights the PCB schematics of the test circuit and <i>Fig 6.</i> and <i>Fig 7.</i> illustrates the signal fidelity and reconstruction tests performed on the spike train output.
</div>
<div style="text-align: justify">
The spike train is then decoded by on-chip SNN to the detect/predict seizure onset.
</div>
<br>
<p align="center">
  <img src="/images/neuromorphic-eeg-pcb.png" width="300" />
  <img src="/images/neuromorphic-eeg-signal-fidelity.png" width="208" /> 
  <figcaption>Fig.5 - PCB; Fig.6 - Signal Fidelity Test</figcaption>
</p>
<p align="center">
  <img src="/images/neuromorphic-eeg-signal-reconstruction.png" />
  <figcaption>Fig.7 - Signal Reconstruction Test</figcaption>
</p>

## My Contributions
* <div style="text-align: justify">Performed literature review on neuro-scientific principles to inform design of neuromorphic circuit</div>
* <div style="text-align: justify">Designed the circuit prototype [incl. amplification, filtering, spiking circuit], first in SPICE using TINA, and then laid out a PCB test circuit, achieving estimated power consumption of 1mW</div>
* <div style="text-align: justify">Created software test bench to verify the spike generation circuit, including signal reconstruction, linearity of circuit, signal-to-noise error ratio</div>
* <div style="text-align: justify">Generated spiking dataset from raw EEG recordings of epileptic seizures for simulated training of on-chip spiking neural networks</div>

## Outcome

Currently in the process of preparing journal paper for submission.