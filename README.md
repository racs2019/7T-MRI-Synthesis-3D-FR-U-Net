# 7T MRI Synthesis from 3T Using Deep Learning

This repository supports the research presented in the paper:

**"Semi-Supervised Synthesis of 7T MRI from 3T Using 3D FR-U-Net with Clinically-Relevant Anatomical Assessment"**  
*Richard Acs, Hanqi Zhuang* — Florida Atlantic University

This project investigates volumetric 7T MRI synthesis from 3T T1-weighted MRI using three deep learning models:

- **3D-FR-U-Net**: A 3D Multi-Scale Fusion Residual U-Net trained on paired 3T/7T data.
- **Semi-Supervised 3D-FR-U-Net**: An extension that incorporates unpaired 7T data through hybrid supervised-consistency loss.
- **Pix2Pix**: A 2D GAN-based model adapted for MRI synthesis with ResNet-based attention.

---

## 📁 Repository Contents

| File                                           | Description                                                                 |
|------------------------------------------------|-----------------------------------------------------------------------------|
| `3D_FRUNet_7T_Synthesis.ipynb`                 | Supervised 3D FR-U-Net for paired 3T-to-7T synthesis.                       |
| `Semi_Supervised_3D_FRUNet_7T_Synthesis.ipynb` | Semi-supervised FR-U-Net using unpaired 7T patches and consistency loss.    |
| `pix2pix_7T_synthesis.ipynb`                   | 2D slice-based pix2pix GAN adapted with ResNet attention blocks.            |

---

## ⚙️ Getting Started

### Requirements

Install dependencies:

```bash
pip install -r requirements.txt
```

You’ll need:

- Python 3.8+
- TensorFlow 2.x
- PyTorch
- TorchIO
- nibabel
- scikit-image
- scikit-learn
- matplotlib
- scipy
- requests
- numpy

### Usage

Each model is implemented in its own Jupyter notebook. You can run them using Jupyter Lab, Jupyter Notebook, or Google Colab:

- Open `3D_FRUNet_7T_Synthesis.ipynb` for supervised 3D training.
- Open `Semi_Supervised_3D_FRUNet_7T_Synthesis.ipynb` to experiment with semi-supervised learning.
- Open `pix2pix_7T_synthesis.ipynb` for 2D GAN-based synthesis.

---

## Data Statement

This research uses publicly available MRI datasets:

1. **Paired 3T/7T MRI Dataset**  
   - From Chen et al. (2023), includes 10 subjects with co-registered 3T and 7T scans.  
   - Source: [Scientific Data, 2023](https://doi.org/10.1038/s41597-023-02400-y)

2. **Unpaired 7T Dataset**  
   - From Li et al. (2024), includes 20 healthy subjects with high-quality T1-weighted 7T MRI.  
   - Source: [MICCAI 2024 Proceedings]

All scans were normalized to [0, 1], and split into overlapping patches of size 64×64×64 with a stride of 32 for training and inference.

---

## Contact

For questions or collaboration inquiries, please contact:  
**Richard Acs** — racs2019@fau.edu
