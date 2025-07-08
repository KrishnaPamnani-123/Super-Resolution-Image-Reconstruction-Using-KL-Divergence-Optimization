# Super-Resolution Image Reconstruction Using KL Divergence

This project explores a patch-based super-resolution technique for enhancing image quality from low-resolution (LR) inputs to high-resolution (HR) outputs using **Kullback-Leibler (KL) divergence** as an optimization objective.

## Overview

Traditional interpolation techniques often fail to retain image details while upscaling. This project optimizes the histogram distributions of HR image patches to match those of LR patches using KL divergence, enabling superior reconstruction results.

## Key Features

- KL Divergence Optimization: Matches histograms of LR and HR patches.
- Patch-Based SR: Divides LR images into patches and optimizes them individually.
- Multiprocessing: Accelerates patch optimization using Python's multiprocessing.
- Grid Search: Tunes hyperparameters like patch size, learning rate (alpha), bins, and iterations.
- Evaluation Metrics: Uses Structural Similarity Index (SSIM) and Mean Absolute Error (MAE).

## Dataset

- LR Image Sizes: `(510, 339)` and `(510, 384)`
- HR Image Sizes: `(2040, 1356)` and `(2040, 1536)`
- Includes diverse natural scenes and objects with different textures and colors.

## Methodology

### KL Divergence Optimization
1. Compute histogram of LR patch.
2. Initialize HR patch 
3. Iteratively adjust pixel values in HR patch based on KL divergence gradient.

### Super-Resolution Pipeline
1. Split LR image into patches.
2. Optimize each patch using KL divergence.
3. Reconstruct HR image from optimized patches.
4. Evaluate reconstructed image with SSIM and MAE.

### Hyperparameter Tuning
- Patch Sizes: (16×16), (32×32)
- Alpha: 0.01, 0.05
- Bins: 256, 512
- Max Iterations: 40, 50, 60

##  Results

| Image          | SSIM   | MAE     |
|----------------|--------|---------|
| Penguin        | 0.540  | 183.85  |
| 0807x4m worst  | 0.1714 | 135.87  |
| 0843x4m best   | 0.8856 | 111.30  |

- Average SSIM: 0.4679  
- Average MAE: 166.50


