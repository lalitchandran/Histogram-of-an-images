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
The Histogram of gray scale image and color image is shown


## Program:
```python
# Developed By: S LALIT CHANDRAN
# Register Number: 212223240077
import cv2
import numpy as np
from matplotlib import pyplot as plt

gray_image = cv2.imread('car.jpg', cv2.IMREAD_GRAYSCALE)

plt.title("Grayscale Image")
plt.imshow(gray_image, cmap='gray')
plt.axis('off')

print("Name : S LALIT CHANDRAN \n Register Number : 212223240077")

plt.title("Histogram of Grayscale Image")
plt.hist(gray_image.ravel(), bins=256, color='black', alpha=0.6)
plt.xlim(0, 255)
plt.tight_layout()
plt.show()

equalized_gray_image = cv2.equalizeHist(gray_image)

plt.title("Histogram of Equalized Grayscale Image")
plt.hist(equalized_gray_image.ravel(), bins=256, color='black', alpha=0.6)
plt.xlim(0, 255)

plt.title("Enhanced Grayscale Image")
plt.imshow(equalized_gray_image, cmap='gray')
plt.axis('off')

import cv2
import numpy as np
import matplotlib.pyplot as plt

color_image = cv2.imread('cat.jpg')

plt.title("Input Color Image")
plt.imshow(cv2.cvtColor(color_image, cv2.COLOR_BGR2RGB))
plt.axis('off')

hist_b = cv2.calcHist([color_image], [0], None, [256], [0, 256])
hist_g = cv2.calcHist([color_image], [1], None, [256], [0, 256])
hist_r = cv2.calcHist([color_image], [2], None, [256], [0, 256])

print("Name : Rakshitha J \n Register Number : 212223240135")


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
![image](https://github.com/user-attachments/assets/c3949f14-2e1a-4eb1-a7e1-1c597c7f8231)




### Histogram of Grayscale Image and any channel of Color Image

![image](https://github.com/user-attachments/assets/ebfb1e8c-db26-48ce-8c0b-0e14208611d1)

### Histogram Equalization of Grayscale Image.

![image](https://github.com/user-attachments/assets/d9a0c8c0-29b0-4b63-884d-e4cffa654cb3)
![image](https://github.com/user-attachments/assets/7b0adfb4-c8c7-450e-b934-a821cbc3cac8)
![image](https://github.com/user-attachments/assets/649e65d3-7204-43f3-8025-f1565e685f12)
![image](https://github.com/user-attachments/assets/8473436f-18be-4cd6-98d4-d3aef161cbbe)
![image](https://github.com/user-attachments/assets/7680389f-a4bb-4e25-ab20-118c3ab1aeb7)




## Result: 
Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.
