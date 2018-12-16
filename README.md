# \[DLAI 2018\] Team 2: Autoencoder

This project is focused in autoencoders and their application for denoising and inpainting of noisey images. Furthermore, it was investigated how these autoencoders can be used as generative models, so-called Variational Autoencoders (VAEs).
It was conducted in the context of the course [Deep Learning for Artificial Intelligence at UPC (Autumn 2018)](https://telecombcn-dl.github.io/2018-dlai/) by the students Michaela Jurková, Michał Krzemiński, Michal Šimek and Daniel Seifert.

## Motivation:

As none of us worked on Deep Learning before, we chose to start off with the rather simple topic of autoencoders in order to learn how to built a neural network, how to train it and how the setting of hyperparameters affect its performance. Moreover, we found interest in autoencoders due to their versatile applications in pattern recognition and classification, denoising and even in generation of completely new data.

## Goals:

### Step 1: Implementation of a simple autoencoder in Keras:
- Learn how autoencoders work
- Build first examples based on the tutorials based on i.a. the MNIST data set
- Investigate performance changes for varying parameters

### Step 2: Implementation of a denoising and inpainting autoencoder:
- Preprocess picture data set by adding noise manually
- Make hyperparameter adjustments to improve its performance
- Apply the denoising and inpainting to more complex datasets

### Step 3: Implementation of Variational Autoencoder (VAE)
- Learn how VAEs work using the MNIST data set
- Investigate performance changes when extending the latent space
- Apply it to more complex datasets 

## What is an autoencoder

![autoencoder](https://blog.keras.io/img/ae/autoencoder_schema.jpg)

Autoencoder refers to a artificial neural network where the input data are compressed by an encoder and this compressed representation is then fed into a decoder to be decompressed into the reconstructed output which is lossy. It is learned automatically from data examples.
Because autoencoders are data-specific, they can only be used with applications using data similar with the data the particular autoencoder have been trained on and won’t really work with different data. 

## Denoising autoencoder with MNIST dataset

### Preparing the data

We loaded the MNIST images without the labels because we don’t need them. After that, we normalized the loaded data values into 0-1 of 32-bit float data type and then reshaped it to the array suitable for the network.

### Model of autoencoder

For the encoder, we used a stack of two Conv2D (2D convolution layer) and MaxPooling2D (2D pooling layer) layers. RelU activation function was used with both Conv2D layers.
For the decoder, we used the stack of two Conv2D with RelU activation and MaxPooling2D layers again, followed by the last layer of a Conv2D with Sigmoid activation function.
We used the convolutional neural networks because on images they perform much better than the other types.
We set the AdaDelta optimizer and Binary Cross-entropy loss function for our model.

### Creating a corrupted images 

We created a synthetic corrupted as an input images for our denoising and inpainting autoencoder. We created a three types of images corruption: applied a noise, generated a randomly placed horizontal black stripes (10 stripes over 28 rows) and created a randomly placed gray block of size 10x10 over the original images.

### Training the network

We trained the network for 100 epochs with batch size of 128. We used the corrupted images as an input of the autoencoder and the original images as a desired output in order to train the autoencoder to map the corrupted input images into the clean output images. After training of the 100 epochs, we got the losses values less than 0.1.

### Results

#### Noisy images
![Noisy MNIST images](https://github.com/telecombcn-dl/2018-dlai-team2/blob/master/Results/mnist_noisy.png?raw=true)

#### Images with stripes
![MNIST images with stripes](https://github.com/telecombcn-dl/2018-dlai-team2/blob/master/Results/mnist_strips.png?raw=true)

#### Images with gray blocks
![MNIST images with blocks](https://github.com/telecombcn-dl/2018-dlai-team2/blob/master/Results/mnist_blocks.png?raw=true)



# Resources:
- [Keras](https://blog.keras.io/building-autoencoders-in-keras.html)
