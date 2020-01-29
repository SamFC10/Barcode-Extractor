# Barcode Extractor using OpenCV

Pipeline to extract barcode number from images using OpenCV functions. A simple k-neighbours classifier was trained to detect the numbers present in the barcode.

### Image pre-processing
- convert image to grayscale
- create structure element for extracting vertical lines through morphology operations. (using cv2.getStructuringElement())
- apply morphological operations. (using cv2.erode() and cv2.dilate())
- using binary_inverse and otsu thresholding using cv2.threshold()

### Digit Extraction
Extract digits present in the training set images using cv2.findContours(). Manually segregate the extracted digits to generate the training set images.

![digit](https://user-images.githubusercontent.com/47391270/73359750-8b3a4b80-42c7-11ea-8dc2-0531b9f08e53.png)

### HOG Feature Extractor
Feature extraction is the process of identifying the unique characteristics of an input (digit in our case) which enables in training a Machine Learning algorithm. Histogram of Oriented Gradients(HOG) are feature extractors mainly used in computer vision object detection. The reason HOG is utilized so heavily is because local object appearance and shape can be characterized using the distribution of local intensity gradients.

The extracted features from HOG are given as input to train a k-neighbours classifier with n_neighbors=1. 

### Testing 
- apply the above image processing methods on test images
- extract the digits from the processed image
- extract features for the digits using HOG 
- predict on these features using the trained knn model.
- concatenate the predicted digits to obtain the barcode number
