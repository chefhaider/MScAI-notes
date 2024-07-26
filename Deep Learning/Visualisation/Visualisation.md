

why do we visualisation

- comminicate
- to evaluate problems such as dying relu, training data
- unndersstaning how networks woek

types of visualisaiton
- architecture
- training 
- paramater/ visualisatio learning of data


types of architecture
- node link base
- block base
sophiscated example: gaph core

types of training visualisation
- input
- parmaeters
- output
e.g tensorboard

types of visualisation for parameters
motivation? why it performs better in controlled enviornment but fails in lab
*confounding factor or cofounder is an external factor from the data that influences the training*
if cofounder is knwon actively include the information and try to supress it or try to avoid them in data collection

Adverarial example: if you know the entire network you can deisgn a noise pattern which can lead to false prediction


- visualise the learn kernel or filter weights to see the patterns - if its very noisy theres something wrong
- visualise the activations - we can see if activations are present but we cant tell why those specific activations are responding
- occlusion, move around a patch around the image and and visualise the confidence of a specific decision wrt the position - idenitfy confounds or wrong focus - *see slide 31 to see how it ultimatelly effects the confidence and how we can evaluate*
- maximally activating the images - take the patches and order them by confidence
- Distributed Stochastic Neighbour Embedding - reduce diminsion and create embeddings based on actvation - as a result similar images are located in neighbourhood. helps in understanding feature extraction

*no notes, see slides for*
Gradient based visualisation
Optimisation based techniques