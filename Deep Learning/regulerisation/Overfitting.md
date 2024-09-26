

 - Early stopping, use a validation set to determine, minum loss during the iteration and stop at there
 - data augmentation
 - Regularise the loss function with maximum aposterior estimation
 - Augmented Loss function - we use regularisation in weight update like - regularisor means controlling the loss outputs which favours the learning
	 -[[L2 regularization]]- which reduced overfitting - the L2 loss pullls it away from data optimal loss wrt training set.
	 - if we want weigths to be sparse or build networks with few connections we can use [[L1 norm]] on weight updates
- [[Batch Normalisation]]
- [[Self Normalising Neural Networks]]
- Dropout -  Randomly sets activation to 0 with probability 1-p. this Breaks internal correlation of neurons, By default weights are correlated and dont learn something new this way,  with correlated inputs all the adaptions run in a similar way, learning indepented features helps avoid overfitting
- Dropconnect - instead of neurons we drop connections