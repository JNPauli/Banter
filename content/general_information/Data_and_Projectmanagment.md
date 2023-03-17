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

## Version control
The whole project is documented on Github. Please click [here](https://github.com/JNPauli/Mental-image-decoding) to get to the Github repository. **Note**: Most of the commits happened on the update branch, so that the main branch is not trashed with random stuff and ideas. The README file of the Github repository explains the respective structure and what contents are documented in which folder. Also, the project is documented on [OSF](https://osf.io/t2psq/).

## Literature
The literature resources used in this jupyter book and the project in general are all documented with the opensource literature software [zotero](zotero.org). To see which literature contributed to creating this project you can either follow the link to the OSF project, or<details>
<summary> click here:</summary>
<br>
@misc{noauthor_mind-vis_nodate,
	title = {{MinD}-{Vis}},
	url = {https://mind-vis.github.io/},
	urldate = {2023-03-13},
}

@article{galton_istatistics_1880,
	title = {I.—{STATISTICS} {OF} {MENTAL} {IMAGERY}},
	volume = {os-V},
	issn = {0026-4423},
	url = {https://doi.org/10.1093/mind/os-V.19.301},
	doi = {10.1093/mind/os-V.19.301},
	number = {19},
	urldate = {2023-03-13},
	journal = {Mind},
	author = {GALTON, FRANCIS},
	month = jul,
	year = {1880},
	pages = {301--318},
}

@article{zeman_lives_2015,
	title = {Lives without imagery – {Congenital} aphantasia},
	volume = {73},
	issn = {0010-9452},
	url = {https://www.sciencedirect.com/science/article/pii/S0010945215001781},
	doi = {10.1016/j.cortex.2015.05.019},
	language = {en},
	urldate = {2023-03-13},
	journal = {Cortex},
	author = {Zeman, Adam and Dewar, Michaela and Della Sala, Sergio},
	month = dec,
	year = {2015},
	pages = {378--380},
}

@article{horikawa_neural_2013,
	title = {Neural {Decoding} of {Visual} {Imagery} {During} {Sleep}},
	volume = {340},
	url = {https://www.science.org/doi/full/10.1126/science.1234330},
	doi = {10.1126/science.1234330},
	abstract = {Visual imagery during sleep has long been a topic of persistent speculation, but its private nature has hampered objective analysis. Here we present a neural decoding approach in which machine-learning models predict the contents of visual imagery during the sleep-onset period, given measured brain activity, by discovering links between human functional magnetic resonance imaging patterns and verbal reports with the assistance of lexical and image databases. Decoding models trained on stimulus-induced brain activity in visual cortical areas showed accurate classification, detection, and identification of contents. Our findings demonstrate that specific visual experience during sleep is represented by brain activity patterns shared by stimulus perception, providing a means to uncover subjective contents of dreaming using objective neural measurement.},
	number = {6132},
	urldate = {2023-03-13},
	journal = {Science},
	author = {Horikawa, T. and Tamaki, M. and Miyawaki, Y. and Kamitani, Y.},
	month = may,
	year = {2013},
	pages = {639--642},
}

@article{reddy_reading_2010,
	title = {Reading the mind's eye: {Decoding} category information during mental imagery},
	volume = {50},
	issn = {1053-8119},
	shorttitle = {Reading the mind's eye},
	url = {https://www.sciencedirect.com/science/article/pii/S1053811909012701},
	doi = {10.1016/j.neuroimage.2009.11.084},
	abstract = {Category information for visually presented objects can be read out from multi-voxel patterns of fMRI activity in ventral–temporal cortex. What is the nature and reliability of these patterns in the absence of any bottom–up visual input, for example, during visual imagery? Here, we first ask how well category information can be decoded for imagined objects and then compare the representations evoked during imagery and actual viewing. In an fMRI study, four object categories (food, tools, faces, buildings) were either visually presented to subjects, or imagined by them. Using pattern classification techniques, we could reliably decode category information (including for non-special categories, i.e., food and tools) from ventral–temporal cortex in both conditions, but only during actual viewing from retinotopic areas. Interestingly, in temporal cortex when the classifier was trained on the viewed condition and tested on the imagery condition, or vice versa, classification performance was comparable to within the imagery condition. The above results held even when we did not use information in the specialized category-selective areas. Thus, the patterns of representation during imagery and actual viewing are in fact surprisingly similar to each other. Consistent with this observation, the maps of “diagnostic voxels” (i.e., the classifier weights) for the perception and imagery classifiers were more similar in ventral–temporal cortex than in retinotopic cortex. These results suggest that in the absence of any bottom–up input, cortical back projections can selectively re-activate specific patterns of neural activity.},
	language = {en},
	number = {2},
	urldate = {2023-03-13},
	journal = {NeuroImage},
	author = {Reddy, Leila and Tsuchiya, Naotsugu and Serre, Thomas},
	month = apr,
	year = {2010},
	keywords = {Imagery, Multi-voxel pattern analysis, Object recognition, Occipito-temporal cortex, Perception, fMRI},
	pages = {818--825},
}

@article{naselaris_encoding_2011,
	series = {Multivariate {Decoding} and {Brain} {Reading}},
	title = {Encoding and decoding in {fMRI}},
	volume = {56},
	issn = {1053-8119},
	url = {https://www.sciencedirect.com/science/article/pii/S1053811910010657},
	doi = {10.1016/j.neuroimage.2010.07.073},
	abstract = {Over the past decade fMRI researchers have developed increasingly sensitive techniques for analyzing the information represented in BOLD activity. The most popular of these techniques is linear classification, a simple technique for decoding information about experimental stimuli or tasks from patterns of activity across an array of voxels. A more recent development is the voxel-based encoding model, which describes the information about the stimulus or task that is represented in the activity of single voxels. Encoding and decoding are complementary operations: encoding uses stimuli to predict activity while decoding uses activity to predict information about the stimuli. However, in practice these two operations are often confused, and their respective strengths and weaknesses have not been made clear. Here we use the concept of a linearizing feature space to clarify the relationship between encoding and decoding. We show that encoding and decoding operations can both be used to investigate some of the most common questions about how information is represented in the brain. However, focusing on encoding models offers two important advantages over decoding. First, an encoding model can in principle provide a complete functional description of a region of interest, while a decoding model can provide only a partial description. Second, while it is straightforward to derive an optimal decoding model from an encoding model it is much more difficult to derive an encoding model from a decoding model. We propose a systematic modeling approach that begins by estimating an encoding model for every voxel in a scan and ends by using the estimated encoding models to perform decoding.},
	language = {en},
	number = {2},
	urldate = {2023-03-13},
	journal = {NeuroImage},
	author = {Naselaris, Thomas and Kay, Kendrick N. and Nishimoto, Shinji and Gallant, Jack L.},
	month = may,
	year = {2011},
	keywords = {Computational neuroscience, Decoding, Encoding, Linear classifier, Multi-voxel pattern analysis, fMRI},
	pages = {400--410},
}

@article{gaonkar_interpreting_2015,
	title = {Interpreting support vector machine models for multivariate group wise analysis in neuroimaging},
	volume = {24},
	issn = {1361-8415},
	url = {https://www.sciencedirect.com/science/article/pii/S136184151500095X},
	doi = {10.1016/j.media.2015.06.008},
	abstract = {Machine learning based classification algorithms like support vector machines (SVMs) have shown great promise for turning a high dimensional neuroimaging data into clinically useful decision criteria. However, tracing imaging based patterns that contribute significantly to classifier decisions remains an open problem. This is an issue of critical importance in imaging studies seeking to determine which anatomical or physiological imaging features contribute to the classifier’s decision, thereby allowing users to critically evaluate the findings of such machine learning methods and to understand disease mechanisms. The majority of published work addresses the question of statistical inference for support vector classification using permutation tests based on SVM weight vectors. Such permutation testing ignores the SVM margin, which is critical in SVM theory. In this work we emphasize the use of a statistic that explicitly accounts for the SVM margin and show that the null distributions associated with this statistic are asymptotically normal. Further, our experiments show that this statistic is a lot less conservative as compared to weight based permutation tests and yet specific enough to tease out multivariate patterns in the data. Thus, we can better understand the multivariate patterns that the SVM uses for neuroimaging based classification.},
	language = {en},
	number = {1},
	urldate = {2022-11-17},
	journal = {Medical Image Analysis},
	author = {Gaonkar, Bilwaj and T. Shinohara, Russell and Davatzikos, Christos},
	month = aug,
	year = {2015},
	keywords = {Analytic approximation, Permutation tests, SVM},
	pages = {190--204},
}

@misc{chen_seeing_2022,
	title = {Seeing {Beyond} the {Brain}: {Conditional} {Diffusion} {Model} with {Sparse} {Masked} {Modeling} for {Vision} {Decoding}},
	shorttitle = {Seeing {Beyond} the {Brain}},
	url = {http://arxiv.org/abs/2211.06956},
	doi = {10.48550/arXiv.2211.06956},
	abstract = {Decoding visual stimuli from brain recordings aims to deepen our understanding of the human visual system and build a solid foundation for bridging human and computer vision through the Brain-Computer Interface. However, reconstructing high-quality images with correct semantics from brain recordings is a challenging problem due to the complex underlying representations of brain signals and the scarcity of data annotations. In this work, we present MinD-Vis: Sparse Masked Brain Modeling with Double-Conditioned Latent Diffusion Model for Human Vision Decoding. Firstly, we learn an effective self-supervised representation of fMRI data using mask modeling in a large latent space inspired by the sparse coding of information in the primary visual cortex. Then by augmenting a latent diffusion model with double-conditioning, we show that MinD-Vis can reconstruct highly plausible images with semantically matching details from brain recordings using very few paired annotations. We benchmarked our model qualitatively and quantitatively; the experimental results indicate that our method outperformed state-of-the-art in both semantic mapping (100-way semantic classification) and generation quality (FID) by 66\% and 41\% respectively. An exhaustive ablation study was also conducted to analyze our framework.},
	urldate = {2022-11-17},
	publisher = {arXiv},
	author = {Chen, Zijiao and Qing, Jiaxin and Xiang, Tiange and Yue, Wan Lin and Zhou, Juan Helen},
	month = nov,
	year = {2022},
	note = {arXiv:2211.06956 [cs]},
	keywords = {ACM-class: I.4, I.5, J.3, Computer Science - Computer Vision and Pattern Recognition},
}

@incollection{suthaharan_support_2016,
	address = {Boston, MA},
	series = {Integrated {Series} in {Information} {Systems}},
	title = {Support {Vector} {Machine}},
	isbn = {9781489976413},
	url = {https://doi.org/10.1007/978-1-4899-7641-3_9},
	abstract = {Support Vector Machine is one of the classical machine learning techniques that can still help solve big data classification problems. Especially, it can help the multidomain applications in a big data environment. However, the support vector machine is mathematically complex and computationally expensive. The main objective of this chapter is to simplify this approach using process diagrams and data flow diagrams to help readers understand theory and implement it successfully. To achieve this objective, the chapter is divided into three parts: (1) modeling of a linear support vector machine; (2) modeling of a nonlinear support vector machine; and (3) Lagrangian support vector machine algorithm and its implementations. The Lagrangian support vector machine with simple examples is also implemented using the R programming platform on Hadoop and non-Hadoop systems.},
	language = {en},
	urldate = {2022-11-13},
	booktitle = {Machine {Learning} {Models} and {Algorithms} for {Big} {Data} {Classification}: {Thinking} with {Examples} for {Effective} {Learning}},
	publisher = {Springer US},
	author = {Suthaharan, Shan},
	editor = {Suthaharan, Shan},
	year = {2016},
	doi = {10.1007/978-1-4899-7641-3_9},
	keywords = {Data Domain, Feature Space, Linear Support Vector Machine, Support Vector Machine, Support Vector Machine Classifier},
	pages = {207--235},
}

@misc{coleman_tensorflow_2022,
	title = {Tensorflow {Image} {Classification}},
	url = {https://github.com/rdcolema/tensorflow-image-classification/blob/1b1dca733f8b79a62fe87357dc537b294ded3538/tf2_cnn.ipynb},
	abstract = {CNN for multi-class image recognition in tensorflow},
	urldate = {2022-11-04},
	author = {Coleman, Robert},
	month = nov,
	year = {2022},
	note = {original-date: 2016-11-29T19:57:09Z},
}

@misc{noauthor_multi-domain_nodate,
	title = {Multi-domain translation between single-cell imaging and sequencing data using autoencoders {\textbar} {Nature} {Communications}},
	url = {https://www.nature.com/articles/s41467-020-20249-2},
	urldate = {2022-11-01},
}

@article{horikawa_generic_2017,
	title = {Generic decoding of seen and imagined objects using hierarchical visual features},
	volume = {8},
	copyright = {2017 The Author(s)},
	issn = {2041-1723},
	url = {https://www.nature.com/articles/ncomms15037},
	doi = {10.1038/ncomms15037},
	abstract = {Object recognition is a key function in both human and machine vision. While brain decoding of seen and imagined objects has been achieved, the prediction is limited to training examples. We present a decoding approach for arbitrary objects using the machine vision principle that an object category is represented by a set of features rendered invariant through hierarchical processing. We show that visual features, including those derived from a deep convolutional neural network, can be predicted from fMRI patterns, and that greater accuracy is achieved for low-/high-level features with lower-/higher-level visual areas, respectively. Predicted features are used to identify seen/imagined object categories (extending beyond decoder training) from a set of computed features for numerous object images. Furthermore, decoding of imagined objects reveals progressive recruitment of higher-to-lower visual representations. Our results demonstrate a homology between human and machine vision and its utility for brain-based information retrieval.},
	language = {en},
	number = {1},
	urldate = {2022-07-19},
	journal = {Nature Communications},
	author = {Horikawa, Tomoyasu and Kamitani, Yukiyasu},
	month = may,
	year = {2017},
	keywords = {Neural decoding, Object vision},
	pages = {15037},
}

@article{horikawa_neural_2013-1,
	title = {Neural {Decoding} of {Visual} {Imagery} {During} {Sleep}},
	volume = {340},
	url = {https://www.science.org/doi/10.1126/science.1234330},
	doi = {10.1126/science.1234330},
	number = {6132},
	urldate = {2022-07-17},
	journal = {Science},
	author = {Horikawa, T. and Tamaki, M. and Miyawaki, Y. and Kamitani, Y.},
	month = may,
	year = {2013},
	pages = {639--642},
}

@article{naselaris_encoding_2011-1,
	title = {Encoding and decoding in {fMRI}},
	volume = {56},
	issn = {1053-8119},
	url = {https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3037423/},
	doi = {10.1016/j.neuroimage.2010.07.073},
	abstract = {Over the past decade fMRI researchers have developed increasingly sensitive techniques for analyzing the information represented in BOLD activity. The most popular of these techniques is linear classification, a simple technique for decoding information about experimental stimuli or tasks from patterns of activity across an array of voxels. A more recent development is the voxel-based encoding model, which describes the information about the stimulus or task that is represented in the activity of single voxels. Encoding and decoding are complementary operations: encoding uses stimuli to predict activity while decoding uses activity to predict information about stimuli. However, in practice these two operations are often confused, and their respective strengths and weaknesses have not been made clear. Here we use the concept of a linearizing feature space to clarify the relationship between encoding and decoding. We show that encoding and decoding operations can both be used to investigate some of the most common questions about how information is represented in the brain. However, focusing on encoding models offers two important advantages over decoding. First, an encoding model can in principle provide a complete functional description of a region of interest, while a decoding model can provide only a partial description. Second, while it is straightforward to derive an optimal decoding model from an encoding model it is much more difficult to derive an encoding model from a decoding model. We propose a systematic modeling approach that begins by estimating an encoding model for every voxel in a scan and ends by using the estimated encoding models to perform decoding.},
	number = {2},
	urldate = {2022-07-17},
	journal = {NeuroImage},
	author = {Naselaris, Thomas and Kay, Kendrick N. and Nishimoto, Shinji and Gallant, Jack L.},
	month = may,
	year = {2011},
	pmid = {20691790},
	pmcid = {PMC3037423},
	pages = {400--410},
}

@article{gorgolewski_bids_2017,
	title = {{BIDS} apps: {Improving} ease of use, accessibility, and reproducibility of neuroimaging data analysis methods},
	volume = {13},
	issn = {1553-7358},
	shorttitle = {{BIDS} apps},
	url = {https://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1005209},
	doi = {10.1371/journal.pcbi.1005209},
	abstract = {The rate of progress in human neurosciences is limited by the inability to easily apply a wide range of analysis methods to the plethora of different datasets acquired in labs around the world. In this work, we introduce a framework for creating, testing, versioning and archiving portable applications for analyzing neuroimaging data organized and described in compliance with the Brain Imaging Data Structure (BIDS). The portability of these applications (BIDS Apps) is achieved by using container technologies that encapsulate all binary and other dependencies in one convenient package. BIDS Apps run on all three major operating systems with no need for complex setup and configuration and thanks to the comprehensiveness of the BIDS standard they require little manual user input. Previous containerized data processing solutions were limited to single user environments and not compatible with most multi-tenant High Performance Computing systems. BIDS Apps overcome this limitation by taking advantage of the Singularity container technology. As a proof of concept, this work is accompanied by 22 ready to use BIDS Apps, packaging a diverse set of commonly used neuroimaging algorithms.},
	language = {en},
	number = {3},
	urldate = {2022-06-09},
	journal = {PLOS Computational Biology},
	author = {Gorgolewski, Krzysztof J. and Alfaro-Almagro, Fidel and Auer, Tibor and Bellec, Pierre and Capotă, Mihai and Chakravarty, M. Mallar and Churchill, Nathan W. and Cohen, Alexander Li and Craddock, R. Cameron and Devenyi, Gabriel A. and Eklund, Anders and Esteban, Oscar and Flandin, Guillaume and Ghosh, Satrajit S. and Guntupalli, J. Swaroop and Jenkinson, Mark and Keshavan, Anisha and Kiar, Gregory and Liem, Franziskus and Raamana, Pradeep Reddy and Raffelt, David and Steele, Christopher J. and Quirion, Pierre-Olivier and Smith, Robert E. and Strother, Stephen C. and Varoquaux, Gaël and Wang, Yida and Yarkoni, Tal and Poldrack, Russell A.},
	month = sep,
	year = {2017},
	keywords = {Computational pipelines, Computer software, Diffusion weighted imaging, Functional magnetic resonance imaging, Magnetic resonance imaging, Neuroimaging, Operating systems, Software tools},
	pages = {e1005209},
}

@techreport{wegrzyn_thought_2018,
	title = {Thought experiment: {Decoding} cognitive processes from the {fMRI} data of one individual},
	copyright = {© 2018, Posted by Cold Spring Harbor Laboratory. This pre-print is available under a Creative Commons License (Attribution 4.0 International), CC BY 4.0, as described at http://creativecommons.org/licenses/by/4.0/},
	shorttitle = {Thought experiment},
	url = {https://www.biorxiv.org/content/10.1101/341594v2},
	abstract = {Cognitive processes, such as the generation of language, can be mapped onto the brain using fMRI. These maps can in turn be used for decoding the respective processes from the brain activation patterns. Given individual variations in brain anatomy and organization, analyzes on the level of the single person are important to improve our understanding of how cognitive processes correspond to patterns of brain activity. They also allow to advance clinical applications of fMRI, because in the clinical setting making diagnoses for single cases is imperative. In the present study, we used mental imagery tasks to investigate language production, motor functions, visuo-spatial memory, face processing, and resting-state activity in a single person. Analysis methods were based on similarity metrics, including correlations between training and test data, as well as correlations with maps from the NeuroSynth meta-analysis. The goal was to make accurate predictions regarding the cognitive domain (e.g. language) and the specific content (e.g. animal names) of single 30-second blocks. Four teams used the dataset, each blinded regarding the true labels of the test data. Results showed that the similarity metrics allowed to reach the highest degrees of accuracy when predicting the cognitive domain of a block. Overall, 23 of the 25 test blocks could be correctly predicted by three of the four teams. Excluding the unspecific rest condition, up to 10 out of 20 blocks could be successfully decoded regarding their specific content. The study shows how the information contained in a single fMRI session and in each of its single blocks can allow to draw inferences about the cognitive processes an individual engaged in. Simple methods like correlations between blocks of fMRI data can serve as highly reliable approaches for cognitive decoding. We discuss the implications of our results in the context of clinical fMRI applications, with a focus on how decoding can support functional localization.},
	language = {en},
	urldate = {2022-06-02},
	institution = {bioRxiv},
	author = {Wegrzyn, Martin and Aust, Joana and Barnstorf, Larissa and Gippert, Magdalena and Harms, Mareike and Hautum, Antonia and Heidel, Shanna and Herold, Friederike and Hommel, Sarah M. and Knigge, Anna-Katharina and Neu, Dominik and Peters, Diana and Schaefer, Marius and Schneider, Julia and Vormbrock, Ria and Zimmer, Sabrina M. and Woermann, Friedrich G. and Labudda, Kirsten},
	month = aug,
	year = {2018},
	note = {Type: article},
	pages = {341594},
}

@article{haxby_distributed_2001,
	title = {Distributed and overlapping representations of faces and objects in ventral temporal cortex},
	volume = {293},
	issn = {0036-8075},
	doi = {10.1126/science.1063736},
	abstract = {The functional architecture of the object vision pathway in the human brain was investigated using functional magnetic resonance imaging to measure patterns of response in ventral temporal cortex while subjects viewed faces, cats, five categories of man-made objects, and nonsense pictures. A distinct pattern of response was found for each stimulus category. The distinctiveness of the response to a given category was not due simply to the regions that responded maximally to that category, because the category being viewed also could be identified on the basis of the pattern of response when those regions were excluded from the analysis. Patterns of response that discriminated among all categories were found even within cortical regions that responded maximally to only one category. These results indicate that the representations of faces and objects in ventral temporal cortex are widely distributed and overlapping.},
	language = {eng},
	number = {5539},
	journal = {Science (New York, N.Y.)},
	author = {Haxby, J. V. and Gobbini, M. I. and Furey, M. L. and Ishai, A. and Schouten, J. L. and Pietrini, P.},
	month = sep,
	year = {2001},
	pmid = {11577229},
	keywords = {Brain Mapping, Face, Female, Form Perception, Humans, Magnetic Resonance Imaging, Male, Pattern Recognition, Visual, Recognition, Psychology, Temporal Lobe, Visual Pathways},
	pages = {2425--2430},
}

@misc{noauthor_neural_nodate,
	title = {Neural decoding of visual imagery during sleep - {PubMed}},
	url = {https://pubmed.ncbi.nlm.nih.gov/23558170/},
	urldate = {2022-06-02},
}

@article{shen_deep_2019,
	title = {Deep image reconstruction from human brain activity},
	volume = {15},
	issn = {1553-7358},
	url = {https://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1006633},
	doi = {10.1371/journal.pcbi.1006633},
	abstract = {The mental contents of perception and imagery are thought to be encoded in hierarchical representations in the brain, but previous attempts to visualize perceptual contents have failed to capitalize on multiple levels of the hierarchy, leaving it challenging to reconstruct internal imagery. Recent work showed that visual cortical activity measured by functional magnetic resonance imaging (fMRI) can be decoded (translated) into the hierarchical features of a pre-trained deep neural network (DNN) for the same input image, providing a way to make use of the information from hierarchical visual features. Here, we present a novel image reconstruction method, in which the pixel values of an image are optimized to make its DNN features similar to those decoded from human brain activity at multiple layers. We found that our method was able to reliably produce reconstructions that resembled the viewed natural images. A natural image prior introduced by a deep generator neural network effectively rendered semantically meaningful details to the reconstructions. Human judgment of the reconstructions supported the effectiveness of combining multiple DNN layers to enhance the visual quality of generated images. While our model was solely trained with natural images, it successfully generalized to artificial shapes, indicating that our model was not simply matching to exemplars. The same analysis applied to mental imagery demonstrated rudimentary reconstructions of the subjective content. Our results suggest that our method can effectively combine hierarchical neural representations to reconstruct perceptual and subjective images, providing a new window into the internal contents of the brain.},
	language = {en},
	number = {1},
	urldate = {2022-05-29},
	journal = {PLOS Computational Biology},
	author = {Shen, Guohua and Horikawa, Tomoyasu and Majima, Kei and Kamitani, Yukiyasu},
	month = jan,
	year = {2019},
	keywords = {Algorithms, Functional magnetic resonance imaging, Imaging techniques, Luminance, Neural networks, Optimization, Sensory perception, Vision},
	pages = {e1006633},
}

</details>

## FAIRNESS
[FAIR](https://www.go-fair.org/fair-principles/f1-meta-data-assigned-globally-unique-persistent-identifiers/) stands for **F**indability, **A**ccessibility, **I**nteroperability, and **R**euse of digital assets.
The research project reaches the Findability and Accessibility criterion, because the data used in it is open-source and linked. Also even the preprocessed data is uploaded on brainlife and it is explained, which explicit data is used. Also it is explained which commands were used to download the data from openneuro (see Dataset Exploration). Also the data can be loaded into Python by following the code on the github repository. There exists a computational environment that can be setup by installing the libraries with the *requirements.txt* file. 
Interoperability is reached, because the data follows the BIDS format. HOWEVER: When preprocessing the data, it no longer follows BIDS and needs to be renamed. So it is interoperable, but only after taking action to maintain it.
The data hits the Reuse criterion, because it not only a license is provided, but also but the data is well documented, it is described how the data was collected and what the data essentially represents.

## Openlab notebook
The [open-lab-notebook](https://github.com/JNPauli/Mental-image-decoding/open_lab_notebook.html) exists. This folder holds the **Documentation.md** file. The whole process of the project is documented there. Every obstacle, failure and win is described and sorted by date. Ideally, the thought process within the project is reasonable and transparent for everyone interested (or just put me under the fMRI, whatever suits you best).

## Computational environment
In order to fulfill the FAIR principle, a computational environment exists. This environment consists of all python modules that are used in this project, but ONLY in this project. This way a possible conflict between different versions of modules etc is prevented. You can find the modules within the **requirements.txt** file in the [code folder](https://github.com/JNPauli/Mental-image-decoding/tree/update/code) of the github repository. To install the modules, proceed this way: Download the requirements.txt file from the github repository. *Alternative way*: Create a new folder and clone the repository (1. cd your_directory,
            2. git clone https://github.com/JNPauli/Mental-image-decoding your_directory)
After downloading the requirements.txt file, cd into the directory, in which the .txt file is stored. Then, create a new conda environment by running conda create --name yourenv (replace yourenv with your environment name). Activate the environment by running conda activate yourenv. Now simply run pip install -r requirements.txt to get all the modules in your active computing environment. Et voila, thats it! Now you have all the data and modules neccessary to replicate the code. 

**CAVE**:
Super important: Please do not forget to RENAME the preprocessed data after downloading it from brainlife. See the respective notebooks for the naming convention. Also you obviously must change the paths that were set in the notebooks.
