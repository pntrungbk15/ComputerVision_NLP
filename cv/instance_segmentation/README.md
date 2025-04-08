# Instance Segmentation
This repository is a curated and customized collection of deep learning applications for instance segmentation.
As a Computer Vision researcher, I’ve redesigned the model and data structures for clarity and flexibility, making it ideal for research and prototyping.

## Info
+ The repository includes YOLO versions from YOLOv3_seg to YOLOv11_seg and YOLOX_seg.
+ The dataset supports data processing in the following formats: VOC, COCO, YOLO.
+ Dataset augmentation options include YOLO-style augmentation (yolo_aug) and SSD-style augmentation (ssd_aug).
+ Model training is monitored using Weights & Biases (wandb), making it easier to observe overfitting or underfitting behaviors.
+ Data augmentation at multiple image sizes, configurable via YAML, helps models generalize better and improves overall performance.
+ Model structure is refactored into a clear pipeline: `backbone -> neck -> head -> predict`, making the code more readable and easier to modify.
+ Multiple bounding box loss functions from various papers are supported and can be selected in the config file, such as: `iou`, `giou`, `diou`, `siou`, `eiou`, `mdpiou`, `piou` and `piou2`.
+ Model performance evaluation is available using mAP metrics and confusion matrix analysis.
+ After training, models can be exported to ONNX format for accelerated inference on various deployment platforms.

## Research Models
![](assets/models.jpg)

## Structure
![](assets/code_structure.jpg)

## Demo
Dataset Augmentation:
+ SSD Augmentation
![](assets/ssd_aug.gif)

+ Yolo Augmentation
![](assets/yolo_aug.gif)

Example YOLOX_Seg Config File

![](assets/yoloX_Seg.jpg)

Example YOLOX_Seg Model Structure

🔧 See full [YOLOX_Seg config example here](assets/coco.yaml)

Model Performance Evaluation
+ mAP metric:
<p align='center'>
    <img width='1500' src='assets/mAP.jpg'>
</p>

## Demo

### Train
```bash
python main.py --yaml_config configs/yolox_seg/coco.yaml
```

### Test .pth & .onnx Model
```bash
voila "test_model.ipynb" --port 8866 --Voila.ip 127.0.0.1 --show_tracebacks=True
```

## Installation

To use these applications, you need to have Python and several Python packages installed. To install the required packages, use the following command:
```bash
pip install -r requirements.txt"
```