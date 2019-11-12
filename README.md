# Finding Tony's Glasses
## EVA Assignment-10
The computer identifies the shades on Tony Stark's face. 
[Weights from a model trained on imagenet are downloaded for VGG16 architechture to make prediction]
# Second Part:

## In the paper, *CNN-based Segmentation of Medical Imaging Data*  (page 21, table 7). The Receptive field increases from 29 to 45.Explain this increase

The reason for this seemingly aberrant pattern in the receptive field is due to the use of strided convolution (stride=2). When a stride of two is used every next pixel in the resulting channel would have seen two new pixels instead of one new pixel as in the case of stride=1. Hence we would see 2x2=4 new pixels if we use stride=2 once, generalizing it gives 2x(kernel size-1). Further once we start stacking layers the growth will be exponential hence it will be 2^n x (kernel size-1). If we take into account the deconvolution as well then we will arrive at the formula given in the paper viz,
ϕi = ϕi−1 + 2^(η−τ) x (Filter size − 1)

applying this formula for our case,
ϕi−1=29
η=3(consider layers with exponential growth in RF)
τ=0
Filter size=3
we get,
ϕi =29+8x2=45

hence the receptive field of the succeeding layer is 45





