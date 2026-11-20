# EXP-3-Record-Histogram-processing-

Aim: To write a Python program using OpenCV to perform histogram equalization on both grayscale and color images to enhance image contrast and brightness.

The program performs the following operations:

Read and display a grayscale image Plot histogram of the grayscale image Apply histogram equalization on grayscale image Read and display a color image Plot histogram of B, G, R channels Convert image to HSV color space Apply histogram equalization on the Value (V) channel Convert the enhanced image back to BGR format Display original and enhanced images with histograms Software Used: Anaconda – Python 3.7 Jupyter Notebook / VS Code OpenCV (cv2) NumPy Matplotlib Algorithm: Step 1: Import the required libraries: OpenCV, NumPy, and Matplotlib.

Step 2: Read the image parrot.jpg in grayscale format.

Step 3: Display the grayscale image and plot its histogram.

Step 4: Apply histogram equalization using cv2.equalizeHist() to enhance contrast.

Step 5: Display original grayscale image, its histogram, enhanced image, and its histogram using a 2 × 2 grid.

Step 6: Read the same image in color format.

Step 7: Split the image into B, G, R channels and plot their histograms.

Step 8: Convert the image from BGR to HSV color space.

Step 9: Apply histogram equalization on the V (Value) channel.

Step 10: Merge the channels and convert the image back to BGR format.

Step 11: Display original color image, histogram, enhanced image, and enhanced histogram using a 2 × 2 grid.

Developed By: Name: MOHANA K.V.S.L

Register No: 21222420093

Program:
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
img = cv2.imread(r"mona.png",cv2.IMREAD_GRAYSCALE)
plt.imshow(img, cmap='gray')
plt.title('original_image')
plt.show()
```
```
plt.hist(img.ravel(),256,range = [0, 256]);
plt.title('Original Image')
plt.show()
```
```
img_eq = cv2.equalizeHist(img)
plt.hist(img_eq.ravel(), 256, range = [0, 256]); 
plt.title('Equalized Histogram')
```

```
plt.imshow(img_eq, cmap='gray')
plt.title('original image')
plt.show()
```
```
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Read image
img = cv2.imread(r"mona.png")

# Equalize each color channel separately
b, g, r = cv2.split(img)

b_eq = cv2.equalizeHist(b)
g_eq = cv2.equalizeHist(g)
r_eq = cv2.equalizeHist(r)

# Merge equalized channels
img_eq = cv2.merge((b_eq, g_eq, r_eq))

# Display original and equalized images
plt.figure(figsize=(12, 10))

plt.subplot(221)
plt.imshow(cv2.cvtColor(img, cv2.COLOR_BGR2RGB))
plt.title('Original Color Image')
plt.axis('off')

plt.subplot(222)
plt.imshow(cv2.cvtColor(img_eq, cv2.COLOR_BGR2RGB))
plt.title('Equalized Image')
plt.axis('off')

# Original histogram
plt.subplot(223)
plt.hist(img.ravel(), bins=256, range=[0, 256])
plt.title('Original Image')

plt.subplot(224)
plt.hist(img_eq.ravel(), bins=256, range=[0, 256])
plt.title('Histogram Equalized')

plt.tight_layout()
plt.show()
```
Output:
ORIGINAL IMAGE:
<img width="371" height="462" alt="image" src="https://github.com/user-attachments/assets/ac3a5e96-5b15-4eae-835d-dc3861ce0f63" />

<img width="588" height="468" alt="image" src="https://github.com/user-attachments/assets/49e4b5c1-2362-462c-9d88-83ed2222699b" />


Equalised Histogram:


<img width="602" height="451" alt="image" src="https://github.com/user-attachments/assets/d4b09a4d-6c65-4fb9-a772-799d3bbac211" />

<img width="370" height="445" alt="image" src="https://github.com/user-attachments/assets/8520ea83-9668-4f57-bea1-9290a560660a" />

Histogram Equalization of Grayscale Image:


<img width="1283" height="627" alt="image" src="https://github.com/user-attachments/assets/4156dba4-dbb9-4eef-bcf9-a8da6868c2fc" />

<img width="1147" height="553" alt="image" src="https://github.com/user-attachments/assets/6bebf940-aad8-4204-af6f-51b7955b94c6" />

