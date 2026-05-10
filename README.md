# RAED-VP: Risk-Aware Adaptive Event-Driven Vehicle Perception

RAED-VP is a risk-aware adaptive event-driven framework for efficient vehicle perception in urban traffic videos.

The main idea is to reduce redundant YOLO inference by processing only the most informative frames instead of running detection on every video frame.

---

## Overview

Urban traffic videos often contain many similar consecutive frames. Processing every frame with a deep learning detector can be computationally expensive.

RAED-VP addresses this problem by using event-driven and adaptive frame selection strategies. The system decides whether to run YOLO or skip a frame based on lightweight risk indicators.

---

## Main Idea

Instead of using continuous inference:

```text
Frame 1 → YOLO
Frame 2 → YOLO
Frame 3 → YOLO
Frame 4 → YOLO
```

RAED-VP uses selective inference:
```text
Frame 1 → YOLO
Frame 2 → Skip
Frame 3 → Skip
Frame 4 → YOLO
```

This reduces computation while keeping detection performance close to continuous processing.

## Compared Strategies

The project compares three strategies:

Continuous Inference : YOLO is applied to every frame.
Event-Driven Inference: YOLO is triggered only when a significant scene change is detected.
Adaptive RAED-VP: YOLO is triggered according to a risk-aware score based on scene variation, vehicle density, and detector uncertainty.
Dataset

The experiments are conducted on the UA-DETRAC traffic video dataset.

The task focuses on vehicle detection in urban traffic scenes.

## Model

A YOLO-based detector is used as the perception backbone.

The contribution of this project is not the YOLO model itself, but the adaptive frame-processing strategy used to reduce unnecessary inference.
