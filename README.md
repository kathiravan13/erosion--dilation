# Implementation-of-Erosion-and-Dilation
## Aim
To implement Erosion and Dilation using Python and OpenCV.
## Software Required
1. Anaconda - Python 3.7
2. OpenCV
## Algorithm:

### Step1:
<br> import the neccesary packages


### Step2:
<br> creat the text using cv2.put Text

### Step3:
<br> create the structuting element

### Step4:
<br>  Erodde the image

### Step5:
<br> Dilate the image

 
## Program:

``` Python
import cv2
import numpy as np
from matplotlib import pyplot as plt
imput_image='actor.jpg'
color_image=cv2.imread(imput_image)
gray_image=cv2.cvtColor(color_image,cv2.COLOR_BGR2GRAY)
edges=cv2.Canny(gray_image,100,200)
kernel_size=5
kernel=np.ones((kernel_size,kernel_size),np.uint8)
erosion=cv2.erode(edges,kernel,iterations=1)
dilation=cv2.dilate(edges,kernel,iterations=1)
plt.figure(figsize=(15,10))
plt.subplot(2,3,1)
plt.imshow(cv2.cvtColor(color_image,cv2.COLOR_BGR2RGB))
plt.title('Original Color Image')
plt.axis('on')
plt.subplot(2,3,2)
plt.imshow(gray_image,cmap='gray')
plt.title('black and white image')
plt.axis('on')
plt.subplot(2,3,3)
plt.imshow(edges,cmap='gray')
plt.title('edge segmentation')
plt.axis('on')
plt.subplot(2,3,4)
plt.imshow(edges,cmap='gray')
plt.title('erosion')
plt.axis('on')
plt.subplot(2,3,5)
plt.imshow(edges,cmap='gray')
plt.title('dilation')
plt.axis('on')




```
## Output:

![image](https://github.com/user-attachments/assets/8772c861-b391-46ad-86ac-3e72fcde051d)

![image](https://github.com/user-attachments/assets/edf823ad-7f50-4af6-86b3-57e4a141e748)

![image](https://github.com/user-attachments/assets/8b564fad-11e0-45a4-804a-3e97d3741c3a)

![image](https://github.com/user-attachments/assets/bdaddde5-bd00-453d-8509-d00b641e3d83)

![image](https://github.com/user-attachments/assets/45de9ba2-2318-4ba4-bd4d-111b83857945)


## Result
Thus the generated text image is eroded and dilated using python and OpenCV.

