# natural-language-based-scene-localisation
: Scene Localization in Dense Images via Natural Language Queries using Yolo World and DBSCAN
YOLO-World Object Search & Grouping with DBSCAN

Overview

This project implements open-vocabulary object detection using the YOLO-World model, combined with DBSCAN clustering to group detected objects based on spatial proximity.

The system allows a user to:

Search for any object in an image using a natural language prompt.

Detect all instances of that object without retraining the model.

Group detected objects into clusters based on their location.

Generate a visual summary with bounding boxes, cluster labels, and object counts.

Features

Open-Vocabulary Detection – Detects objects based on a user-provided text prompt.

Zero-Shot Capability – Can detect unseen categories without extra training.

Spatial Grouping – Uses DBSCAN clustering to identify and group related objects.

Visualization – Draws bounding boxes and cluster IDs directly on the image.

Group Summary – Outputs the number of objects per cluster.

Technologies Used
YOLO-World

Accepts custom text prompts for detection.

Works across multiple scales (nano to extra-large).

Supports zero-shot inference.

DBSCAN Clustering

Density-based algorithm for grouping detections.

Works with arbitrary shapes.

No need to specify the number of clusters in advance.

System Workflow

Image Upload – Upload an image in Colab or load from disk.

Model Loading – Load YOLO-World (yolov8m-worldv2.pt).

Prompt Input – User enters the object name to detect.

Object Detection – YOLO-World detects instances matching the prompt.

Clustering – DBSCAN groups detected objects by spatial proximity.

Visualization – Annotated image is displayed with group labels.

Output Summary – Number of objects per cluster is printed.

Installation

To run this project in Colab, install dependencies:

pip install ultralytics transformers sentence-transformers opencv-python matplotlib scikit-learn

Usage

Open in Colab using the badge above.

Upload your image or modify the code to load from disk.

Enter your search prompt (e.g., "person", "car", "apple").

View detected and grouped objects in the annotated output image.

Example Output

(Add a sample before/after image here once the repo is public)

Limitations

Clustering performance depends on DBSCAN parameters (eps and min_samples).

Overlapping objects might be grouped incorrectly in very dense scenes.

Future Work

Integrating multi-class detection for multiple prompts in one pass.

Adding confidence-based filtering for more accurate grouping.

Exploring alternative clustering algorithms (e.g., MeanShift, Agglomerative).
