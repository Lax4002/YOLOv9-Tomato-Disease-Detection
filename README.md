# YOLOv9 Tomato Leaf Disease Detection

A course project evaluating **YOLOv9c** for multi-class tomato leaf disease detection using transfer learning.

The experiment compares five initial learning rates while holding the remaining training configuration constant. The goal is to study learning-rate sensitivity and identify a configuration that gives strong validation performance.

## Reported Results

| Learning Rate | mAP@0.5 | mAP@0.5:0.95 | Precision | Recall |
|---:|---:|---:|---:|---:|
| 0.1 | 0.0008 | 0.0002 | 0.0006 | 0.1377 |
| 0.01 | 0.7593 | 0.4907 | 0.8228 | 0.6318 |
| **0.001** | **0.7674** | **0.5145** | 0.6994 | **0.7812** |
| 0.0001 | 0.7518 | 0.4887 | 0.8227 | 0.6788 |
| 0.00001 | 0.7553 | 0.4992 | 0.7911 | 0.6768 |

The best reported configuration used an initial learning rate of **0.001**.

## Model and Training Setup

- Architecture: YOLOv9c
- Framework: Ultralytics
- Pre-trained weights: COCO
- Optimizer: AdamW
- Epochs: 100
- Batch size: 16
- Input resolution: 640 × 640
- Augmentations: Mosaic, MixUp and CutMix

## Disease Classes

The project evaluates seven classes:

- Bacterial Spot
- Early Blight
- Healthy
- Late Blight
- Leaf Mold
- Target Spot
- Black Spot

## Repository Structure

```text
.
├── notebooks/
│   └── YOLOv9_Tomato_Disease.ipynb
├── report/
│   └── YOLOv9_TomatoDisease_Report.pdf
├── data/
│   └── README.md
├── results/
├── requirements.txt
├── .gitignore
└── README.md
```

## Setup

Create a Python environment and install the dependencies:

```bash
pip install -r requirements.txt
```

Download the tomato leaf disease dataset described in `data/README.md`, then place the extracted YOLO-format dataset in a `dataset/` directory at the repository root.

The expected structure is:

```text
dataset/
├── data.yaml
├── train/
├── valid/
└── test/
```

Open the notebook in Jupyter or Google Colab and run the cells in order. If the project files are stored somewhere else, set the `MCE531_PROJECT_ROOT` environment variable before running the notebook.

## Reproducibility Notes

The original work was developed in Google Colab. The public notebook has been cleaned so paths are based on a configurable project root instead of a personal Google Drive path.

Training outputs and model weights are intentionally excluded from Git by default because YOLO runs and `.pt` checkpoints can become large. Re-run the notebook to regenerate them, or selectively add final artifacts if required.

## Project Report

The submitted project report is included in `report/Group5_YOLOv9_TomatoDisease_Report.pdf`.

## Academic Context

This repository contains coursework for MCE 531 and is published primarily for portfolio, learning and reproducibility purposes.
