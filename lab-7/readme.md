# CS3807 – Deep Learning Laboratory

## Experiment 7

**Comprehensive Study of Autoencoders, Convolutional Autoencoders, Denoising Autoencoders and Variational Autoencoders**

### Objective

Study autoencoder-based architectures for image representation learning and reconstruction. The experiment covers fully connected autoencoders, convolutional autoencoders, denoising autoencoders and variational autoencoders, along with latent-space analysis, reconstruction quality, noise removal, image generation and latent-space interpolation.

---

## Additional Analysis

The experiment compares model performance across several studies:

- Fully Connected Autoencoder (FC AE)
- Convolutional Autoencoder (Conv AE)
- Denoising Convolutional Autoencoder (Denoising CAE)
- Variational Autoencoder (VAE)
- Effect of latent dimension on reconstruction
- Effect of Gaussian noise level on denoising performance
- Reconstruction quality comparison
- Latent-space visualization
- VAE image generation
- Latent-space interpolation
- Reconstruction-error analysis
- High-reconstruction-error image analysis

The analysis includes:

- Original and reconstructed images
- Training and validation loss curves
- FC AE and Conv AE reconstruction comparison
- Clean, noisy and denoised images
- Noise-level performance comparison
- VAE latent-space visualization
- Randomly generated VAE samples
- Latent-space interpolation
- VAE training and validation reconstruction loss
- Reconstruction-error distribution
- High-error reconstruction examples

---

## Dataset

### Main Experiment

The notebook uses image data for unsupervised representation learning and reconstruction.

- **Input:** Grayscale handwritten digit images
- **Task:** Image reconstruction and representation learning
- **Train/Validation/Test:** Training, validation and test splits are used

The same image data is used to study deterministic and probabilistic latent representations.

---

## Model Architecture

### Fully Connected Autoencoder

The fully connected autoencoder consists of:

```text
Input Image
      ↓
Encoder
      ↓
Latent Representation
      ↓
Decoder
      ↓
Reconstructed Image