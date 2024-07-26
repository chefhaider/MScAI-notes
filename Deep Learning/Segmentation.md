
evaluation
- problem: sometime the classes are not equally distributed so for this we can use technique such as accouting for background class

using cnn as encoder and decoder for segmentation
	not autoencoder, because the input is the image and  output is the image mask
	the decoder  performs - unpooling, 

context knowledge for segmentation
	use from previous downsampling approach and use it within the decoder branch to use it a sum to procude highly resolved image? explain more

segnet
reude the information during pooling from downsample at the time of upsampling such that you get better results

unet
 - state of the art
 - name from the shape - high resolution from the downsample and low resoluton, and then therea a decoder branch that upsamples everythong again
 - the key information is skip connections connecting the two different levels of encoder and decoder
 - 
advanc topics
	a gan can be used to augment the loss, the output of the segmentor as an input for dicrimnator the discrimniator decides, weather this is an automatic or a manual segmentation which can be used as an adversarial loss