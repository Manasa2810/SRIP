# SRIP

## Data Exploration and Understanding

### Dataset Statistics
- Compute the number of instances of solar panels in the dataset.
- Compute and show the value counts of labels per image.
- Calculate statistics of the area of solar panels (in meters).
- Identify the method used to compute the area.
- Compute mean and standard deviation of area.
- Plot a histogram of the areas and analyze observations.

## Implementing Fundamental Functions

### IoU (Intersection over Union)
- Implement IoU computation using the `shapely` library for axis-aligned bounding boxes in YOLO format.
- Compare results with IoU computed using the `supervision` library.

### Average Precision (AP) Computation
- Implement AP using:
  - Pascal VOC 11-point interpolation method
  - COCO 101-point interpolation method
  - Area under Precision-Recall Curve (AP) method
- Generate 10 random images (100x100), 10 ground truth boxes (20x20), and 10 predicted boxes (20x20).
- Compute AP50 using all three methods and compare results.

## Model Building and Evaluation

### Training and Validation
- Split data into 80-20 train-test split, with 10% of training data as validation.
- Train an object detection model using Ultralytics YOLO.
- Ensure validation loss convergence.

### Predictions and Visualization
- Predict solar panels using the trained model.
- Visualize ground truth and predicted bounding boxes on 3-4 random test samples.
- Use distinct color schemes for ground truth and predicted labels.

### Metrics Computation
- Compute mAP50 using the `supervision` library and compare it with manual implementation.
- Create a table of Precision, Recall, and F1-score for IoU thresholds `[0.1, 0.3, 0.5, 0.7, 0.9]` and confidence thresholds `[0.1, 0.3, 0.5, 0.7, 0.9]`.
- Use `supervision.metrics.ConfusionMatrix` to derive TP, FP, and FN for metric computations.
