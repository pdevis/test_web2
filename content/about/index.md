---
title: Welcome to CoMet Toolkit!
summary: What is CoMet Toolkit and what can it be used for?
date: 2024-03-19

# Featured image
# Place an image named `featured.jpg/png` in this page's folder and customize its options here.
image:
  caption: 'Image credit: [**Unsplash**](https://unsplash.com)'

authors:
  - admin

# tags:
#   - CoMet
#   - Metrology
#   - Uncertainties
---

<!-- Welcome 👋 -->

## ❔ What is CoMet Toolkit?

  The **Community Metrology** (CoMet) **Toolkit** is a set of open-source software tools that can handle, process, and store measurement data uncertainties and error-correlation information.
 
  The main feature of this toolkit lies in its abilities to deal with the complexities of combining individual uncertainties from various sources, propagating these through any Python measurement function, and quantify and store uncertainty and error correlation information on the outputs. 
  
  This is done in a way that allows the user to use quality assured code, while most of the complexities are handled behind the scenes. This simplifies dealing with uncertainties for experienced and less experienced users alike.  

## 💡 Why is CoMet Toolkit relevant?

  To ensure credible and reliable interpretation of data, the associated uncertainty information ought to be provided. Oftentimes it is made up of a multitude of sources combined through the processing chain. Each source affects the final product at varying levels.
  
  When multiple measurements with uncertainties are combined throughout the processing chain (e.g. performing temporal or spatial averages or integrals, or when fitting a model to the data), it is also critical to take into account the error-correlation information. 
  
  Depending on the error-correlation, the output uncertainty will be different (e.g., random uncertainties are reduced by averaging, but systematic uncertainties are not). To get a correct uncertainty on the final measurand from the combined measurements, 
  the error correlation thus needs to be taken into account for each relevant dimension. 

  CoMet Toolkit accounts for case- and source-specific characteristics of the measurement uncertainties. It can handle:

- any measurement function that can be written as a Python function
- data of any dimension (float/1D/2D/3D/…)
- data with multiple sources of uncertainties
- a wide range of different error correlation structures
- different probability distribution functions
- _many more_

## 📋 What can CoMet Toolkit be used for?

CoMet toolkit can be used to:
  
- define measurement functions in Python
- propagate uncertainties 
- create digital effects table (DTE)
- Automatically parse and propagate uncertainties in DTE
- propagating uncertainties through temporal or spatial averaging
- combining random and systemic uncertainties
- handling random and systemic uncertainties separately
- calculate the uncertainty budget
- _many more_

Initially, CoMet was designed to fulfil the Quality Assurance framework for Earth Observation (**QA4EO**) requirements.
According to these guidelines, all Satellite Earth Observations (EO) and in-situ measurements require their corresponding uncertainty information. 
Where as the CoMet toolkit was designed with the requirements of the EO community in mind, 
it can be applied to any field that requires measurement uncertainty propagation. 

## 📍 Where can CoMet Toolkit be accessed?

  The CoMet Toolkit is available on [**GitHub**](https://github.com/comet-toolkit) with packages installable via pip from the Python Package Index.
  **Examples** demonstrating the capabilities of this toolkit are available [**here**](https://www.comet-toolkit.org/examples/). 

## 👋 Authors & Citations

  **Developed by:** National Physical Laboratory (NPL)
  
  **Funded by:** 
  - **IDEAS-QA4EO:** Instrument Data quality Evaluation and Assessment Service - Quality Assurance for Earth Observation (IDEAS-QA4EO) contract funded by ESA-ESRIN (n. 4000128960/19/I-NS)
  - **NMS:** The UK’s Department for Business, Energy and Industrial Strategy’s (BEIS) National Measurement System (NMS) programme
  
  **Citation:** _De Vis, P. & Hunt, S. E. CoMet Toolkit. [online] National Physical Laboratory. Available at: [(https://www.comet-toolkit.org)](https://www.comet-toolkit.org)_
