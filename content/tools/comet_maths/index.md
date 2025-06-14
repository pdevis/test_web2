---
title: comet_maths

authors:
  - admin
---

## ❔ What is *comet_maths*?

*comet_maths* is a python module with useful mathematical algorithms (including interpolation with uncertainties) for general use as well as for use in the other tools in the CoMet toolkit.

## 📍 Where can *comet_maths* be found?

The *comet_maths* documentation is available [here](https://comet-maths.readthedocs.io/en/latest/).
There are also jupyter notebooks available in the [example section](/user-guide/examples/).

## 📋 What can *comet_maths* tool be used for?

There are quite a range of different functionalities within *comet_maths*. There are currently three submodules. One for linear algebra (mainly used for matrix operations in both *obsarray* and *punpy*), one for random generators (mainly used for sample generation in *punpy*) and one for interpolation (for general use).

## ✔️ Interpolation using *comet_maths*

The interpolation submodules focuses on two aspects. First, it aims to provide interpolation uncertainties that are as realistic as possible, and include both a contribution from the uncertainty on the input data point, as well as a contribution from the uncertainty in the model used for interpolation. Second, the interpolation module has functionality to interpolate between some low-resolution data points following a high resolution example. The example spectrum gets scaled in order to go through the low-resolution data points to form a sensible interpolation. For more info, see the [*comet_maths* documentation](https://comet_maths.readthedocs.io/en/latest/). 