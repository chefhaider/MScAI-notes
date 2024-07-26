[]()
Early Architecture

LeNet - 5 classeic typical CNN
AlexNet (2012) - can implemented to two differnent GPUs, can be trained and then shyncronised
	not a very deep arhcitecture

network in network aka 1x1 convolutions

VGG Network
	reduce spatial dimension and increase the channel dimension gradually, so we move from a spatial to interpretation domain 


Google Net, Inception-v1
	good ideas to save computations 
	intersting features are insception blocks - because it lets the network decide weather it wants to pool or convulve
	it has differnet branch for each convulv i.e 1x1  followed by nxn convlulve or ma pooling followed by 1x1 pooling, these branches go parellel and then these are concatenated for next layer, this way the network decides which branch to move for the next layer - the bottleneck 1x1 layer is used to compress for easier computations