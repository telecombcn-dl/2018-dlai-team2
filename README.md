# \[DLAI 2018\] Team 2: Autoencoder

This project is focused in autoencoders and their application for denoising and inpainting of noisey images. Furthermore, it was investigated how these autoencoders can be used as generative models, so-called Variational Autoencoders (VAEs).
It was conducted in the context of the course [Deep Learning for Artificial Intelligence at UPC (Autumn 2018)](https://telecombcn-dl.github.io/2018-dlai/) by the students Michaela Jurkova, Michał Krzemiński, Michal Šimek and Daniel Seifert.

## Motivation:

As none of use worked on Deep Learning before, we chose to start off with the rather simple topic of autoencoders in order to learn how to built a neural network, how to train it and how the setting of hyperparameters affect its performance. Moreover, we found interest in autoencoders due to their versatile applications in pattern recognition and classification, denoising and even in generation of completely new data.

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

### Resources:
- [Keras](https://blog.keras.io/building-autoencoders-in-keras.html)
