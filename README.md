# SRIP
Data Exploration and Understanding
Dataset statistics 
How many instances of solar panels are present in the dataset?
Compute and show the value counts of labels per image. E.g., X images have 0 labels, Y images have 1 label, … and so on.

Calculate the statistics of the area of solar panels in meters (Read label readme carefully for this question)
What method was used to compute the area (in meters) for a single instance?
What is the mean area and standard deviation?
Plot the histogram of areas. What do you observe?
Implementing the Fundamental Functions
Write a function to compute IoU (Intersection over Union) https://pyimagesearch.com/2016/11/07/intersection-over-union-iou-for-object-detection/ between two axis-aligned bounding boxes specified in the Ultralytics YOLO format. You MUST use the shapely library [https://pypi.org/project/shapely/] and its functionalities to write your function. Show that your function provides the same or similar answer as IoU computed using `supervision` library 


Write a function to compute Average Precision (AP) 
Use Pascal VOC 11 point interpolation method to implement the function 
Use COCO 101-point interpolation method to implement the function

Use Area under Precision-Recall Curve (AP) method to implement the function 

Randomly generate 10 images of size 100x100. Randomly generate 10 ground truth boxes of size 20x20 and 10 predicted boxes of size 20x20 in each image. Assume there is only one class of objects. Compare the AP50 (Average Precision at IoU 0.5) computed by 3 of your methods
Model building and evaluation 

Split the data into 80-20 train-test split. Use 10% of training data as validation.
Use any model from Ultralytics like YOLO to train the object detection model. Show that validation loss is converged. 

Predict solar panels using the trained model. Visualize the ground truth and predicted bounding boxes on 3-4 random samples from the test dataset. Use appropriate color schemes to differentiate between ground truth and predicted labels. 

Use supervision.metrics functionality from supervision library to compute the following metrics.
Compute mAP50 with supervision and compare with your implementation. What do you observe 

Create a table of Precision, Recall and F1-scores where rows are IoU thresholds [0.1, 0.3, 0.5, 0.7, 0.9] and columns are confidence thresholds [0.1, 0.3, 0.5, 0.7, 0.9] (Hint use supervision.metrics.ConfusionMatrix to get the confusion matrix and get TP, FP and FN from it to compute the P, R and F-1) 
