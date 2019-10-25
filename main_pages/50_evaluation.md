---
layout: page
title: Evaluation
permalink: evaluation/
include_in_menu: true
---

Below, the way submissions are evaluated is described.

## Foam phantoms

Each submission for the foam phantom challenges consists of a segmented volume (see [here](https://tomochallenge.github.io/submit/) for more information on how to submit), 
with voxels within the foam material having the value 1, and the voxels with air having the value 0.
To compute error metrics, a ground truth volume at the same resolution is created using the ground truth locations and radii of the voids,
with each voxel labeled as background, foam, large void, medium-sized void, or small void. Using the submitted segmented volume and ground truth volume, the following metrics are computed:

1. Dice score of the foam material: 2 tp/(2 tp + fn + fp), where tp is the total number of foam voxels correctly segmented to 1, fn the total number of foam voxels that are incorrectly segmented to 0, and fp the total number of void voxels that are incorrectly segmented to 1. Note that the background voxels (i.e. those outside the sample) are ignored, since they are trivial to segment correctly as the sample size is easy to determine.
2. Fraction of correctly segmented voxels for large voids: tp/n, where tp is the total number of large void voxels correctly segmented to 0, and n is the total number of large void voxels in the sample.
3. Fraction of correctly segmented voxels for medium-sized voids: tp/n, where tp is the total number of medium-sized void voxels correctly segmented to 0, and n is the total number of medium-sized void voxels in the sample.
4. Fraction of correctly segmented voxels for small voids: tp/n, where tp is the total number of small void voxels correctly segmented to 0, and n is the total number of small void voxels in the sample.
5. Dice score of the foam material for voxels that are on a boundary between foam and air. This score is computed similarly to the first Dice score above, but using only pixels that are on a boundary between foam and air (i.e. foam voxels that have a neighboring air voxel or vice-versa). Here, the outer boundary of the sample is included in the metric computation.

As a final score of the submission, the harmonic mean of all five metrics is used. For the expanding foam phantom, the metrics are computed for the sample at the time that projection number 2688 (out of 3072) is taken. To make a submission for the expanding phantom, please submit only the 3D segmented volume at the time of projection 2688.

The Python script used to compute these metrics is made available in a [GitHub repository](https://github.com/tomochallenge/tomochallenge_utils). Also provided is the ground truth file for the Foam 1 sample, which
can be used to compute the metrics for the training datasets.

## Operando Fuel Cell data

Each submission for the operando fuel cell dataset challenge consists of segmented volumes for 3 selected time steps (see [here](https://tomochallenge.github.io/submit/) for more information on how to submit), with water voxels having the value 1, and the other voxels (air, carbon, platinum, …) the value 0. The time steps considered for the evaluation are the following:

* Time step A – Reconstruction using projection 17701 to 18000 (out of 18060 projections) from sample fuelcell_i2.  
* Time step B  –  Reconstruction using projection 8701 to 9000 (out of 18060 projections) from sample fuelcell_i3.  
* Time step C – Reconstruction using projection 17701 to 18000 (out of 18060 projections) from sample fuelcell_i3.  

Only the central part of each segmented volume (reconstructed slices 240-840 out of 1100) will be evaluated. You can either submitted the full volume or just the relevant slices.

To compute error metrics, ground truth volumes for the corresponding time steps are created through an established reconstruction and segmentation procedure. Using the submitted segmented and corresponding ground truth volumes, the following metrics are computed:

1.	Dice score of water: 2 tp/(2 tp+ fn + fp), where tp is the total number of water voxels correctly segmented to 1, fn the total number of water voxels that are incorrectly segmented to 0, and fp the total number of non-water voxels that are incorrectly segmented to 1. The evaluated volume comprises the catalyst coated membrane, the gas diffusion layer, and the channels (Region 1 in Figure 1).
2.	Dice score of water in one channel (Region 2 in Figure 1).
3.	Dice score of water in the gas diffusion layer region (Region 3 in Figure).
4.	Dice score of water in the membrane region (Region 4 in Figure 1).

![github_fc_pic](https://user-images.githubusercontent.com/56732221/67579034-fc57e900-f743-11e9-92d7-2ceef81811ac.png)
Figure 1 – Reconstructed fuel cell, time step C, slice number 360 of the full volume. The reconstruction has been artificially rotated just for illustration purposes.

As a final score of the submission, the harmonic mean of all four metrics is used.
