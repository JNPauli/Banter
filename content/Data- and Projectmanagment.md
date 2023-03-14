# Data- and Projectmanagment
This file containts the description of the Data- and Projectmanagment. In other words, the **Dataset** is described and evaluated, also the question regarding **Version control** are answered, the **literature library** and the **FAIR** principle is adressed. Furthermore, comments about the **open lab notebook** and the **computational environment** are made. So lets start right away.

## Dataset description and evaluation
As already mentioned in the *Research question* section, the [Dataset](https://openneuro.org/datasets/ds001506/versions/1.3.1) can be obtained from openneuro. [Openneuro](https://openneuro.org/) is a open-source website that hosts multiple datasets from different modalities. In our case, the Dataset is from an fMRI experiment. Since the data is not preprocessed, it needs to be downloaded from brainlife. Brainlife is a cloud computing platform, that makes it possible to store share and analyse Data. The preprocessed brainlife dataset can be found [here](https://brainlife.io/project/638b2a566881d56fbfac223e). Brainlife has specifically been used to preprocess the fMRI data in the *subject anatomical space* for the imagery sessions of all three subjects. Further descriptions follow in the Dataset Exploration part. 
**NOTE:** It is actually possible to store preprocessed Data on openneuron as well. It would have been better, if the dataset would have been preprocessed already. This way its easier to comprehend every step that has been made in the analysis. Regarding the analysis of the paper: The authors also uploaded their code on [Github](https://github.com/KamitaniLab/DeepImageReconstruction).

The dataset follows the BIDS format and contains the data from three healthy subjects. For each subject there is fMRI data from five different experiment tasks and multiple sessions. In our case, only the fMRI data of the **imagery** sessions are used. The structure of the imagery sessions looked like this: 
Subject one - Session imagery 01, 02, 03 and 04. 5 runs per session, so 20 runs in total.
Subject two - Session imagery 01, 02 and 03. Session one had 8 runs, session two and three 6 runs. So also 20 runs in total.
Subject three - Session imagery 01, 02 and 03. Session one had 3 runs, session two 9 and session three 8 runs. Leading to further 20 runs in total.

Every run consisted of the 25 images shown (for further details, please see the Dataset Exploration part). Each imagery period lasted for 4 seconds. This means, that per stimuli only 4 seconds of fMRI activity was recorded per run. This also means, that only 80 seconds of fMRI activity per stimuli is recorded per subject. This is not a lot of data to beginn with. Implications of this issue are discussed in the... Discussion part.
The stimuli images were obtained from Imagenet. So called natural images were explicitly used for the imagery sessions.



