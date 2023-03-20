# Discussion

Reminder: The hypothesis we tested in the machine learning section was, if "A machine learning classifier can predict a mental imagery given the respective voxel pattern with an accuracy atleast above chance."

The hypothesis was examined with an supervised learning algorithm, expressed in an logistic regression, a SVM and a fully connected neural network. The results make it quite clear, that we must reject our hypothesis. For this given implementation of the hypothesis, it was in fact not possible to predict mental imagery with an accuracy above chance. The model was heavily overfitted and could not predict anything at all in the test set. Feature selection, increasing the sample size, adjusting the hyperparameters and other tricks were not useful at all.

The correlation plot and the PCA made the underlying problem quite clear. There is a very high correlation between each respective session. Each session correlates almost perfectly with itself. The correlation between other sessions? Not so much. A PCA showed us, that almost all of the variance in the data is explained by the sessions. In order to accept the hypothesis, we  the variance shpuld have been explained by the 26 categories and not the four sessions.

Shen et al. (2019) tackled the decoding problem, with the same dataset, by selecting the most important voxels with a sparse linear regression. For a detailed description, please take a look at the paper and examine the section "DNN feature decoding analysis".

An opportunity to get successfull (=accuracies above chance) results would be in adapting the general linear model. Nilearns first level model come with a lot of parameters to adapt and to tune. Possibly, there is an very specific session drift or noise that influences the voxel pattern so much, that a learning algorithm becomes "blind" to any data that belongs to an external session. One could also change the HRF model. 

Other than that, the training set provided accuracies around 100%. Most likely a lot of noise was modelled and thus the 100% accuracies are reasonable.
Interestingly enough, when trying to solely decode the sessions, reasonable accuracies in the training and test set were obtained, further reinforcing the assumption of high session specific variance.

Also one could try to train the algorithm with perceptual data. As described before, the fMRI data of the perceptual sessions, so when the subjects actually looked at the images, is stored in the dataset. So you could train the algorithm with the perceptual data and test it on the imagery data. The categories are the same for both, so this would have been possible, in theory.

# Reflection of the research process

This research project was definitely an intense one. I came in with two semesters worth of matlab and one semester worth of python and was introduced to something way way bigger than that.
Not only did this project force me to step up my python game a `whole lot`, it required me to surround myself with information that I did not encounter at all in my studies before.
Having the opportunity to learn about artifical intelligence is one thing, but really diving into the science, both math and information system wise, thats something different. 
It took some time to understand the basics in general and I felt that everytime I understood something, the next obstacle was around the corner. Fortunately I enough, I was not only provided with `great` lectures and a great (double exclamation mark !!) [resource](https://peerherholz.github.io/Cog_Com_Neuro_ML_DL/) by Peer Herholz.

All the way through this project I felt excited to learn new things. This was further reinforced by the practical side of the research internship, aka the project and everything you saw in this jupyter book.
Dealing with fMRI data in a very very exciting research project was something else. All the way from preprocessing the data to finally doing *something* with it was just awesome. Setting up the glm was really intense for me. Not only getting comfortable with nilearns functionality, but also setting up the code in a smooth way challenged me a lot, but in a very good way. Often times I thought 