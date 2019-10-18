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

As a final score of the submission, the harmonic mean of all five metrics is used.

The Python script used to compute these metrics is made available in a [GitHub repository](https://github.com/tomochallenge/tomochallenge_utils). Also provided is the ground truth file for the Foam 1 sample, which
can be used to compute the metrics for the training datasets.

