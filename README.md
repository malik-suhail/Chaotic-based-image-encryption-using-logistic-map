
# Chaotic-based Image Encryption Using Logistic Map

This project demonstrates an image encryption technique based on **chaotic theory** using the **logistic map**. It scrambles image pixels according to a chaotic sequence, making the image unintelligible without the correct chaotic key.

## Original Image

<img src="image.jpg" alt="image" width="300"/>

## Encrypted Image using Logistic map in grayscale

<img src="encrypted_image.png" alt="image" width="300"/>

## Decrypted Image in grayscale

<img src="decrypted_image.png" alt="image" width="300"/>

## Table of Contents
- [Introduction](#introduction)
- [Features](#features)
- [How It Works](#how-it-works)
- [Prerequisites](#prerequisites)
- [Usage](#usage)
- [Customizing for RGB Images](#customizing-for-rgb-images)
- [Future Enhancements](#future-enhancements)

## Introduction

Chaotic systems, such as the logistic map, are highly sensitive to initial conditions. In this project, we use the logistic map to generate a chaotic sequence that scrambles and encrypts grayscale images. Decryption requires the same chaotic key used for encryption, providing a high level of security.

## Features

- **Grayscale Image Encryption**: By default, the system encrypts grayscale images using pixel scrambling.
- **Chaotic Key**: The logistic map generates a chaotic sequence based on initial conditions (`r` and `x0`), which acts as the encryption key.
- **Lossless Decryption**: The decryption process accurately restores the original image using the chaotic key.

## How It Works

1. **Image Loading**: The input image is loaded and converted to grayscale (if necessary).
2. **Logistic Map Generation**: A chaotic sequence is generated using the logistic map formula.
3. **Pixel Scrambling**: The image pixels are scrambled according to the chaotic sequence to produce the encrypted image.
4. **Decryption**: To decrypt, the same chaotic sequence is used to reverse the pixel scrambling, restoring the original image.

## Prerequisites

Before running the code, you need to install the following Python libraries:

- **Pillow** (for image processing)
- **NumPy** (for numerical operations)
- **Matplotlib** (for visualization)


## Usage

### Load image and generate a chaotic sequence
Load an image by proving the path of the image to the image_path variable in the encrypt file.
image_path = "image.jpg"

Generate chaotic sequence based on initial conditions (`r` and `x0`)

r = 3.99  # Control parameter

x0 = 0.5  # Initial condition


### Decrypt an Image

To decrypt the image, you use the same chaotic key (sequence) used during encryption.

### Load the encrypted image
image_path = "encrypted_image.png"  # Path to the input image


## Customizing for RGB Images

By default, the project handles grayscale images. To extend it for **RGB images**, each color channel (Red, Green, Blue) should be encrypted individually:

1. Split the image into R, G, and B channels.
2. Apply the chaotic encryption to each channel separately.
3. Merge the channels back together to form the encrypted RGB image.

This can be implemented with small modifications to the existing code.

## Future Enhancements

- Extend the project to support **RGB image encryption**.
- Explore other chaotic systems like the Henon map or Lorenz system for stronger encryption.
- Add an interface for customizing chaotic parameters (\`r\` and \`x0\`).
