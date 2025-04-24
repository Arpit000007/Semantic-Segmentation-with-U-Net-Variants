# Multi‑Class Semantic Segmentation with U‑Net Variants

**Models:** Vanilla U‑Net, Residual U‑Net, Attention‑Gated U‑Net  
**Framework:** PyTorch  
**Task:** 13-class segmentation on 256×256 images

---

## 📋 Overview
This repository contains implementations of three U‑Net based architectures for multi‑class semantic segmentation:

1. **Vanilla U‑Net** – Baseline 4-level encoder‑decoder with skip connections.
2. **Residual U‑Net** – Replaces each double‑conv block with a residual block to improve gradient flow.
3. **Attention‑Gated U‑Net** – Integrates additive attention gates in skip connections to focus on relevant spatial features.

All models are trained for 50 epochs on 256×256 images and evaluated on a held‑out test set using mean Intersection‑over‑Union (mIoU).

## 🚀 Quickstart

###  Prepare Data
Organize your dataset as:
```
dataset_256/
├─ train/
│  ├─ images/
│  └─ labels/
├─ test/
│  ├─ images/
│  └─ labels/
```


Training scripts will log:
- **Loss curves** (train & validation)
- **mIoU curves** (train & validation)
- **Final test mIoU**

Visualizations for sample predictions will be saved in `outputs/`.

## 📈 Results
| Model                   | Test mIoU (%)  | Δ vs. Vanilla |
|-------------------------|---------------:|--------------:|
| **Vanilla U‑Net**       |           85.8 |         —     |
| **Residual U‑Net**      |           86.4 |       +0.6    |
| **Attention‑Gated U‑Net** |         86.7 |       +0.9    |


## 🛠️ Project Structure
```
├── sematic segmentation.py      # Training & evaluation script
└── README.md                    # Project documentation
```

## 📦 Requirements
```
torch>=1.8.0
torchvision
numpy
matplotlib
Pillow
```

## 🔗 References
- Ronneberger et al., "U‑Net: Convolutional Networks for Biomedical Image Segmentation"
- Oktay et al., "Attention U‑Net: Learning Where to Look for the Pancreas"

---

