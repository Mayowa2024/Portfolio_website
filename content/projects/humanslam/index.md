---
title: HumanSLAM
date: 2026-08-01
summary: A human-inspired semantic place-recognition framework that augments ORB-SLAM3 for robust, low-latency localisation under perceptual change.
tags:
  - Research
  - SLAM
  - Visual Place Recognition
  - Semantic Perception
  - Computer Vision
  - ROS 2
  - ORB-SLAM3
categories:
  - Research
image:
  alt_text: HumanSLAM semantic place-recognition system overview
---

HumanSLAM is an ongoing research project investigating whether structured, human-inspired semantic reasoning can improve visual place recognition without sacrificing the latency required by online SLAM. It augments ORB-SLAM3 with a semantic retrieval layer designed to recognise previously visited places despite illumination, weather, blur, viewpoint change, and visually repetitive environments.

The central design principle is a separation of responsibilities: HumanSLAM proposes **where the camera may have been**, while ORB-SLAM3 remains responsible for geometric verification, pose estimation, relocalisation, loop closure, and map fusion.

## Motivation

Conventional visual SLAM relies heavily on local appearance and geometric features. These representations can fail when the same place looks different because of environmental change, or when different places look deceptively similar—for example, on separate floors of a multi-storey car park. HumanSLAM introduces higher-level contextual reasoning to produce more reliable place hypotheses before geometric verification.

## Approach

HumanSLAM builds a semantic retrieval index over existing ORB-SLAM3 keyframes. It combines scene-level context with structured semantic cues to rank previously observed locations, then passes the strongest candidates to ORB-SLAM3's geometric backend for physical verification.

This design adds semantic understanding without replacing the established SLAM geometry. The implementation is engineered for online operation, with attention to retrieval quality, inference latency, and the amount of work passed to downstream verification.

## Evaluation

The research evaluates place recognition separately from its downstream effect on the complete SLAM system. Experiments cover:

- **KITTI Odometry:** real road sequences with controlled motion blur and illumination degradation.
- **CARLA:** repeated routes under controlled night, fog, rain, glare, and combined weather changes.
- **4Seasons:** natural seasonal variation and perceptual aliasing in a structurally repetitive multi-level garage.

The evaluation considers recognition robustness, runtime performance, geometric-verification workload, tracking behaviour, and trajectory quality across both real and simulated environments.

## Preliminary Findings

Early experiments are encouraging, particularly under substantial appearance change and in structurally repetitive environments. Full methodology and quantitative results will be released with the paper after the evaluation and review process is complete.

## Current Status

The HumanSLAM framework, ORB-SLAM3 integration, controlled-degradation benchmarks, and comparative VPR/SLAM experiments are implemented. The paper is currently in preparation, and real-time vehicle evaluation remains in progress.

## Technologies

ORB-SLAM3, ROS 2 Humble, semantic perception, GPU-accelerated inference, TensorRT, CUDA, PyTorch, KITTI, CARLA, and 4Seasons.
