---
title: Propagating uncertainties through a processing chain
summary: How are uncertainties propagated through a measurement function
date: 2025-06-14
authors:
  - admin
tags:
  - Uncertainty
  - Measurement function
  - Monte Carlo
  - Law of propagation of uncertainties
image:
  caption: 'Image credit: [**Unsplash**](https://unsplash.com)'
---

In order to propagate uncertainties using the CoMet toolkit, one needs to be able to write the measurement function as a Python function which takes the input quantities as arguments and returns the measurand. Inside this measurement function, there can be a varying range of complexity. It could be a simple analytical function, or a full processing chain, including calls to other external software. The CoMet toolkit treats this measurement function somewhat as a blackbox and simply modifies the inputs, and analyses the outputs. 
