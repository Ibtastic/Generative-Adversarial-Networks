# Generative-Adversarial-Networks

GANs are a class of Unsupervised Learning Algorithms that do much more than just recognizing image / voice , predicting or translating. They implement deep neural networks or CNN and are comprised of two parts, pitting one against the other (thus the “adversarial”). These two parts are called the Generator and the Discriminator.

* **Generator** - The generator takes the role of a forger and tries to create music/image/speech from random noise. It learns to map from a latent space to a particular data distribution of interest. It generally implements a Deconvolutional Network to do so.
* **Discriminator**- The Discriminator on the other hand takes the role of the evaluater and tries to distinguish the fake data (created by the Generator) from the real one. It is usually implemented as a Convolutional Network.

With that said what follows is a loop in which -
* The generator tries to maximize the probability of fooling the Discriminator by making the images(for example) more close to real in each step thereby making the Discriminator classify them as real.
* And the discriminator guides the generator to produce more realistic images , by classifying it's images as fake.


![alt text](https://skymind.ai/images/wiki/GANs.png)



You can think of a GAN as a game of cat and mouse between a counterfeiter (Generator) and a cop (Discriminator). The counterfeiter is learning to create fake money, and the cop is learning to detect the fake money. Both of them are learning and improving. The counterfeiter is constantly learning to create better fakes, and the cop is constantly getting better at detecting them. Competition in this game drives both teams to improve their methods until the counterfeits are indistiguishable from the genuine or real money


In this repository I'll be exploring and implementing some of the applications of GANs that I find particularly interesting.
