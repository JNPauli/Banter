# Research Question aka what is this project all about?

This research project deals with the field of mental imagery. Mental imagery refers to the imagination of a certain object, scene, person etc..

Typically mental imagery is investigated by combining functional magnet resonance imaging (fMRI) and machine learning techniques. fMRI has the adavantage of a high spatial resolution, altough it comes with a poor temporal resolution. The given brain activity, recorded in the fMRI, can then be decoded through machine learning. A popular approach would be a classifier like the logistic regression or the support vector machine. To decode brain activity means, in general, to classify the activity into a given category. For example, a participant could look at cats and dogs in an fMRI experiment. Decoding in this example would mean that the machine learning algorithm could predict, whether the participant was seeing a dog or a cat, given the respective voxel pattern. In terms of mental imagery, the participant would imagine those images of a cat or dog. Decoding has been around many years and has been proven to work quite well, see [Naselaris et al., 2011](https://www.sciencedirect.com/science/article/pii/S1053811910010657?casa_token=1Uey6U2ByjwAAAAA:6qHcdw5hdNlKg6e-WymuGXcqPSg2zu648D_dCGAQNe5DEtIpaQp4h8DE-EdaCCbLw8DVA-uE9A).

The question that will be answered in this research project is, whether the voxel pattern observed during mental imagery can be decoded. In machine learning terms: The algoritm will be both trained and tested on the mental imagery voxel pattern. Mental imagery is an interesting research area, because it is more subjective than solely looking at given pictures. Just imagine the difference in looking at a picture of a dog (insert dog picture here). Everyone agrees, that this is how a dog looks. And you could probably imagine, that everyone would recognize this picture of a dog after a week or two. But viewing objects in your mind is something different. It comes with far more difficulties, because you cannot control it as much. Thoughts are racing in ones mind, and it might be difficult to maintain mental focus. Already there are some studies that show that decoding from mental imagery is indeed possible ([Reddy et al., 2010](https://www.sciencedirect.com/science/article/pii/S1053811909012701?casa_token=lw6pq-cpWKwAAAAA:PAew2-UYG3rEqa4fU-dgZM3QuAq-JcgEE-_BLwpbfly0ewSrnT9nS7E05KAek0LKB8mOQxI0JQ)). Test accuracies were about 50%. Evidence that both perception and imagination share similiar voxel patterns was given. However, only 4 categories were shown. Would this also work with more categories? Leading to more cognitive load and thus reducing focus and might introduce more noise in the thought process.

The hypothesis answered in this research project is the following:
A machine learning classifier can decently predict a stimulus given the respective voxel pattern.

Different classifiers are implemented and compared. Those are: Logistic regression, support vector machine and a fully connected neural network. All analyzes are done in python.

The dataset used is open source and can be obtained from [openneuro](https://openneuro.org/datasets/ds001506/versions/1.3.1). The respective paper from Shen et al. (2019) is also available [here](https://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1006633).



