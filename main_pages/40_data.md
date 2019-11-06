---
layout: page
title: Data
permalink: data/
include_in_menu: true
---

The data for all challenges are made available through [TomoBank](https://tomobank.readthedocs.io/) [[1]](#note1), which uses [Globus](https://www.globus.org/) to distribute files. A (free) Globus account is required to download the data. More information about using TomoBank can be found [here](https://tomobank.readthedocs.io/en/latest/source/usage.html). Below, specific links to datasets for each specific challenge are given.

## Foam phantoms

The data for the simulated foam phantoms is available [here](https://tomobank.readthedocs.io/en/latest/source/phantom/docs.phantom.foams.html#challenge), including a detailed description. The data of Foam 1 (phan_00016 to phan_00022 on TomoBank) can be used for training and testing of your algorithms, while results should be submitted for the other provided foam samples (phan_00023 to phan_00028 on TomoBank).

## Fuel cell data

The data for the dynamic fuel cell experiment is available [here](https://tomobank.readthedocs.io/en/latest/source/data/docs.data.dynamic.html#fuel-cell-data), including a detailed description. The data is available from a single Globus folder (tomo_00081 on TomoBank), which includes three datasets (fuelcell_i1.h5, fuelcell_i2.h5, and fuelcell_i3.h5).

## Nano CT data

Are you looking for an even harder problem? We have some nanoCT data that is difficult even for state-of-the-art methods! We have data sets measured using Zernike phase contrast, [here](https://tomobank.readthedocs.io/en/latest/source/data/docs.data.nano.html#zernike), and requiring PSF deconvolution, [here](https://tomobank.readthedocs.io/en/latest/source/data/docs.data.nano.html#psf), both available through TomoBank, including a detailed description. This data is not yet officially part of the TomoChallenge -- we do not have an official submission script or a way to display submissions on the results page or a way quantitatively evaluate results. We are hoping to soon add all of this for some of these data sets; until then, if you work on this data, feel free to upload your results (through the globus endpoint, see the submission page) and we will reach out to discuss with you more!

## References

1. <a name="note1"></a> De Carlo, Francesco, et al. "TomoBank: a tomographic data repository for computational x-ray science." *Measurement Science and Technology* 29.3 (2018): 034004.
