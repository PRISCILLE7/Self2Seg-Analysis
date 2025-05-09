# Scientific Paper Analysis — Self2Seg

This repository presents a structured and critical review of the paper **"Self2Seg: Single-Image Self-Supervised Joint Segmentation and Denoising"**, as part of the *Literature Review and Case Study* module in the Master's program SIM at IFI (Vietnam National University).

 Paper: [arXiv:2309.10511 – Self2Seg](https://arxiv.org/abs/2309.10511)  
 Supervisor: Dr. Ho Tuong Vinh  
 Author: Priscille Ebwala (SIM Cohort P27)

---

##  Project Objective

To conduct a critical and structured analysis of the Self2Seg paper, which introduces a **self-supervised method** that jointly performs **image denoising and segmentation** from a single image without requiring ground-truth annotations.

---

## Summary of the Analysis

### I. Introduction

- Identifies challenges in traditional image processing pipelines.
- Motivates the need for combined segmentation and denoising in noisy and label-scarce domains (e.g., biomedical imaging).

### II. Problem Statement & Goals

- How can one denoise and segment an image with **no annotations**?
- Goal: propose a **robust and unified framework** that leverages the synergy between both tasks to improve visual quality and segmentation accuracy in noisy conditions.

### III. Related Work

- **Variational methods** (e.g., Chan-Vese): effective but require preprocessing and are not annotation-free.
- **Self-supervised denoising** (e.g., Noise2Self, Noise2Void): focus on image quality, ignore segmentation.
- **Hybrid approaches** (e.g., DenoiSeg): combine tasks, but still rely on partial supervision or masks.

### IV. Proposed Method: Self2Seg

- Two **expert denoisers**: one for foreground, one for background.
- Joint optimization via a **shared energy function**.
- Strong interaction between tasks:
  - Segmentation guides where to denoise.
  - Denoising improves segmentation clarity.
- Iterative learning with **ADAM optimizer** for networks and **Chambolle-Pock** for segmentation updates.

### V. Implementation & Experiments

- Dataset: **DSB2018** (nuclei images with synthetic Gaussian noise).
- Metrics: **PSNR**, **SSIM**, **Dice score**.
- Comparisons:
  - Self2Seg outperforms Chan-Vese, DenoiSeg, and Noise2Fast, especially at high noise levels.
- Key findings:
  - Robust to low and high noise.
  - Scalable to more than two classes.
  - Stronger segmentation with multi-expert design.

### VI. Related Papers Discussed

- BEVContrast: self-supervised segmentation for LiDAR.
- Multi-Task Self-Supervised Learning (Seg + Depth).
- Source Identification for medical dense prediction tasks.

---

##  Personal Critical Review

###  Strengths

- Fully self-supervised — no manual labels needed.
- Strong **coupling** of tasks improves both outputs.
- Excellent **robustness to noise**.
- Effective even under limited data conditions.

###  Limitations

- Performance is **sensitive to hyperparameters**.
- Needs **domain adaptation** for general use (e.g., non-biomedical).
- Lacks comparisons to **state-of-the-art transformer-based models**.

###  Future Directions

- Test on **real-world non-medical datasets**.
- Use **AutoML** to automate hyperparameter tuning.
- Combine with **contrastive or multi-task learning** for improved representations.

---

## Files Included

- `analyse_self2seg.pdf` — full critical review in French.
- `articleFrancais.tex` / `articleAnglais.tex` — LaTeX source versions.

---

## References

- Gruber et al. (2024). *Self2Seg: Single-Image Self-Supervised Joint Segmentation and Denoising*. arXiv:2309.10511.
- Noise2Self, DenoiSeg, BEVContrast, Multi-Task SSL, Source Identification.

---

> This analysis was conducted for educational purposes and aims to enhance scientific reading, structured synthesis, and critical evaluation skills in the field of self-supervised learning and computer vision.
