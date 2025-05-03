# Histogram-of-an-images
## Aim
To obtain a histogram for finding the frequency of pixels in an Image with pixel values ranging from 0 to 255. Also write the code using OpenCV to perform histogram equalization.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Read the gray and color image using imread()

### Step2:
Print the image using imshow().



### Step3:
Use calcHist() function to mark the image in graph frequency for gray and color image.

### step4:
Use calcHist() function to mark the image in graph frequency for gray and color image.

### Step5:
The Histogram of gray scale image and color image is shown.


## Program:
```python
# Developed By: Dharshni V M
# Register Number: 212223240029
import cv2
import numpy as np
import matplotlib.pyplot as plt

img = cv2.imread('parrot.jpg', cv2.IMREAD_GRAYSCALE)

plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()

plt.hist(img.ravel(),256,range = [0,256]);
plt.title('Original Image')
plt.show()

img_eq = cv2.equalizeHist(img)

plt.hist(img_eq.ravel(),256,range = [0,256]);
plt.title('Equalized Histogram')

plt.imshow(img_eq, cmap='gray')
plt.title('Original Image')
plt.show

img = cv2.imread('parrot.jpg', cv2.IMREAD_COLOR)

img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)

img_hsv[:,:,2] = cv2.equalizeHist(img_hsv[:,:,2])

img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)

plt.figure(figsize = (10, 12))
plt.subplot(121);plt.imshow(img[:,:,::-1]); plt.title('Original Color Image')
plt.subplot(122);plt.imshow(img_eq[:,:,::-1]); plt.title('Equalized Image')
plt.subplot(321);plt.hist(img.ravel(),256,range = [0,256]); plt.title('Original Image')
plt.subplot(322);plt.hist(img_eq.ravel(),256,range = [0,256]); plt.title('Equalized Image')
```
## Output:
### Input Image

![original img](https://github.com/user-attachments/assets/a4507a7e-a2a5-4460-a9e9-55e683f787ce)

### Input Image Histogram

![hist original img](https://github.com/user-attachments/assets/56952a90-b4fd-4d53-87a8-0ff04a20e598)

### Gray Image

![gray img](https://github.com/user-attachments/assets/4d708cbc-b319-4ecd-992d-d66311f8b836)

### Equalized Histogram

![equ hist](https://github.com/user-attachments/assets/a38ed2a8-8ecd-4592-9878-317a0cd75c20)

### Equalized Images and Histogram

![Equ img and hist](https://github.com/user-attachments/assets/d214aeb4-5b51-4dc2-b8ff-c74333cbe5f2)

## Result: 
Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.
