# Barcode Extractor using OpenCV

Pipeline to extract barcode number from images using OpenCV functions. A simple k-neighbours classifier was trained to detect the numbers present in the barcode.

### Image pre-processing
- convert image to grayscale
- create structure element for extracting vertical lines through morphology operations. (using cv2.getStructuringElement())
- apply morphological operations. (using cv2.erode() and cv2.dilate())
- using binary_inverse and otsu thresholding using cv2.threshold()

### Digit Extraction
Extract digits present in the training set images using cv2.findContours(). Manually segregate the extracted digits to generate the training set images.

![digit](https://user-images.githubusercontent.com/47391270/73359646-58905300-42c7-11ea-9195-14afa72ff6cd.png)
