---
title: Getting started with CoMet
date: 2024-03-21

# Featured image
# Place an image named `featured.jpg/png` in this page's folder and customize its options here.
#image:
#  caption: 'Image credit: [**Unsplash**](https://unsplash.com)'

authors:
  - RasmaOrmane

tags:
  - CoMet
  - Metrology
  - Uncertainties
  - comet_maths
  - obsarray
  - punpy
---

Welcome 👋

In this brief guide we will walk you through the basic steps and prerequisists to get started with CoMet. 

## 1.💡 Get familiar with the toolkit and its capabilitites. 

All the relevant information regarding the aims and functionality of CoMet Tolkit is outlined in the [**About Section**]({{< relref "/about" >}}). 

But, in a nutshell, 

  > CoMet stands for **Community Metrology Toolkit** and it a set of software tools that handle, process, and store measurement data uncertainties and error-correlation information.

It accounts for case- and source-specific characteristics of the measurements, and can be used to quantify uncertainties and the uncertainty budget, create digital effects tables, and overall validate measurements. 

At this time, there are three individual tools:

    1. obsarray
    2. punpy
    3. comet_maths

but more modules are planned to be developed and included in the future. For more detail, refer to the [**Tools Section**]({{< relref "/#tools" >}}). 

## 2. 🗃️ Characterise the data/measurements that require the uncertainty propagation. 

The main purpose of these tools, is to propagate uncertaintites. To do that, you must have an overall understanding of the type of data/measurements you are working with. 

To help you identify all the relevant information from your dataset, we have compiled a list of relevant questions and tips.

### 🗸 General 

  - ❔ What kind of data do you have?
  - ❔ Does it require any pre-processing or filtering?
  - ❔ How many datapoints do you have? Is the data memory-heavy?

### 🗸 Quantifying uncertainties on input quantities

  - ❔ Can you list all the input quantities of your measurements?
  - ❔ Can you identify all the error sources?
  - There are three types of errors, each with their own characteristics: 
    1. Random
    2. Systematic
    3. Structured random

  ❕ Each of the input quantities will be affected by **one or more** error effect!

### 🗸 Defining measurement function

  - ❔ What is the analytic expression (i.e. measuremet function) of your data? 

  Read more about the importance and functionality of **measurement functions** in this [FIDUCEO tutorial](https://research.reading.ac.uk/fiduceo/archive/tutorials/measurement-function-pt1/#:~:text=Often%2C%20we%20are%20able%20to%20explicitly%20write%20the,X%20i%2C%20via%20the%20functional%20relationship%20f%20f.).

### 🗸 Determining error correlation

Once you have identified the various errors and their types, that are present in your measurements, it's important to consider how these values and errors correlate with one another.

As defined by this FIDUCEO article on ["The origin of error correlation"](https://research.reading.ac.uk/fiduceo/archive/tutorials/the-origin-of-error-correlation/),

  > Correlation is a statistical measure of how two, or more, variables vary together.

To learn more about error correlation structures and examples in the context of Earth Observations, refer this [FIDUCEO tutorial](https://research.reading.ac.uk/fiduceo/archive/tutorials/evaluating-error-correlation/). 

## 3. 🧾 Identify similarities between your specific requirements and the available examples.

  - Look through the available [examples]({{< relref "/user-guide/examples" >}}) and documentation. 
  - Plan out how the toolkit can be applied to your specific case study.
  - ❔ Which tools and in what order will you use? 

## 4. 🖥️ Install the tools

All the available tools are  available on [GitHub](https://github.com/comet-toolkit) and installable via pip:

    - pip install comet_maths
    - pip install punpy
    - pip install obsarray

  _Installing **punpy** will automatically install comet-maths and obsarray._


## 5. ✔️ Perform the uncertainty estimation and interpret the results. 

After defining a measurement function, installing and importing all the relevant packages and data, it's time to benefit from the power of CoMet! 

### 🗸 Method breakdown

A general overview of the various capabilitites and methods are combiled bellow. 

  - Propagate uncertainties
    1. 🎲 Monte Carlo (MC)
    2. ⚖️ Law of Propagation of Uncertainty (LPU)
    3. ⛰️ Gaussian Process Regression (GPR)
    4. 📈 Standard deviation
  - Interpolate data & uncertainties
    1. Linear
    2. Quadratic
    3. Cubic 
  - Extrapolate data
    1. Analytical method
  - Plot results

_Several of the methods listed above apply to more than one of the applications. For more information refer to [examples]({{< relref "/user-guide/examples" >}})._

## 6. 📈 Advanced use.

In this section, we have highlighted certain tips for advaced use of the toolkit. 

### 🗸 Managing memory and runtime

  - Certain products may have large RAM requirements.
  
  For example, to propagate uncertainties for all of the **HYPERNETS L2B** surface reflectance data series, [punpy]({{< relref "/tools/punpy" >}}) would have to calculate a very large correlation matrix.

  This can be avoided, by utilising **error correlation dictionaries**, which will take much less memory. 
  
  Full example code for this adjustment is available [here](https://colab.research.google.com/github/comet-toolkit/comet_training/blob/main/hypernets_surface_reflectance.ipynb).


  <!-- 
  
  Things to include here from Pieter

  One section I would add at the end is on `advanced use' or `managing memory and runtime' or something like that, which could point to https://punpy.readthedocs.io/en/latest/content/punpy_memory_and_speed.html and other resources for how to deal with more complex/large datasets (which tend to be what people really need in practise). 
  
  in step 4, there is not pip install comet, but there is a pip install punpy, pip install obsarray and pip install comet_maths   (note that the punpy install also installs the other two as dependencies). in step 5, I would say uncertainty propagation rather than estimation . Is uncertainty estimation of input quantities (i.e. compiling the actual values from documentation/literature/expert knowledge) part of step 2? Or should that be a separate step after step 2? We should make sure to link this to the QA4EO `steps to an uncertainty budget' (https://qa4eo.org/docs/3_Process_Document.pdf)
  
  Maybe under step 2, there could be a few subsections (e.g. general/defining measurement function/quantifying uncertainties on input quantities/determining error correlations)?
  
  -->