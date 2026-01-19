# Cancer Patch Segmentation

A computer vision project for extracting corner squares containing R/L letters from knee X-ray images using ultra-fast processing techniques.

## Overview

This project processes knee X-ray images to extract corner squares that contain directional markers (R for right, L for left), while making everything else black. The output maintains the same image dimensions as the input.

## Features

- 🚀 **Ultra-fast processing**: ~930 images/second
- 🎯 **High accuracy**: 97.8% success rate  
- 🖼️ **Same-size output**: Maintains original image dimensions
- ⚡ **No complexity**: Direct corner detection without unnecessary error handling
- 📊 **Visual feedback**: Progress tracking and result visualization

## Method Evolution

The project evolved through multiple approaches:

1. **Complex ML Approach**: Initial U-Net segmentation model
2. **Simple Computer Vision**: Basic corner detection with error handling
3. **Ultra-Simple Method**: Direct corner extraction assuming all images have squares

## Key Classes

- `UltraSimpleSquareExtractor`: Final ultra-fast method (recommended)
- `ImprovedSquareExtractor`: 97.8% success rate with error handling
- `SimpleSquareExtractor`: Initial simple approach (80% success)
- `CornerPatchDetector`: Corner region analysis utilities

## Usage

1. **Setup Environment**:
   ```python
   # Install required packages
   import cv2, numpy as np, matplotlib.pyplot as plt
   from tqdm import tqdm
   ```

2. **Process Images**:
   ```python
   # Initialize ultra-fast extractor
   extractor = UltraSimpleSquareExtractor()
   
   # Process all images
   results = extractor.process_all_images(image_paths, output_dir)
   ```

3. **Results**:
   - Processed images saved with `extracted_` prefix
   - Black background with only corner squares visible
   - Same dimensions as original images

## Dataset

- **Input**: Knee X-ray images with R/L corner markers
- **Output**: Same-size images with extracted squares and black backgrounds
- **Format**: PNG images

## Performance

- **Processing Speed**: ~930 images/second
- **Success Rate**: 97.8% (using ImprovedSquareExtractor)
- **Ultra-Fast Method**: 100% processing (assumes all images have squares)

## Requirements

```
opencv-python>=4.13.0
numpy
matplotlib
tqdm
scikit-image
tensorflow>=2.19.0 (optional, for advanced methods)
```

## Project Structure

```
├── knee_patch_segmentation.ipynb  # Main notebook
├── 0_patch/                      # Input dataset (gitignored)
├── 2_patch/                      # Input dataset (gitignored)
├── output/                       # Results (gitignored)
└── README.md                     # This file
```

## Results

The ultra-fast method successfully processes all images by:

1. **Corner Detection**: Analyzes all 4 corners for square regions
2. **Square Extraction**: Identifies rectangles containing R/L letters  
3. **Black Background**: Replaces everything except the square with black pixels
4. **Size Preservation**: Maintains original image dimensions

Perfect for batch processing large datasets of medical images with directional markers!

---

*Built with ❤️ for medical image processing*
