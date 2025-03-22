🐶🧍 Pet-Person Object Detection with YOLO

This project explores object detection for the classes Person and Pet (cats and dogs) using a YOLO model trained on a dataset created without manual annotation.


🔍 Problem

Creating high-quality labeled datasets for object detection is labor-intensive. This project solves that by automatically generating annotations using the Florence-2 model on the Flickr image dataset.


🎯 Objective

Detect persons and pets in real images.

Build a balanced and robust dataset using minimal manual intervention.

Train a lightweight YOLO model suitable for real-time applications.


🖼️ Dataset Creation & Preprocessing

Image Source: Flickr dataset.

Annotation: Florence-2 generated labels.

Image size: Resized to 512x512 for efficiency.

Keyword filtering: Selected images via comment keywords like "dog", "cat", "man", "woman", etc.

Balancing strategy:

Pets: Prioritized cats and puppies to offset dog overrepresentation.

Persons: Balanced across age and gender (men, women, boys, girls).

Duplicates filtered based on comments and image IDs.


⚠️ Florence-2 Challenges & Solutions

Label inconsistency → Unified to single classes: "person", "pet".

Misclassifications → Filtered out incorrect labels and added more images to compensate.


🔧 Training & Augmentations

Used YOLO due to:

Real-time detection speed

Good accuracy

Built-in augmentations

Easy customization


Training Results:

10 Epochs, No Augmentations:
Precision: 0.836, Recall: 0.692, mAP@0.5: 0.803, mAP@0.5-0.95: 0.601

30 Epochs, No Augmentations:
Precision: 0.920, Recall: 0.831, mAP@0.5: 0.918, mAP@0.5-0.95: 0.773

50 Epochs, With Augmentations:
Precision: 0.929, Recall: 0.894, mAP@0.5: 0.946, mAP@0.5-0.95: 0.781


🧪 Potential Enhancements

Test Time Augmentations (TTA): Evaluate robustness and detect weaknesses in model/data.

Ensembles: Improve performance and analyze dataset biases.

Data expansion: Add more cat images and diverse sources to improve class balance and generalization.

Architectures: Try YOLOv9, YOLOv10, etc.


💡 Lessons Learned

Data diversity and balance are critical.

Careful filtering is needed when using automated labeling.

Augmentations significantly improve generalization.

Thorough documentation and early debugging save time.
