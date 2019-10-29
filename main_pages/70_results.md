---
layout: page
title: Results
permalink: results/
include_in_menu: true
---

This page will show the scores for the submissions so far, and will be updated every time new results are submitted.

## Foam phantoms

The shown metrics are (see [here](https://tomochallenge.github.io/evaluation/) for more information):

* DF: Dice score of the foam material.
* LV: Fraction of correctly segmented voxels for large voids.
* MV: Fraction of correctly segmented voxels for medium-sized voids.
* SV: Fraction of correctly segmented voxels for small voids.
* DE: Dice score of the foam material for voxels that are on a boundary between foam and air.
* HM: Harmonic mean of all other scores.

### Limited angle

| Name                         | By     | DF | LV | MV | SM | DE | HM  |
|:-----------------------------|:-------|:-----------:|:-----------:|:------------:|:-----------:|:-----------:|:-----:|
| ASTRA FBP_CUDA [[1]](#note1) | dmpelt |       0.845 |       0.963 |        0.951 |       0.898 |       0.814 | 0.890 |

### Noisy

| Name                         | By     | DF | LV | MV | SM | DE | HM  |
|:-----------------------------|:-------|:-----------:|:-----------:|:------------:|:-----------:|:-----------:|:-----:|
| ASTRA FBP_CUDA [[1]](#note1) | dmpelt |       0.571 |       0.821 |        0.805 |       0.758 |       0.695 | 0.717 |

### Missing wedge

| Name                         | By     | DF | LV | MV | SM | DE | HM  |
|:-----------------------------|:-------|:-----------:|:-----------:|:------------:|:-----------:|:-----------:|:-----:|
| ASTRA FBP_CUDA [[1]](#note1) | dmpelt |       0.836 |       0.994 |        0.977 |       0.878 |       0.748 | 0.877 |

### Blur

| Name                         | By     | DF | LV | MV | SM | DE | HM  |
|:-----------------------------|:-------|:-----------:|:-----------:|:------------:|:-----------:|:-----------:|:-----:|
| ASTRA FBP_CUDA [[1]](#note1) | dmpelt |       0.860 |       0.994 |        0.976 |       0.863 |       0.750 | 0.880 |

### Artifacts

| Name                         | By     | DF | LV | MV | SM | DE | HM  |
|:-----------------------------|:-------|:-----------:|:-----------:|:------------:|:-----------:|:-----------:|:-----:|
| ASTRA FBP_CUDA [[1]](#note1) | dmpelt |       0.811 |       0.949 |        0.936 |       0.884 |       0.804 | 0.873 |

### Expanding

| Name                         | By     | DF | LV | MV | SM | DE | HM  |
|:-----------------------------|:-------|:-----------:|:-----------:|:------------:|:-----------:|:-----------:|:-----:|
| ASTRA FBP_CUDA [[1]](#note1) | dmpelt |       0.238 |       0.822 |        0.743 |       0.725 |       0.352 |  0.455|

## Fuel Cell data

The shown metrics are (see [here](https://tomochallenge.github.io/evaluation/) for more information):

* DW: Dice score of water.
* DC: Dice score of water in one channel.
* DL: Dice score of water in the gas diffusion layer region.
* DM: Dice score of water in the membrane region.
* HM: Harmonic mean of all other scores.

| Name                         | By     | DW | DC | DL | DM | HM  |
|:-----------------------------|:-------|:-----------:|:-----------:|:------------:|:-----------:|:-----------:|
|  |  |  |  |  |  |  |



## Notes

1. <a name="note1"></a> Uses ASTRA 1.8.3 [(link)](http://www.astra-toolbox.com/) 2D FBP_CUDA with the defaults options (i.e. Ram-Lak filter).

