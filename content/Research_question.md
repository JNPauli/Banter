# Research Question aka what is this project all about?

This research project deals with the field of mental imagery. Mental imagery refers to the imagination of a certain object, scene, person etc..

Typically mental imagery is investigated by combining fMRI and machine learning techniques. fMRI has the adavantage of a high spatial resolution, altough it comes with a poor temporal resolution. The given brain activity, recorded in the fMRI, can then be decoded through machine learning. A popular approach would be a classifier like the logistic regression or the support vector machine. To decode brain activity means, in general, to classify the activity into a given category. For example, a participant could look at cats and dogs in an fMRI experiment. Decoding in this example would mean that the machine learning algorithm could predict, whether the participant was seeing a dog or a cat, given the respective voxel pattern. In terms of mental imagery, the participant would imagine those images of a cat or dog. Decoding has been around many years and has been proven to work quite well, see [Naselaris et al., 2011](https://www.sciencedirect.com/science/article/pii/S1053811910010657?casa_token=1Uey6U2ByjwAAAAA:6qHcdw5hdNlKg6e-WymuGXcqPSg2zu648D_dCGAQNe5DEtIpaQp4h8DE-EdaCCbLw8DVA-uE9A).

The question that will be answered in this research project is, whether the voxel pattern observed during mental imagery can be decoded. In machine learning terms: The algoritm will be both trained and tested on the mental imagery voxel pattern. Mental imagery is an interesting research area, because it is more subjective than solely looking at given pictures. Just imagine the difference in looking at a picture of a dog (insert dog picture here). Everyone agrees, that this is how a dog looks. And you could probably imagine, that everyone would recognize this picture of a dog after a week or two. But viewing objects in your mind is something different. It comes with far more difficulties, because you cannot control it as much. Thoughts are racing in ones mind, and its difficult to maintain mental focus.

Thus, the hypothesis is the following:
A machine learning classifier can decently predict a stimulus given the respective voxel pattern.

Different classifiers are implemented and compared. Those are: A logistic regression, support vector machine and a fully connected neural network.

The dataset used is open source and can be obtained from [openneuro](https://openneuro.org/datasets/ds001506/versions/1.3.1). 



