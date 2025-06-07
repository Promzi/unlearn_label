# Multi-Label Unlearning for Responsible Facial Systems

**Prommy Sultana Hossain**, **Emanuela Marasco**, **Jessica Lin**, **Michael King**  
George Mason University · Florida Institute of Technology

📌 **Official Paper (ECML PKDD 2025)**  
🔗 [Read the paper here](https://)  
📄 Accepted to ECML PKDD 2025 – Research Track

---

## 📂 Repository Overview

This repository contains the **official implementation** of our ECML PKDD 2025 paper, _"I Forgot About You! Exploring Multi-Label Unlearning (MLU) for Responsible Facial Systems."_ It includes:

- 🧪 Codebase for **Weight Filtering** and **Weight Pruning** methods  
- 📊 Reproduction scripts for all **experiments and privacy metrics**  
- 🗂 Pretrained **best checkpoint** from our main experiments  
- 📦 Dataset loader and configuration for CelebA, MUFAC, VGGFace2, CIFAR-10, MNIST, and SVHN  
- 📜 Extended **Appendix (B–F)**: theoretical proofs, algorithm pseudocode, and ethical analysis not included in the ECMLPKDD main paper

---

## 🔍 Reproducing Results

To reproduce the results:

```bash
git clone https://github.com/Promzi/unlearn_label.git
cd unlearn_label
pip install -r requirements.txt
python run_experiment.py --method WP --dataset CelebA --label Gender


**## Supplementary Material (Beyond Main Paper)**












