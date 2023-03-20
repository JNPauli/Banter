# Documentation

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
I incorperated some feedback that I got from Peer Herholz in the issue that I created on Github. Mainly, I added some overview about the paradigm that was used in the study. I explained how the mental imagery experiment works. Also, I added more structure and tried to be more narrative and explain more things. I updated the README files of the data and code folder.

What I am still struggling with is to understand the metadata of the functional files. I do not completely understand what things like "echo timing", "slice timing" or "flip angle" mean.

## 26.11.2022
I decided that probably the best thing for my support vector machine would be to use the "one versus all" classifying approach. 
I created the General linear model notebook and loaded the data for sub-01/ses-imagery01/run01-run-05. I inspected the confounds.tsv file and started to create the structure for running the first level model.

## 28.11.2022
For subject one, ses and run one the first level model was created. I created the respective design matrix. 
Also, I updated the exploration notebook with an updated plot for categories over time.

## 29.11.2022
Created a new plot to show how the categories distribute over time.

# December 2022


## 01.12.2022
Prepared the calculation of contrasts for essentially detecting voxels with significant effects for a single run of subject one.
Computed effect and z map. Plotted the z map on the mean img.

## 02.12.2022
I tried the plotting methods with different conditions. For some reason, the displayed brain images do not change at all. I guess there must be something wrong with the way I computed the contrasts. I already created an issue for this. 
Also, I updated the exploration dataset with comments from the respective issue.

## 03.12.2022
According to the feedback I got in the issue, the way I computed the glm and everything associated with it in the notebook was correct. Thus, I proceeded and started to prepare the GLM for all 5 runs. Still figuring how I have to go about it.

## 04.12.2022
I calculated another z map. This time, I fitted the whole glm on 5 different fMRI images and their respective design matrices. Im still not sure which way is right one. In my first approach I calculated the contrast for a given condition, repeated this for all 5 runs, meaning I got 5 different zmaps of five different runs.

## 05.12.2022
I changed my approach and tried to follow the [nilearn documentation](https://nilearn.github.io/stable/auto_examples/04_glm_first_level/plot_fiac_analysis.html) and compute the design matrices for each run, without fitting the glm to get the matrices. Then I ran the glm, computed and saved the z-maps for each contrast. I am still unsure, wether this can now finally serve as the input to the SVM. I tried to plot the contrasts, but I need to specifiy which contrasts I want to plot. I am not sure, if I should plot all 26 contrasts.

Also, I need to create a figure that shows the stimuli over time for all 5 runs.

## 11.12.2022
I started by calculating R squared for the glm, to evaluate the model. However, I do not know yet how to properly interpreted the results. It seems like the results are in accordance to what I am expecting, but I need to figure some things out. For example which exact brain areas show increased R^2 and if those are according to literature.

I created a plot for each contrast across runs and started to compare them to the meta analysis database of neurosynth. This needs to be done to conclude, wether the activation pattern behaves according to theory.

## 12.12.2022
I finalized the evaluation of the R-Squared plots and discussed the results with Peer on the discord server. Furthermore, I compared the 26 contrast plots across runs to the results from neurosynth. They seem to show similar patterns, meaning that it is most likely now time to start with training the SVM.

## 20.12.2022
This week can be summed up pretty easy: I decided, that ROI based decoding makes the most sense for my supervised learning algorithm. This means, that I should look into the literature and decide which ROI makes the most sense. There are already masks provided in the openneuro dataset. The provided masks are the following (for the left and right hemisphere, respectively):
V1,V2,V3,V4,Higher Visual cortex, PPA, FFA, LOC.
I am diving into the literature to conclude which ROI will be the most useful for starters.
I probably will go with the visual areas, or even the LOC due to its significant role in [object detection](https://www.sciencedirect.com/science/article/pii/S0042698901000736).

# January 2023

## 02.01.2023
Things I need to do this week: Create 26 z-maps (so one z-map for each condition) across runs for all 4 sessions. So basically just repeat the steps I already did. 
Then I can train the SVM for example on 3 sessions and test them on 2 other sessions (= cross validation).

## 03.01.2023
I started with applying the glm analysis to the remaining 3 sessions. For this purpose, I created a loop that gets me a design matrix, which contains all 5 runs for each session. This design matrix was validated for session with the respective event file, meaning that the pattern of the stimuli behavior is the same for both the design matrix and the event file. I will still validate the other 2 sessions on another day. 

I probably just need to run the glm for all three sessions and create the contrasts for the three session, so I get the respective z-map time series.

## 04.01.2023
I continued with calculating the z-map time series. At first, I did this for session two alone. Then I had the idea, that I can just include the calculation in the main loop of section 5.0. I did this, and compared the results of 26 z-map contrasts for session 2. What I mean by this is that I checked if the plotted contrasts for session 2, when calculating the z-maps on its own, and when including it in a fancy loop are the same. They are indeed equal, meaning the loop I wrote is correct and works.

Also, I compared the voxel based activity pattern of all three z-maps to the one from session one. The pattern is very similiar meaning its also similiar to the pattern usually found in literature.

## 05.01.2023
I started with a new notebook for the SVM. Within this notebook I loaded the masks and tried to extract the time-series out of the z-maps. However, this did not work with nilearns "apply_mask()" function, because the "Mask affine is different from image affine". Currently looking for a solution to fix this.

## 06.01.2023
So I simply plotted the ROI on the z-map with the plot_roi() function. It seems like the mask objects do allign with the z-maps in a way that makes sense, meaning the visual cortex mask is plotted on the right spot for the z-map.

One problem is that for sub 02 and sub 03 the functional images are not in subject space. This could lead to allignment issues. The brainlife preprocessing is now happening again, but this time with the functional images in subject space.
When this is done I can run the glm for all subjects again and proceed with the SVM.

In the meanwhile I could try to run the SVM and try things out.

## 09.01.2023
The functional files have been reprocessed on brainlife. Now, all functional images are in the subject space, meaning in the respective anatomical T1 image. 
The z-maps have been recalculated and plotted. The pattern still makes sense in respect to theory. So next step now is to download the remaining subject files (02 and 03) and calculate the respective z-maps.

## 17.01.2023
Summary of the last week:
The functional files for sub-02 and -03 have been reprocessed and successfully downloaded. Unfortunately, Brainlife has issues with the backend server for now. This means, that I am not able to progress with the project by downloading the respective regressors.
They are working on a solution and will give notice, when the issues is fixed.

## 18.01.2023
Started to load the data into X and Y variables. Tried to implement logistic regression algorithm.

## 19.01.2023
There were some misunderstandings on my part about the X and Y variables. If I understood it correct, X needs to be n_samples * n_features large. N_samples is 104, since we have 26 categories a 4 sessions. N_features is equal to 992, since there are 992 for the mask applied (left hemisphere visual cortex). 
I now created an numpy array that has 104 rows and 992 columns. Each row represents the respective timeseries.

Also I calculated a correlation matrix that displays the most 100 highest correlation coefficients... Im not sure if I should keep it this way. But its a start.

I created the Y variable. It has 104 entries, aka 26*4. Each category is classified with a number. First category = 1 and so on.

When running the logistic regression algorithm, it returns a model prediction of 0. Something is wrong. Maybe the features are to highly correlated? Not enough samples?

## 20.01.2023
Been trying to figure out why the model performs so poorly. Mainly by inspecting the correlation between features.
Well it is going rather... unsuccesfull. Today I just tried out a lot of different things, but I am not really smarter

## 23.01.2023
Investigated the different voxel patterns and compared them with respective z_maps. There is a session specific correlation, but I still do not know why. Maybe it is what it is...

I also tried different values for the C-Hyperparameter. For now, the model is working very well (accuracy 100%) for the training. However, the test data still performs very poor. This was inspected by creating a confusion matrix. Probably the model is pretty overfitted.

I extracted the most important features from the coef_ function of the logistic regression model. Still, the training performance is very bad.

Also I added a bit more structure to the notebook. The notebook was moved from /data to /code.

## 24.01.2023
Mapping onto brain

datasplit, one class member in 25% split.

explain session-specifics. first 3 components = session specific variance.

Plot PCA (session specific correlation hypothesis). If so, remove PCA components that account for session differences. Reconstruction.

PCA with sklearn, then "manually reconstruct". (inverse transform, check source code.)
https://github.com/scikit-learn/scikit-learn/blob/ff1023fda/sklearn/decomposition/_base.py#L128

## 30.01.2023
In the last week I did a lot of error search. It is evident, that the high session correlations affect the data. Almost al of the variance gets explained by it. A PCA reveals, that there are session cluster. We are not interest in session clusters, but in category cluster. 

I tried a bunch of different things:
Feature selection, with sklearns kbest. Hyperparamter selection with sklearns GridSearch. Instead of automatically splitting Y into training and test, I did this with a loop. The idea came, because when inspecting the confusion matrices, not every class was represented in the test set. Thus the loop comes in handy. It randomly selects a element from one of the sessions. This is done randomly, to defy the session specific effects.

Since nothing really helped, I'll continue with the SupportVectorMachine.

# February 2023

## 02.02.2023

I applied the SVM algorithm to the dataset. Similiar to the Logistic Regression, the performance was very poor. Sklearns GridSearch and feature selection did not help at all. So probably there is something wrong with the data.

I now downloaded the data from subject 2 and will apply the glm analysis and proceed with the Logistic Regression and SVM pipeline.

This turned out to not work. Meaning the model performance remains very poor. Very similiar to subject one, there is a very session specific pattern that can be observed in the z-maps, a correlation plot and in the PCA.
So regardless of the model and the subject, the performance is poor. 

Maybe I need to adjust the glm parameters. I provided the mask in the glm, but I am uncertain wether this is the way to go.


## 11.02.2023

Recap of last week:
We decided that the issue most likely is due to the data obtained. The very specific correlation pattern makes it impossible to actually decode anything (besides the session labels). I still want to learn as much as possible,thus I decided to continue with setting up a fully connected neuronal network. I did this with pytorch.

Pytorch comes with several modules that are very helpful when setting up an NN. Also I am working through the [computational neuroscience](https://compneuro.neuromatch.io/tutorials/intro.html) and [DeepLearning](https://deeplearning.neuromatch.io/tutorials/intro.html) course from neuromatch. The course really helped me coding the NN.

So far I coded a very simple architecture (one hidden layer, ReLu Function) and applied different learning rates, width of the hidden layer and epoch sizes. Similar to the SVM and LR, the training set works quite nice, but testing it is really bad. Since I am not that experienced with coding neural networks, this can be due to an non proper working code. A code review will definitely happen. The whole process is happening in the [Neural_network](https://github.com/JNPauli/Mental-image-decoding/blob/update/code/Neural_network.ipynb) notebook within the code folder of the Github repository.

## 12.02.2023

I adapted the labels a bit and applied the "randomization loop", so each label is represented in the test set. This lead to an very interesting results: I perfectly(!) replicated the following accuracy: 0.038461538461538464
This accuracy has also been reached in the SVM and LR. Very interesting. Something is wrong but I do not know what.

Also, I tried the DNN with the z-maps per run, and not across runs. Results are similiar. However, I had to adapt epochs and amount of neurons in the hidden layer. I might add several layers. I am unsure, if I should add an activation function at every layer though.

## 13.02.2023

Added a dropout layer, this did not change anything though.

## 14.02.2023

Validated the pipelines I set up with the haxby dataset. It worked fine for the SVM and the NN, meaning it leads to decent accuracies for both training and testing data. So atleast the pipelines are okay.

Things I need to do:

Leave the fourth session out for testing purposes. So manually split the data again, but this time not random session in the test data but explicitly the fourth one. This way the algorithm never sees data from session 4... we'll see!

Also: Adapat hidden layers -> Add one more layer and add useful amount of neurons. Furthermore, try the NN with Keras, see the workshop from Peer on [Brain decoding and encoding](https://main-educational.github.io/brain_encoding_decoding/mlp_decoding.html).

Also: Maybe not use the most likely category predicted, but rather the top 3 or 5 ones.
Plot the accuracy per epoch.

## 15.02.2023

I set up the cross validation pipeline in the logistic regression notebook. Here I defined the [LeaveOneGroupOut](https://scikit-learn.org/stable/modules/generated/sklearn.model_selection.LeaveOneGroupOut.html) method. This way, in training, the LogisticRegression is trained with session 1 and 2 and validated on 3. However, the split it selfs works, but Im not sure it really does work when using the crossvalidation function. This needs to be further investigated.

# March 2023

## 01.03.2023

Nothing new happened. The hypothesis to decode mental imagery does not seem to work. This means that I will now stop the machine learning and start to get the assignment ready.

## 20.03.2023

The past weeks I spend almost all of the time on setting up the jupyter book. It seems to be almost finished now! Hurray!