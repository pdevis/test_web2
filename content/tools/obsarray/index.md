---
# ... Put Your Section Options Here (title etc.) ...
title: obsarray
# subtitle:
# weight: 10  # section position on page
# design:
#   # Choose how many columns the section has. Valid values: 1 or 2.
#   columns: '1'

authors:
  - admin
---

## ❔ What is *obsarray*?

*obsarray* is an extension to xarray for

- defining
- storing
- interfacing 

with uncertainty and measurement error-covariance information in NetCDF files using standardised metadata. 

These datasets that include standardised uncertainty and error-covariance information are dubbed **'digital effects tables'**.

## 📍 Where can *obsarray* be found?

- The *obsarray* documentation is available [here](https://obsarray.readthedocs.io/en/latest/).
- There are also jupyter notebooks available in the [example section](user-guide/examples/).

## 📋 What can *obsarray* tool be used for?

Although storage of full error-covariance matrices for large observation datasets is not practical, they are often structured to an extent that allows for simple parameterisation. 

*obsarray* makes use of a parameterisation method for error-covariance information, first developed in the **FIDUCEO** project, stored as attributes to uncertainty variables. In this way the datasets can be written/read in a way that this information is preserved.

One important aim of CoMet is to abstract away the complexity of dealing with error-covariances. *obsarray* does this by saving all error-correlation information in standardised metadata together with the uncertainty variables (and the input quantities themselves) in one dataset. These `digital effects tables' can then be passed to *punpy*, which can directly use this information, so that users typically never have to interact with it. This allows efficient and easy uncertainty propagation.
