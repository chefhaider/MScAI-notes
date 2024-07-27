

note: modaliities means different types data, text, audio etc
		manifold: low dimension representation of data


making labels available for massive data?
methods
for making it without manually labelling
sol
weakly supervised 

using the label and gradient we can localise the label, thus we can get cheap bounding boxes

semi supervised technique: partial or little data of labels and we try to apply to a larger dataset

a typical technique would be bootstraping we make a classifer from partial data and then estimate which of the data points have been classified correctly and then we take the reliable into a new training set and we iterate untill we have a better system
Unspuervised: we have no labeled data

Label free learning
dimenionality reduction
the smaller dimension is supposed to carry all the information
application: 
network initialisation - transfer learning slide - 4 
so if we perform dimensionality reduction over a neural network, we potentially have fewer weights that we have to learn 
Clustering - identify images in a low dimensional space
generative models - 
		further applications
			missing data, image to image translation, reinforcement learning(simulate possible futures)