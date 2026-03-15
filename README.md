# Panorama Image Stitching

A multi-image panorama stitching pipeline built with Python and OpenCV, using SIFT feature detection and homography-based alignment.

---

## Overview

Stitches 4 overlapping images into a single panorama by detecting and matching keypoints across images, computing homography transformations, and blending overlapping regions.

---

## Techniques Used

- **SIFT** — Scale-Invariant Feature Transform for keypoint detection and descriptor extraction
- **BFMatcher + Lowe's Ratio Test** — filters reliable feature matches (threshold: 0.75)
- **RANSAC Homography** — robust estimation of perspective transformation between image pairs
- **Feather Blending** — distance-transform-based alpha blending for seamless transitions in overlapping regions
- **Multiple Reference Frames** — experimented with different root images (image 0, 2, 3) to compare alignment quality

---

## Pipeline

```
Input Images (x4)
      ↓
Grayscale Conversion
      ↓
SIFT Keypoint Detection
      ↓
BFMatcher Feature Matching
      ↓
RANSAC Homography Estimation
      ↓
Perspective Warping
      ↓
Feather Blending
      ↓
Panorama Output
```

---

## Requirements

```bash
pip install opencv-python numpy matplotlib pillow
```

---

## Run

```bash
jupyter notebook CV_ASM2.ipynb
```

Or open directly in [Google Colab](https://colab.research.google.com/drive/1eNCD5MvKXq8Gj-VTGTF2NnId8SUaR5Pi).
