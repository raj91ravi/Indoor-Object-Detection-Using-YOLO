# Indoor Object Detection Using YOLOv8

**Comparative analysis of YOLOv8 models for indoor object detection using the HomeObjects-3K dataset.**

## Overview

This repository explores indoor object detection with the YOLOv8 family of object detectors. The project focuses on comparing model variants on the **HomeObjects-3K** dataset to study detection performance and the trade-off between accuracy and computational requirements.

The main implementation is provided as a Jupyter Notebook: [`Indoor object recognition YOLO.ipynb`](./Indoor%20object%20recognition%20YOLO.ipynb).

## Objectives

- Explore object detection in indoor environments using YOLOv8.
- Train or evaluate YOLOv8 variants on the HomeObjects-3K dataset, as configured in the notebook.
- Compare models using available detection metrics and qualitative predictions.
- Investigate accuracy–efficiency trade-offs relevant to indoor robotic perception.

## Dataset

The project uses **HomeObjects-3K**, an indoor-object detection dataset. Obtain the dataset from its authorized distribution source and verify the license and annotation format before use.

For Ultralytics YOLO training, the dataset typically needs images, YOLO-format labels, and a dataset YAML file identifying train/validation/test paths and class names. Adapt these paths to the dataset layout used in the notebook.

> The dataset is not included in this repository's publicly visible root files. Check the notebook for the exact expected paths, classes, and preprocessing.

## Methodology

1. **Prepare data:** Load the HomeObjects-3K images and bounding-box annotations.
2. **Configure models:** Select the YOLOv8 model variants and training settings defined in the notebook.
3. **Train / validate:** Run the notebook cells for model training or evaluation.
4. **Compare:** Examine precision, recall, mean average precision (mAP), and inference efficiency where recorded.
5. **Visualize:** Inspect predicted bounding boxes and class labels on indoor images.

### Evaluation metrics

| Metric | Interpretation |
| --- | --- |
| Precision | Fraction of predicted detections that are correct |
| Recall | Fraction of ground-truth objects detected |
| mAP@0.5 | Mean average precision at IoU threshold 0.5 |
| mAP@0.5:0.95 | Mean AP averaged across IoU thresholds from 0.5 to 0.95 |
| Inference time / FPS | Computational efficiency, when measured on comparable hardware |

**Note:** This README does not claim numerical results or a winning model because those outcomes must be verified against the notebook outputs and experimental settings.

## Repository structure

```text
Indoor-Object-Detection-Using-YOLO/
├── Indoor object recognition YOLO.ipynb
└── README.md
```

## Installation

Use Python 3.9+ in a virtual environment. Install Jupyter and the Ultralytics package; install any additional dependencies imported by the notebook.

```bash
git clone https://github.com/raj91ravi/Indoor-Object-Detection-Using-YOLO.git
cd Indoor-Object-Detection-Using-YOLO
python -m venv .venv
```

Activate the environment:

**Windows**
```powershell
.venv\Scripts\activate
```

**macOS / Linux**
```bash
source .venv/bin/activate
```

Install core packages:

```bash
python -m pip install --upgrade pip
pip install ultralytics jupyter matplotlib pandas
```

For GPU acceleration, install a compatible PyTorch build according to the [official PyTorch instructions](https://pytorch.org/get-started/locally/).

## Run the notebook

```bash
jupyter notebook "Indoor object recognition YOLO.ipynb"
```

Before running all cells:

1. Download and prepare the HomeObjects-3K dataset.
2. Update dataset paths and any YAML configuration to match your environment.
3. Check model checkpoint names and training hyperparameters in the notebook.
4. Select CPU or GPU execution as available.
5. Run the cells sequentially and inspect the saved predictions and evaluation outputs.

## Reproducibility checklist

For a fair comparison, document the dataset split, model variants, pretrained weights, image size, epochs, batch size, random seed, hardware, software versions, and evaluation protocol. Compare inference speed only under matched conditions.

## Applications

Indoor object detection can support assistive robotics, service robots, smart-home monitoring, inventory assistance, and visual scene understanding. These are potential application areas; deployment performance has not been established by this repository alone.

## Limitations and future work

- Validate generalization across different indoor scenes, lighting conditions, and occlusions.
- Report per-class detection metrics and failure cases.
- Benchmark runtime and memory on deployment hardware.
- Package dataset configuration and dependencies for reproducibility.
- Explore real-time robotic perception after testing reliability and safety.

## Author

**Ravi Raj**  
[GitHub: @raj91ravi](https://github.com/raj91ravi)

## Citation

If you use this repository in academic work, please link to the repository and identify the commit or release used. Add a formal paper citation here if an associated publication becomes available.

## License

No license is specified here. Please consult the repository's license status before redistributing or reusing code; the author can add a `LICENSE` file to clarify permissions.
