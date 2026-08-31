---
title: Waymo Object Detection with Transfer Learning
date: 2025-12-12
summary: Fine-tuning and comparing YOLOv8 and Faster R-CNN for vehicle and pedestrian detection on the Waymo Open Dataset.
tags:
  - Autonomous Driving
  - Object Detection
  - Transfer Learning
  - YOLOv8
  - Faster R-CNN
  - PyTorch
image:
  alt_text: Vehicle and pedestrian detection on a Waymo Open Dataset road scene
---

An end-to-end computer vision pipeline for detecting vehicles and pedestrians in camera images from the Waymo Open Dataset. I used transfer learning to adapt COCO-pretrained object detectors to autonomous-driving scenes and compared a real-time, one-stage detector with a higher-accuracy, two-stage architecture.

## Approach

- Decoded Waymo camera images and 2D bounding-box annotations from Parquet files.
- Converted the annotations into YOLO and COCO formats.
- Fine-tuned YOLOv8n, YOLOv8s, and Faster R-CNN with a ResNet50-FPN backbone for 30 epochs.
- Froze the pretrained backbones and trained the detection heads to reduce training cost and limit overfitting on the small dataset.
- Split the data by driving segment rather than individual frames, preventing visually similar frames from leaking between the training and validation sets.
- Evaluated each model using standard COCO mean average precision metrics.

## Results

| Model | `mAP@0.50` | `mAP@0.50:0.95` |
| --- | ---: | ---: |
| YOLOv8n | 0.338 | 0.173 |
| YOLOv8s | 0.435 | 0.235 |
| Faster R-CNN ResNet50-FPN | **0.518** | **0.269** |

Fine-tuning increased YOLOv8n's `mAP@0.50` from 0.045 to 0.338 and YOLOv8s's from 0.074 to 0.435. Faster R-CNN achieved the best overall detection accuracy, while YOLOv8 offered the architecture better suited to real-time inference.

Vehicle detection was stronger than pedestrian detection because the data contained roughly seven times more vehicles than people. Small, distant pedestrians were the main failure case, highlighting the effects of class imbalance, object scale, and training on only one Waymo segment.

## Technologies

Python, PyTorch, Torchvision, Ultralytics YOLOv8, OpenCV, Pandas, NumPy, pycocotools, and Google Colab with an NVIDIA Tesla T4 GPU.

[View the project and training notebook on GitHub](https://github.com/Mayowa2024/waymo-object-detection-transfer-learning)
