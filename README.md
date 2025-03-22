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
gray_image = cv2.imread('flower.png', cv2.IMREAD_GRAYSCALE)
plt.title("Grayscale Image")
plt.imshow(gray_image, cmap='gray')
plt.axis('off')
print("Name : Dharshni V M \n Register Number : 212223240029")
plt.title("Histogram of Grayscale Image")
plt.hist(gray_image.ravel(), bins=256, color='black', alpha=0.6)
plt.xlim(0, 255)
plt.tight_layout()
plt.show()
equalized_gray_image = cv2.equalizeHist(gray_image)
print("Name : Dharshni V M \n Register Number : 212223240029")
plt.title("Histogram of Equalized Grayscale Image")
plt.hist(equalized_gray_image.ravel(), bins=256, color='black', alpha=0.6)
plt.xlim(0, 255)
plt.title("Enhanced Grayscale Image")
plt.imshow(equalized_gray_image, cmap='gray')
plt.axis('off')

import cv2
import numpy as np
import matplotlib.pyplot as plt
color_image = cv2.imread('shero.jpg')
plt.title("Input Color Image")
plt.imshow(cv2.cvtColor(color_image, cv2.COLOR_BGR2RGB))
plt.axis('off')
hist_b = cv2.calcHist([color_image], [0], None, [256], [0, 256])
hist_g = cv2.calcHist([color_image], [1], None, [256], [0, 256])
hist_r = cv2.calcHist([color_image], [2], None, [256], [0, 256])
print("Name : Dharshni V M \n Register Number : 212223240029")
plt.title("Histogram of Input Color Image")
plt.plot(hist_b, color='blue', label='Blue channel')
plt.plot(hist_g, color='green', label='Green channel')
plt.plot(hist_r, color='red', label='Red channel')
plt.show()
blue_channel_eq = cv2.equalizeHist(color_image[:, :, 0])
green_channel_eq = cv2.equalizeHist(color_image[:, :, 1])
red_channel_eq = cv2.equalizeHist(color_image[:, :, 2])
equalized_color_image = cv2.merge([blue_channel_eq, green_channel_eq, red_channel_eq])
plt.title("Equalized Image")
plt.imshow(equalized_color_image[:,:,::-1])
plt.axis('off')
```
## Output:
### Input Grayscale Image and Color Image

![flower](https://github.com/user-attachments/assets/5dacd446-4f3a-4d88-8e71-9384a9e2d013)

![input img](https://github.com/user-attachments/assets/b1144efc-3d01-4e4d-a7e6-660777b1270d)

### Histogram of Grayscale Image and any channel of Color Image
![hist grayscale](https://github.com/user-attachments/assets/2717ed8c-7fdf-414e-a3f3-072e267e2fa8)

![hist input img](https://github.com/user-attachments/assets/b1cd9400-b43e-46d0-bfd7-cf57008eb3f6)

### Histogram Equalization of Grayscale Image.

![equalisation hist](https://github.com/user-attachments/assets/c72ca34b-c55f-4c77-acd5-3722c5e992cc)

## Result: 
Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.
