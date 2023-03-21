# Discussion

`Reminder`: The hypothesis we tested in the machine learning section was:

"A machine learning classifier can predict a mental imagery given the respective voxel pattern with an accuracy atleast above chance."

The hypothesis was examined with a supervised learning algorithm, expressed in a logistic regression, a SVM and a fully connected neural network. The results make it quite clear, that we must reject our hypothesis. For this given implementation of the hypothesis, it was in fact not possible to predict mental imagery with an accuracy above chance. The model was heavily overfitted and could not predict anything at all in the test set. Feature selection, increasing the sample size, adjusting the hyperparameters and other tricks were not useful at all.

The correlation plot and the PCA made the underlying problem quite clear. There is a very high correlation between each respective session. Each session correlates almost perfectly with itself. The correlation between other sessions? Not so much. A PCA showed us, that almost all of the variance in the data is explained by the sessions. In order to accept the hypothesis, the variance should have been mostly explained by the 26 categories and not the four sessions.

Shen et al. (2019) tackled the decoding problem, with the same dataset, by selecting the most important voxels with a sparse linear regression. For a detailed description, please take a look at the [paper](Shen, G., Horikawa, T., Majima, K., & Kamitani, Y. (2019). Deep image reconstruction from human brain activity. PLOS Computational Biology, 15(1), e1006633. https://doi.org/10.1371/journal.pcbi.1006633) and examine the section "DNN feature decoding analysis".

An opportunity to get improved results would be in adapting the general linear model. Nilearns first level model comes with a lot of parameters to adapt and tune. Possibly, there is a very specific session drift or noise that influences the voxel pattern so much, that a learning algorithm becomes "blind" to any data that belongs to an external session. One could also change the HRF model of the glm. 

Other than that, the training set provided accuracies around 100% (atleast for the Logistic Regression and the Neural Network). Most likely a lot of noise was modelled and thus we ended up with 100% accuracy on the training- and 0% on the test set, i.e. the model overfitted.
Interestingly enough, when trying to solely decode the sessions, reasonable accuracies in the training and test set were obtained, further reinforcing the assumption of high session specific variance.

Also one could try to train the algorithm with perceptual data. As described before, the fMRI data of the perceptual sessions, so when the subjects actually looked at the images, is stored in the dataset. So you could train the algorithm with the perceptual data and test it on the imagery data. The categories are the same for both, so this would have been possible, in theory.

# Reflection of the research process
This research project was definitely an intense one. I came in to the course with two semesters worth of matlab and one semester worth of python and was introduced to something way way bigger than that.
Not only did this project force me to step up my python game `tremendously`, it required me to surround myself with information that I did not encounter at all in my studies before.
Having the opportunity to learn about artifical intelligence is one thing, but really diving into the science, both math and information system wise, is something different. 
It took some time to understand the basics in general and I felt that everytime I understood something, the next obstacle was waiting around the corner. Fortunately enough, I was provided with `great` lecturers and a great (double exclamation mark !!) [resource](https://peerherholz.github.io/Cog_Com_Neuro_ML_DL/) from Peer Herholz.

All the way through this project I felt excited to learn new things. This was further reinforced by the practical side of the research internship, aka the project and everything you saw in this jupyter book.
Dealing with fMRI data in a very very exciting research project was something else. All the way from preprocessing the data to finally doing *something* with it was just awesome. Setting up the glm was really intense for me. Not only getting comfortable with nilearns functionality, but also setting up the code in a smooth way challenged me a lot, but in a good way. Often times I experienced frustration, because you must consider so many things when simply setting up the glm. But after each frustration I became more motivated to get stuff done, to create this fancy loops for the z-maps, to compare results with neurosynth, to set up design matrices and compare them smoothly with the event files, or event to nicely set up this contrast dictionary!

This was fun and the cherry on top was the machine learning bit. Finally I was able to convert my theoretical knowledge into something practical. This was also very challenging to me, but very rewarding. 
Unfortunately my results were really not that great. Test accuracies around ~0% are just awful and made me wonder, if I did something fundamentally wrong. Several examinations from the lectures made me believe, that there is something else wrong with the data and not the way I implemented it, which was nice. I also evaluated my pipelines with the very famous [dataset](https://nilearn.github.io/dev/modules/generated/nilearn.datasets.fetch_haxby.html) from [Haxby(2001)](https://pubmed.ncbi.nlm.nih.gov/11577229/). Reasonable accuracies validated that my pipelines were working correctly, and the unsatisfiying results can not be attributed to poor programming skills.

This research internship made it possible to set up fMRI data in a glm pipeline and run those statistical z-maps through different decoding pipelines. Even though the results of my hypothesis were...yeah, not that great, I learned `a lot`, from setting up a Github repository to building a Deep Neural Network in pytorch. I put a lot of hours in to this project and have been rewarded greatly. This internship challenged me differently and I must evaluate the process it self very positive. I am greatful for having learned so much in the past year and cannot wait to improve my abilities more in the next project.

# Ending

<iframe src="https://giphy.com/embed/3EvqXUZbb8iui6AXT7" width="480" height="270" frameBorder="0" class="giphy-embed" allowFullScreen></iframe><p><a href="https://giphy.com/gifs/theblock-channel-9-block-the-2022-3EvqXUZbb8iui6AXT7">via GIPHY</a></p>

If you have made it this far, thanks a lot for thoroughly examing the research I conducted in the past 12 months. If you stumbled here by accident, thank you anyway!

This research report is now officially coming to an end.

If you have anything else to add, please open an issue or <details>
<summary> contact me via e-mail:</summary>
<br>(paulijanos@gmail.com) </details>

I am happy to discuss anything with you!

## References

 Haxby, J. V., Gobbini, M. I., Furey, M. L., Ishai, A., Schouten, J. L., & Pietrini, P. (2001). Distributed and overlapping representations of faces and objects in ventral temporal cortex. Science (New York, N.Y.), 293(5539), 2425–2430. https://doi.org/10.1126/science.1063736 

Shen, G., Horikawa, T., Majima, K., & Kamitani, Y. (2019). Deep image reconstruction from human brain activity. PLOS Computational Biology, 15(1), e1006633. https://doi.org/10.1371/journal.pcbi.1006633