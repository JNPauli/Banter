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
I installed the raw dataset from openneuro by using *datalad install https://github.com/OpenNeuroDatasets/ds001506.git*. The structure of this dataset has been started to be explored by using *pybids*.

## 8.11.2022
Things that I need to do this week:
Take a look at how many categories there are in the dataset.
Use *datalad get* to install anatomical file of subject one and the functional file of subject one (within session one and run one). Plot images of anatomical file for subject one and plot functional images from subject one in the first imagery run and session. 
Update notebook with step 3 of fMRI Data handling (Data modelling). 
Read about SVM.
Work through the following notebooks from the course website [1](https://peerherholz.github.io/Cog_Com_Neuro_ML_DL/introduction/notebooks/neuroscience/statistical_maps.html), [2](https://peerherholz.github.io/Cog_Com_Neuro_ML_DL/introduction/notebooks/neuroscience/statistical_analyses_MRI.html), [3](https://peerherholz.github.io/Cog_Com_Neuro_ML_DL/introduction/notebooks/neuroscience/statistical_analyses_MRI.html#performing-statistical-analyses-on-bids-dataset). 

## 13.11.2022
Updated the Bids_exploration notebook with more comments, structure and information (still in progress though!). *datalad get sub-01/ses-imagery01/func/sub-01_ses-imagery01_task-imagery_run-01_bold.json* and *datalad get sub-01/ses-imagery01/func/sub-01_ses-imagery01_task-imagery_run-01_events.tsv* did not work, but the *datalad get (/../../..).nii.gz* worked.  The exploration of the anatomical and functional brain images have been executed. The amount of categories in for the imagery session 01 is included. 
    Further exploration of .json .tsv files have *still* to be done.

I looked up the [scikit-learn algorithm cheatsheet](https://scikit-learn.org/stable/tutorial/machine_learning_map/index.html). It seems like the most useful model for my research project would be the support vector machine.
    Adding information about data modelling is still missing in the notebook; I am thinking about creating another one for this purpose.

## 14.11.2022
Next step would be to run a GLM analysis on the preprocessed data, so I have the input for my machine learning model. The input to my model is the brain activity during the imagery and natural stimuli trials and thus requires the GLM. However, I still do not have the preprocessed data, because there are current issues with the data transfer.

## 15.11.2022
Added information about how to execute the datalad commands. Created first draft of a plot categorie id over time. Added more notes and structure. Made explanations to why the mean_img of the fmri image should be taken.

## 16.11.2022
Added more info to event and .json file. Created a second draft of plotting the categories over time. Transformed some markdown files from **txt** to a, in my opinion, more nicer way by using boxes.

## 22.11.2022
I incorperated some feedback that I got from Peer Herholz in the issue that I created on Github. Mainly, I added some overview about the paradigm that was used in the study. I explained how the mental imagery experiment works. Also, I added more structure and tried to be more narrative and explain more things.

What I am still struggling with is to understand the metadata of the functional files. I do not completely understand what things like "echo timing", "slice timing" or "flip angle" mean.