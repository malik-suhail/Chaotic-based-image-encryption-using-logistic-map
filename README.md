
# Chaotic-based Image Encryption Using Logistic Map

This project demonstrates an image encryption technique based on **chaotic theory** using the **logistic map**. It scrambles image pixels according to a chaotic sequence, making the image unintelligible without the correct chaotic key.

## Table of Contents
- [Introduction](#introduction)
- [Features](#features)
- [How It Works](#how-it-works)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Usage](#usage)
- [Customizing for RGB Images](#customizing-for-rgb-images)
- [Future Enhancements](#future-enhancements)
- [License](#license)

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

You can install these using the following command:

\`\`\`bash
pip install numpy pillow matplotlib
\`\`\`

## Installation

1. Clone the repository:

\`\`\`bash
git clone https://github.com/yourusername/Chaotic-based-image-encryption-using-logistic-map.git
\`\`\`

2. Navigate to the project directory:

\`\`\`bash
cd Chaotic-based-image-encryption-using-logistic-map
\`\`\`

## Usage

### Encrypt an Image

To encrypt an image, you can use the \`scramble_image()\` function after generating a chaotic sequence with the logistic map.

Example:

\`\`\`python
# Load image and generate a chaotic sequence
image_data = load_image("input_image.jpg")
chaotic_sequence = logistic_map(size=image_data.size, r=3.99, x0=0.5)

# Encrypt the image
encrypted_image = scramble_image(image_data, chaotic_sequence)

# Save and display the encrypted image
save_image(encrypted_image, "encrypted_image.png")
show_image(encrypted_image, "Encrypted Image")
\`\`\`

### Decrypt an Image

To decrypt the image, you use the same chaotic key (sequence) used during encryption.

Example:

\`\`\`python
# Load the encrypted image
encrypted_image = load_image("encrypted_image.png")

# Decrypt the image using the same chaotic sequence
decrypted_image = descramble_image(encrypted_image, chaotic_sequence)

# Save and display the decrypted image
save_image(decrypted_image, "decrypted_image.png")
show_image(decrypted_image, "Decrypted Image")
\`\`\`

### Customizing for RGB Images

By default, the project handles grayscale images. To extend it for **RGB images**, each color channel (Red, Green, Blue) should be encrypted individually:

1. Split the image into R, G, and B channels.
2. Apply the chaotic encryption to each channel separately.
3. Merge the channels back together to form the encrypted RGB image.

This can be implemented with small modifications to the existing code.

## Future Enhancements

- Extend the project to support **RGB image encryption**.
- Explore other chaotic systems like the Henon map or Lorenz system for stronger encryption.
- Add an interface for customizing chaotic parameters (\`r\` and \`x0\`).

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
