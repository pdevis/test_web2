---
title: Examples
summary: How to utilise the various tools within the CoMet Toolkit?
date: 2024-03-19

authors:
  - admin
tags:
  - CoMet
  - punpy
  - comet_maths
  - obsarray

image:
    caption: 'Image credit: [**Unsplash**](https://unsplash.com)'
---

Below, we have compiled a list of relevant examples and linked their corresponding jupyter notebooks with detailed commentary. All the available tools can be used on their own or in conjunction with other modules. For additional information regarding individual packages, refer to the signposted sources throughout the website. 

## 📦 Punpy as a Standalone Package

### 🗸 General use cases

An example showcasing the capabilitites of the [punpy]({{< relref "/tools/punpy" >}}) package can be found [here](https://colab.research.google.com/github/comet-toolkit/comet_training/blob/main/punpy_standalone_example_overview.ipynb).

This jupyter notebook covers the following concepts:

  1. **Calibration** of L0 data to L1
  2. Propagation of various types of uncertainties:
    - **uncorrelated** (random) uncertainties
    - **fully correlated** (systematic) uncertainties
    - uncertainties associated with **structured errors**
  3. **Correlation** along one, two, or more dimensions of a variable
  4. **Multidimensional** input quantities, where a certain correlation structure is known along one dimension, while the other dimensions are random or systematic.

### 🗸 Punpy vs. NIST

We also have compiled some validation examples [here](https://colab.research.google.com/github/comet-toolkit/comet_training/blob/main/NIST_example.ipynb), where the [punpy]({{< relref "/tools/punpy" >}}) results are compared against the NIST uncertainty machine.

Here, we have replicated the following **examples** available on the NIST uncertainty machine [user manual](https://uncertainty.nist.gov/NISTUncertaintyMachine-UserManual.pdf).  

  1. End-gauge calibration
  2. Dynamic viscosity
  3. Resistance
  4. Stefan-Boltzmann constant
  5. Voltage reflection coefficient

❕ All the obtained results are fully consistent with the results of the NIST uncertainty machine.

## 📋 Digital Effects Tables (DET)

### 🗸 Defining DET

A notebook containing examples that define **digital effects tables** is available [here](https://colab.research.google.com/github/comet-toolkit/comet_training/blob/main/defining_digital_effects_table.ipynb). 

It covers the following concepts:

  - How [obsarray]({{< relref "/tools/obsarray" >}}) can be used as a templater for efficiently making **xarray datasets** (both with and without uncertainties)?
  - How, using [obsarray's]({{< relref "/tools/obsarray" >}}) **special variable types** (uncertainties and flags), datasets including detailed uncertainty and covariance information as well as quality flags can be created? 
  - An example for a digital effects table quantifying the uncertainties and error-correlation of the gas temperature, pressure, and the number of moles. Here, the uncertainties can be efficiently and easily propagated through a **measurement function** using [punpy]({{< relref "/tools/punpy" >}}) ([learn more](https://colab.research.google.com/github/comet-toolkit/comet_training/blob/master/training/punpy_digital_effects_table_example.ipynb)).

### 🗸 Utilising obsarray & punpy

1. An example showcasing the application of [obsarray]({{< relref "/tools/obsarray" >}}) can be found [here](https://colab.research.google.com/github/comet-toolkit/comet_training/blob/main/obsarray_example.ipynb).

2. An example of using [punpy]({{< relref "/tools/punpy" >}}) with digital effects tables created with [obsarray]({{< relref "/tools/obsarray" >}}) is explained [here](https://colab.research.google.com/github/comet-toolkit/comet_training/blob/main/defining_digital_effects_table.ipynb).

This notebook outlines how digital effects tables that are created with [obsarray]({{< relref "/tools/obsarray" >}}), can be propagated through a measurement function using [punpy]({{< relref "/tools/punpy" >}}). 

  - At first, we **calculate the uncertainties** in a volume of gas, using the ideal gas law and a digital effects table. 
  - Then we **quantify the uncertainties** and **error-correlation** of the gas temperature, pressure and amount of substance.

## ☄️ Comet_maths interpolation 

### 🗸 How to interpolate data with uncertainties?

A jupyter notebook for **interpolation** with uncertainties can be found [here](https://colab.research.google.com/github/comet-toolkit/comet_training/blob/main/interpolation_example.ipynb).

This example covers the following concepts:

  - Interpolation 
    1. Linear
    2. Quadratic
    3. Cubic
  - **Unknown** input uncertainties (e.g. model uncertainties)
  - **Known** measurment uncertainties
  - Monte Carlo uncertainty propagation
  - Extrapolation
  - 1D interpolation along high-resolution example

## 🗂️ Project specific examples

In this section, we have compiled a list of external projects and examples that have utilised the CoMet Toolkit. 

### 🗸 **HYPERNETS example** 

- 🛰️ LANDHYPERNET flags and uncertainty propagation (through band integration over S2 SRF) is available [here](https://colab.research.google.com/github/comet-toolkit/comet_training/blob/main/hypernets_surface_reflectance.ipynb).