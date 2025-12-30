# Deep Learning for Image Generation and Style Transfer

This project explores multiple deep learning approaches for image generation and transformation, investigating the strengths and limitations of both adversarial and deterministic modeling strategies. The notebook provides implementations and comparative experiments using Generative Adversarial Networks (GANs) and Adaptive Instance Normalization (AdaIN).

## Project Overview

The goal of this notebook is to demonstrate and analyze different techniques for manipulating visual representations. It covers two primary domains:
1.  **Generative Modeling:** Creating new synthetic images from noise.
2.  **Style Transfer:** Applying the artistic style of one image to the content of another.

## Methods Implemented

### 1. Generative Adversarial Network (GAN)
A standard GAN architecture was implemented to generate synthetic images.
* **Focus:** Explored the fundamental min-max game between the Generator and Discriminator.
* **Observations:** Highlighted common challenges such as training instability and mode collapse.

### 2. Conditional GAN (cGAN)
An extension of the standard GAN that incorporates conditioning information (e.g., class labels) into both the generator and discriminator.
* **Focus:** Controlled image generation.
* **Observations:** Demonstrated how conditioning improves control over the output, increases diversity, and enhances the interpretability of the generated results.

### 3. Adaptive Instance Normalization (AdaIN)
A deterministic, feature-based approach for arbitrary style transfer. Unlike GANs, this method does not require adversarial training.
* **Focus:** Manipulating feature statistics (mean and variance) in latent space to transfer style.
* **Observations:** Proven to be an efficient method for global style transfer. Experiments revealed that its visual impact is highly dependent on data complexity; effects are significant on natural images but subtle on low-resolution or binary images (e.g., MNIST).

## Datasets

The project utilizes the following datasets for training and evaluation:
* **MNIST:** Used primarily for benchmarking the GAN and cGAN models to demonstrate generation of handwritten digits.
* **Natural Images:** Used for evaluating the AdaIN style transfer model to showcase artistic effects.

## Key Findings

* **Adversarial vs. Deterministic:** GANs offer powerful generative capabilities but are difficult to stabilize. Feature-based methods like AdaIN offer a stable, deterministic alternative for specific tasks like style transfer.
* **Data Complexity:** The effectiveness of style transfer is correlated with the information content of the image. Simple binary images (like MNIST) possess fewer feature statistics to manipulate, rendering AdaIN less effective compared to its performance on rich, natural images.
* **Control:** Conditional GANs successfully mitigate some of the "black box" nature of standard GANs by allowing directed generation.

## Dependencies

To run this notebook, you will need a standard Deep Learning environment, likely including:
* Python 3.x
* Jupyter Notebook
* TensorFlow/Keras
* NumPy
* Matplotlib
* Torchvision
