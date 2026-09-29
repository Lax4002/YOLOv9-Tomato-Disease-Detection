# Dataset

This project uses a tomato leaf disease detection dataset distributed through Kaggle and prepared in YOLO format.

Expected classes:
- Bacterial Spot
- Early Blight
- Healthy
- Late Blight
- Leaf Mold
- Target Spot
- Black Spot

The original coursework report identifies the dataset as **Tomato Leaf Disease Detection** on Kaggle.

For reproducibility, download the dataset from its source and extract it to `dataset/` at the repository root. The repository does not redistribute the image dataset.

Expected layout:

```text
dataset/
├── data.yaml
├── train/
├── valid/
└── test/
```

Verify that paths inside `data.yaml` match your local directory structure before training.
