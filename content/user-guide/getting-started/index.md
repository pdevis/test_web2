---
title: Getting started with CoMet
date: 2024-03-21

# Featured image
# Place an image named `featured.jpg/png` in this page's folder and customize its options here.
#image:
#  caption: 'Image credit: [**Unsplash**](https://unsplash.com)'

authors:
  - RasmaOrmane
  - admin

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

All the relevant information regarding the aims and functionality of CoMet Toolkit is outlined in the [**About Section**]({{< relref "/about" >}}). 

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

For a general approach on determining an uncertainty budget, we refer to the 5-step QA4EO approach. See [this page](user-guide/theory/QA4EO) in our theory section, or the [QA4EO process document](https://qa4eo.org/docs/3_Process_Document.pdf).

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
    3. Structured

  ❕ Typically, each of the input quantities will be affected by **one or more** error effect!

### 🗸 Defining measurement function

  - ❔ What is the analytic expression (i.e. measurement function) of your data? 
  - ❔ Do you have a more complex processing chain using external software?
  - ❔ Can your measurement function be written as a Python function that has the input quantities as arguments, and returns the measurand? 

  Read more about the importance and functionality of **measurement functions** in our page on [**propagating uncertainties through a measurement function**](user-guide/theory/processing-chains/).  

### 🗸 Determining error correlation

Once you have identified the various errors and their types, that are present in your measurements, it's important to consider how these values and errors correlate with one another.

As defined by this FIDUCEO article on ["The origin of error correlation"](https://research.reading.ac.uk/fiduceo/archive/tutorials/the-origin-of-error-correlation/),

  > Correlation is a statistical measure of how two, or more, variables vary together.

To learn more about error correlation structures and examples in the context of Earth Observations, refer our page on [error correlation and how to store it](user-guide/theory/error_correlation).

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

  - store uncertainty and error correlation information
    1. machine readable digital effects tables
    2. UNC specification
  - Propagate uncertainties
    1. 🎲 Monte Carlo (MC)
    2. ⚖️ Law of Propagation of Uncertainty (LPU)
  - Interpolate data & uncertainties
    1. Linear
    2. Quadratic
    3. Cubic 
    4. Gaussian Process Regression (GPR)
    5. Extrapolate data

_Several of the methods listed above apply to more than one of the applications. For more information refer to [examples]({{< relref "/user-guide/examples" >}})._

## 6. 📈 Advanced use.

In this section, we have highlighted certain tips for advanced use of the toolkit. 

### 🗸 Managing memory and runtime

  Certain products may have large RAM requirements, and the MC approach that is often used in CoMet can increase the RAM and runtime requirements by one or more orders of magnitude. 
  
  There are ways to manage memory and runtime, as described in the [punpy documentation](https://punpy.readthedocs.io/en/latest/content/punpy_memory_and_speed.html). 

  For example, often storing the error correlation between all the measurements along all dimensions in a dataset is often prohibitively memory intensive. 
  Instead, it is usually possible to store the error correlation separately between different dimensions. 

  E.g. the **HYPERNETS L2A** surface reflectance data, has a wavelength and series dimension for which the error correlation are stored separately.  
  When propagating this information, using error correlation dictionaries can be useful, (see e.g. the end of [this jupyter notebook example](https://colab.research.google.com/github/comet-toolkit/comet_training/blob/main/hypernets_surface_reflectance.ipynb)).


