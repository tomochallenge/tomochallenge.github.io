---
layout: page
title: Submit
permalink: submit/
include_in_menu: true
---

## Foam phantoms

To submit results for the challenges of the foam phantoms, please use the `prepare_submission` function of the `foam_phantom_utils.py` script that can be found [here](https://github.com/tomochallenge/tomochallenge_utils). In the function, please use the following as arguments:

* `vol`: numpy array of size 1080x1280x1280 voxels. Values larger than 0.5 will be segmented as 'foam material', with all other values segmented as 'air'.
* `filename`: output filename. Please use a descriptive filename.
* `description`: a description of the submission in a text string. Please include (at least) the following:
    1. which challenge the submission is for.
    2. a short name for the submission (about 10 characters).
    3. a short name for the submitting person or group (about 10 characters).
    4. a longer explanation of the approach used to obtain the submitted results. References can also be included.

Please see [here](https://tomochallenge.github.io/results/) what information previous submissions have provided. If you have previously submitted results for the same challenge with the same short name, the results will be updated in the table. Please indicate what was changed compared with the previous submission(s).

## Operando Fuel Cell data

To submit results for the challenge of the operando fuel cell, please use the prepare_submission function of the fuel_cell_utils.py script that can be found here. In the function, please use the following arguments:

•	vol: numpy array of size 1440x1440x1100 (full volume) or 1440x1440x600 (vertically cropped volume) voxels.  
•	filename: output filename. Please use a descriptive filename.  
•	description: a description of the submission in a text string. Please include (at least) the following:  
    o	a short name for the submission (about 10 characters)  
    o	a short name for the submitting person or group (about 10 characters)  
    o	a longer explanation of the approach used to obtain the submitted results. References can also be included.   

