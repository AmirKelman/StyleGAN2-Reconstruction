# StyleGAN2 Reconstruction Project

This repository contains code and results for an image reconstruction project using StyleGAN2, implemented in Google Colab. The project focuses on inverting real and synthetic images, as well as recovering degraded images through deblurring (Section 3.3.1), colorization (Section 3.3.2), and inpainting (Section 3.3.3), as detailed in the accompanying report.

## Overview

The project leverages StyleGAN2's latent space optimization and perceptual loss (via VGG16) to:
- Invert real images (e.g., Amir's wedding photo) and synthetic images into the latent space.
- Recover images degraded by Gaussian blur, grayscale conversion, or inpainting masks.
- Explore hyperparameter effects (e.g., 
num_steps, latent_dist_reg_weight) on reconstruction quality.

Key findings from the report:
- Gaussian blur recovery restores sharpness but struggles with fine details.
- Grayscale recovery infers plausible colors, though exact matching is challenging.
- Inpainting effectively reconstructs masked regions with minor boundary inconsistencies.

## Files

### Code
- Amir_Copy_of_IMPR_Ex5_Deep_Style_Image_Prior_2024_2025_.ipynb: Jupyter notebook with the full implementation, including setup, degradation functions, and optimization logic.

### Report
- Amir Kelman Image Processing - Exercise 5.pdf: Detailed report covering Sections 3.1 (inversion), 3.2 (synthetic reconstruction), 3.3.1 (deblurring), 3.3.2 (colorization), and 3.3.3 (inpainting).

### Output Files
- `latents/`: Directory containing `.npz` files (e.g., `inverted_latent.npz`) with optimized latent vectors for each reconstruction.
- Image files under directories (e.g., `3.2/`, `3.3.1/wedding/`, `3.3.2/alan/`):
  - `original_image.png`: Original input image.
  - `original_degraded_image.png`: Degraded version (blurred, grayscale, or masked).
  - `final_inverted_image.png`: Reconstructed image after optimization.
  - `intermidiate_*.png`: Intermediate reconstruction steps.
  - `loss_plot.png`: Loss progression during optimization.

### Resources
- `impr_ex5_resources/stylegan2-ada-pytorch/`: Extracted StyleGAN2-ADA-PyTorch code and pretrained models.
- `Wedding_image_Amir_Aligned.jpg`, `alan_turing_grayscale.png`, `fei_fei_li_original.png`, `yann_lecun_blur.png`: Input images used for experiments.

## Setup

### Prerequisites
- Python 3.x
- PyTorch (with CUDA support for GPU acceleration)
- Additional libraries: `ninja`, `mediapy`, `opencv-python`, `imageio`, `PIL`

### Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/AmirKelman/StyleGAN2-Reconstruction.git
   cd StyleGAN2-Reconstruction" > README.md
git add README.md
git commit -m "Add README file"
git push
