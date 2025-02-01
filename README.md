# Handwritten Digit Classification & Generation

## Overview
This project focuses on **classifying and generating handwritten digits** using deep learning techniques. A **CNN classifier** was trained to recognize digits, while a **Variational Autoencoder (VAE)** was used to generate synthetic digit images.

## Libraries Used
- **PyTorch** – Model building and training  
- **torchvision** – Handling the MNIST dataset  
- **matplotlib** – Visualizing results  

## Model Implementation

### 1️⃣ Dataset Preparation  
- Imported the **MNIST dataset** (digits 0–9).  
- Preprocessed images into **tensors** and normalized them.  
- Used **DataLoaders** to efficiently batch and split into training/testing sets.  
- Set computations to **GPU (default)** with CPU fallback.  

### 2️⃣ Variational Autoencoder (VAE)  
- Defined a **VAE with an encoder-decoder architecture**:
  - **Encoder:** Compressed images into a small **latent space**.  
  - **Reparameterization Trick:** Added randomness to improve generalization.  
  - **Decoder:** Reconstructed images from the latent space.  
- Trained by minimizing **reconstruction loss** for accurate digit recreation.  

### 3️⃣ CNN Classifier  
- Constructed a **CNN with convolutional layers** for feature extraction.  
- Used **fully connected layers** to classify digits **0–9**.  
- Trained using **cross-entropy loss** over multiple epochs.  

### 4️⃣ Digit Generation Process  
- Initialized a **random latent vector** and passed it through the VAE decoder.  
- Optimized using the **CNN classifier's feedback** to maximize confidence for a specific digit (1–9).  
- Generated **digit-like images** based on classifier feedback.  

### 5️⃣ Experimenting with Non-Existent Digits  
- Tried generating images for **digit 11** (a non-existent class).  
- Since the classifier never learned this class, the output was **random noise**.  

## Results & Visualization  
- Generated images for digits **1–9**.  
- Created **unexpected/funny images** for non-existent classes.  
- Visualized the training process and generated outputs using **matplotlib**.  

## How to Run  
1. Install dependencies:  
   ```bash
   pip install torch torchvision matplotlib
