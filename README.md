# Gastroscope-tube-defect-dataset
Official dataset for the paper: "[SCFNet: A Structure-Aware and Contrast-Enhanced Collaborative Few-Shot Industrial Defect Detection Method]", submitted to Signal, Image and Video Processing.

# Gastroscope-tube Defect Dataset

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

Official dataset for the paper:
**"SCFNet: A Structure-Aware and Contrast-Enhanced Collaborative Few-Shot Industrial Defect Detection Method"**
*Submitted to Signal, Image and Video Processing*

## 📂 Dataset Overview
This dataset is constructed to evaluate few-shot defect detection methods on gastroscope tubes. To ensure compatibility with standard detection frameworks, the data is organized following the **PASCAL VOC** directory structure.

The dataset supports a two-stage training paradigm:
1.  **Base Training (Stage 1):** Uses the standard VOC structure (`VOC2012`) containing all base class data.
2.  **Few-Shot Fine-tuning (Stage 2):** Uses specific data splits (`few_shot_ann`) for $K$-shot adaptation tasks.

## 🗂️ Directory Structure
The repository is organized as follows:

```text
Gastroscope-tube-defect-dataset/
├── VOC2012/                     # [Stage 1 Data] Standard VOC-style dataset
│   ├── Annotations/             # XML annotation files for all images
│   ├── JPEGImages/              # Raw images of gastroscope tube defects
│   └── ImageSets/
│       └── Main/                # Train/Val splits for base training (e.g., train.txt, val.txt)
│
└── few_shot_ann/                # [Stage 2 Data] K-shot benchmark splits
    └── voc/
        ├── benchmark_1shot/     # Support sets for 1-shot experiments
        ├── benchmark_3shot/     # Support sets for 3-shot experiments
        ├── benchmark_5shot/     # Support sets for 5-shot experiments
        └── benchmark_10shot/    # Support sets for 10-shot experiments
            ├── box_10shot_black_train.txt
            ├── box_10shot_break_train.txt
            └── ...
