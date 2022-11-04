# October 2022:

Things that happended so far in this project:
The overall workflow of the fMRIPrep protocol has been followed. 
Step 1 of the workflow was to validate the dataset regarding the BIDS principle. The dataset follows bids, i.e. is bids compliant. The bids version is 1.0.2.

Step 2 of the workflow was the data processing. A computing environment has been set up (find the environment in ('folder_undefined')). The MRIQC for all participants has been done and all images have been approved. The fMRIPrep pipelines have run succesfully.

Things that are missing for now:
Quality check of the functional data. Quality check of the processed data.

The model of interest performs by supervised learning. The input to the model is brain activity of the participants. Since this input will be decoded and thus categorized, the respective labels of the stimuli(mental imagery; natural stimuli) are needed.

# November 2022:

## 1.11.2022

One issue that I encountered was the lack of "human readable" labels for the stimuli. Each stimuli was paired with a numeric ID. Luckily, there is a [repository](https://github.com/mf1024/ImageNet-Datasets-Downloader/blob/master/classes_in_imagenet.csv) that containts the translation for each ID.
However, a license is missing. It is still in question whether I can actually use this repository. 

## 3/4.11.2022
I installed the raw dataset from openneuro by using *datalad*. The structure of this dataset has been started to be explored by using *pybids*.