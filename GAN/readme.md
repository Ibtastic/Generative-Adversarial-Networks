In the above file I'm implementing Deep Convolutional GAN , based on this paper on [DCGAN](https://github.com/user/repo/blob/branch/other_file.md) which is in contrast to [Ian GoodFellow's paper]( http://papers.nips.cc/paper/5423-generative-adversarial-nets.pdf). This is the original paper on GAN and implements a dense network both in the generator and the discriminator rather than a CNN.

I am using the **CIFAR10** dataset and I'm training the model on a single class.

* In the generator we use a method called Upsampling to produce images. I have used Upsampling2D but TransposeConv2d + stride or PixelShuffle could be used alternatively.
* The Discriminator has several Conv2d layers for the classification task's.

A lot of changes have been made in GAN's Architecture since Goodfeloow's original paper , but some things remain the same like:-

* Normalizing the input
* The activation function in all except the last layer of the generator must be a ***relu*** , it helps with the problem of vanishing gradients that appears in the generator during the starting iterations when the discriminator is too good as the generator is just beggining to learn.
* The activation in the last layer of the generator which is a Dense Layer is *tanh* activation.
* Same goes for the discriminator, all the layers except the last have relu as activtaion and the last Dense layer uses *Sigmoid* Activation.
* We use binary_cross_entropy method to calculate loss in both the adversaries.

Now some hacks/tips that have been introduced in papers in the last few years to make GANs better are:-

* Using BatchNormalization in all layers except the input layer in the generator and the output layer in the discriminator.
* Using Adam Optimizer for the generator and SGD for the discriminator.
* Adding some random noise to the labels before feeding them to the discriminator.
* Sampling from a *Gaussian Distribution* instead of a *Uniform distribution*.
* Construct different mini-batches for real and fake, i.e. each mini-batch needs to contain only all real images or all generated images.
* Pre-training the discriminator.

It's not necessary that all the above tricks will work for your model. You will have to find the ones that do.
