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
  
---

## Challenges Unique to Multi-Label Unlearning
Multi-label unlearning introduces new difficulties not present in the single-label case. Key challenges include:

- **Partial label deletion**: In MLC each example can have multiple labels. Unlearning may require removing only some labels of an example while keeping the rest. This means the example remains in training (since it still has valid labels), and we must delete part of its label information. For instance, if an image is labeled {Person=A, Glasses=Yes, Smile=Yes} and we wish to forget the “Glasses” label, we cannot simply drop the image (we still want to retain Person and Smile). Instead, we must remove the influence of the “Glasses” annotation while preserving the signals for “Person” and “Smile.” Designing updates that excise one label’s effect without harming the others is non-trivial.

- **Entangled representations**: Most multi-label models share parameters (for example, common hidden layers feeding into multiple output heads). Consequently, the internal representations are entangled across labels. Features that help predict one label often also contribute to others. Adjusting model weights to forget a particular label thus risks degrading representations used by other labels. Unlearning must carefully disentangle these shared features: naively zeroing out weights could hurt all labels, whereas more targeted updates must isolate only the unwanted label’s contributions.

- **Shared label dependencies**: Real-world labels often exhibit statistical dependencies. For example, two attributes may frequently co-occur or be conditionally related. If label $i$ and label $j$ are strongly correlated, a model learns shared features for both. Removing label $i$ in such cases can inadvertently confuse the model about label $j$. In practice, this means that forgetting one label can degrade performance on its correlated partners. As a result, strong inter-label dependencies make unlearning harder: methods must account for these correlations to avoid “unlearning spillover” into the remaining labels.

---

# Appendix Material (Beyond Main Paper)
Due to ECML PKDD formatting constraints, theoretical guarantees and algorithmic details have been placed in the Appendix.pdf that includes:

📐 **Appendix A:** Theoretical privacy proofs for Weight Filtering and Pruning

🔐 **Appendix B:** Ethical considerations and privacy compliance (GDPR/CCPA)

🧪 **Appendix c:** Hardware specs, environment setup, and implementation details

📈 **Appendix D:** Full result tables and figures not shown in the paper

📉 **Appendix E:** Runtime performance and entropy distribution analysis

These sections are cited in the main paper as references to the GitHub repository.

--

# Dataset and Baseline Source Code

We provide loading and preprocessing code for the following datasets:

🧑‍🎓 CelebA (multi-label attributes)

🧠 MUFAC (East Asian faces, age labels)

🧸 CIFAR-10, 🧮 MNIST, 🧑 SVHN (baseline SLC tests)

Dataset download links and preparation scripts are in data/README.md.

Also includes reimplementation of baselines: SCRUB, SalUN, UNSIR, CF-k.

--

## 🔍 Reproducing Results

To reproduce the results:

```bash
git clone https://github.com/Promzi/unlearn_label.git
cd unlearn_label
pip install -r requirements.txt
python run_experiment.py --method WP --dataset CelebA --label Gender
```  


## 💡 Citation

If you use this code, please cite:

```bibtex
@inproceedings{hossain2025mlu,
  author = {Hossain, Prommy Sultana et al.},
  title = {“I Forgot About You!”: Exploring Multi-Label Unlearning for Responsible Facial Systems},
  booktitle = {},
  year = {2025}
}
```

# Contact

Questions or issues? Open an issue or email: **phossai [at] gmu.edu**





