
training strategies
- check gradient
- check loss functions
- check layer implementations
- compare the analytic and numeric gradient 

*see slide*

make checks with turning of data augentation, dropout, and regulerization terms, repeat with multiple random initializations to see if initialization is incorrect
take a subset of data to overfit and get zero loss - if the network cant overfit there could be a bug in the implementation or the model may not be suffiecent so increasing the capacity, parameters etc 
get an idea about data, loss and network behaviour - looking at the Loss/epochs graphs make sure no exploding or vanishing gradient 
 - if noisy curves increase the batch size
use the validation  set, the trainig loss would always go down, but the test loss might go up at some instance, so use that to evaluate if overfit has occured
 if train and validation loss are close but very high this means underfitting - so decrease the regularization and increase the model size
 tip: save intermediate model which can be used for evaluating later
 monitor the weights, and keep track of the updates -  the range should be sensible like 1e-3
 for CNN we can use initial filters, to check if they are smooth and not too noisy
 consider - dying relu problem by checking large activations 

## practices for optimisers and learning rate

with sgd the gradient noise funcitons becomes very noisy thus mini batch sgd
and try better optimisers like ADAM etc 