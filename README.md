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

## 📝 Detailed Usage Guide

### Stage 1: Base Training
For the initial pre-training stage (learning base classes), please point your dataloader to the `VOC2012` directory.
- **Images:** Located in `VOC2012/JPEGImages`.
- **Annotations:** Located in `VOC2012/Annotations` (standard XML format).
- **Splits:** Training and validation lists are provided in `VOC2012/ImageSets/Main/`.

### Stage 2: Few-Shot Fine-tuning
For the meta-learning or fine-tuning stage, use the split files provided in `few_shot_ann`.
- Each folder (e.g., `benchmark_10shot`) contains text files defining the support set for specific defect classes (e.g., black, break, stain).
- **Format:** The text files (e.g., `box_10shot_stain_train.txt`) contain the filenames of the specific samples selected for the K-shot episodes.
- **Note:** The actual images corresponding to these lists are stored in the main `VOC2012/JPEGImages` folder.

## ⚙️ Customization
This dataset mimics the PASCAL VOC 2012 structure, allowing it to be easily integrated into popular detection codebases (e.g., MMDetection, Detectron2) with minimal modification.

## 🔗 Citation
If you use this dataset in your research, please cite our paper:

```bibtex
@article{Hu2026SCFNet,
  title={SCFNet: A Structure-Aware and Contrast-Enhanced Collaborative Few-Shot Industrial Defect Detection Method},
  author={{Hu, Shifei and Gu, Minming and Li, Xinyu},
  journal={Signal, Image and Video Processing},
  year={2026},
  note={Under Review}
}
## 📧 Contact
For any questions regarding the dataset, please contact:
* **Shifei Hu**: `2023220705009@mails.zstu.edu.cn`
* **Minming Gu** (Corresponding Author): `guminming@zstu.edu.cn`
