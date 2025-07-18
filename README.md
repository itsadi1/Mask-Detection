# Face Mask Detection Using VGG16

## Project Overview

This project applies the **VGG16** convolutional neural network for automated face mask detection. It robustly classifies images of faces into two categories: **with mask** and **without mask**. The goal is to provide a fast and accurate detection framework suitable for both static images and real-time video feed scenarios.

---

## Approach

- **Transfer Learning:** Utilizes a pre-trained VGG16 model for feature extraction and fine-tunes only the final layers for the mask detection task.
- **Binary Classification:** Predicts whether a detected face is wearing a mask or not.
- **Image Preprocessing:** All input images are resized to 224x224 pixels to comply with VGG16 input dimensions.
- **Data Augmentation:** Incorporates such techniques as rotation, flipping, scaling, and brightness adjustment to make the model resilient to real-world variability.
- **Face Detection:** Faces are localized in input images (e.g., using Haar cascade classifiers) before classification.

---

## Model Highlights

| Feature                | Description                                         |
|------------------------|----------------------------------------------------|
| Architecture           | VGG16 (16-layer deep CNN)                          |
| Transfer Learning      | Pre-trained on ImageNet; classifier retrained      |
| Dataset Compatibility  | Works with both small and medium-sized datasets    |
| Accuracy (Tested)      | Up to **85.57%**   |
| Output                 | Probability of mask presence per face              |
| Application            | Real-time video, CCTV, static image analysis       |

---

## Typical Workflow

1. **Dataset Preparation:**  
   Collect and label images under two categories—`with_mask` and `without_mask`.

2. **Data Augmentation:**  
   Apply random transformations to each image to introduce variation.

3. **Preprocessing:**  
   - Detect and crop face regions
   - Resize images to 224x224
   - Normalize pixel values

4. **Model Training:**  
   - Load VGG16 (pre-trained)
   - Replace top layer(s) with binary classifier
   - Freeze base layers, train the classifier head on your data

5. **Inference:**  
   - Detect faces in new images or frames
   - Preprocess as above
   - Predict mask presence for each face

6. **Deployment:**  
   Integrate the model in video pipelines, CCTVs, or access control systems for live compliance monitoring.

---

## Applications

- **Public Surveillance:** Automated mask monitoring in stations, airports, malls, and workplaces.
- **Access Control:** Integrate with turnstiles or entry gates.
- **Retail & Service:** Monitor staff and customer compliance.

---

## Key Benefits

- **High Accuracy:** Strong transfer learning performance, even with limited data.
- **Efficient:** No need to train a deep network from scratch.
- **Adaptable:** Easily extensible to other binary or multi-class image classification tasks.
- **Real-Time Ready:** Suitable for integration with live video streams.

---

_This project provides a clear, reliable, and scalable solution for mask detection using state-of-the-art deep learning methods. For commercial use or research, the modular approach and well-documented workflow ensure fast adaptation for your specific requirements._
