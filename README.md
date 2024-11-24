# Implementation-of-Erosion-and-Dilation
## Aim
To implement Erosion and Dilation using Python and OpenCV.
## Software Required
1. Anaconda - Python 3.7
2. OpenCV
## Algorithm:
### Step1:
Apply the dilation operation on the image using cv2.dilate() with the same structuring element. Dilation will increase the size of the white regions (text) in the image, effectively reversing the effect of erosion

### Step2:
Initialize a blank image (100 pixels high and 400 pixels wide) using NumPy. The image should be a single-channel (grayscale) array filled with zeros (black).

### Step3:
Use OpenCV's cv2.putText() function to overlay the text "HYCINTH" on the blank image. Define the font style, position, font scale, color, and thickness for rendering the text.

### Step4:
Specify the size of the structuring element (e.g., 5x5 pixels) and create a rectangular structuring element using cv2.getStructuringElement(). This element will be used for the morphological operations.

### Step5:
Apply the erosion operation on the image using cv2.erode() with the defined structuring element. Erosion will reduce the size of the white regions (text) in the image.


## DEVELOPED BY :Kathiravan P
## REGISTER NO: 212222230063

## Program:
# Import the necessary packages
``` 
import cv2
import matplotlib.pyplot as plt


image = np.zeros((300, 600, 3), dtype="uint8")
```
# Create the Text using cv2.putText
```

text = "HASHISH"
font = cv2.FONT_HERSHEY_SIMPLEX
cv2.putText(image, text, (50, 150), font, 2, (255, 255, 255), 3)
```


# Create the structuring element
```
kernel = cv2.getStructuringElement(cv2.MORPH_RECT, (5, 5))
```
# Erode the image
```
eroded_image = cv2.erode(image, kernel, iterations=1)
```
# Dilate the image
```
dilated_image = cv2.dilate(image, kernel, iterations=1)
```
# Convert images from BGR to RGB for Matplotlib
```
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
eroded_image_rgb = cv2.cvtColor(eroded_image, cv2.COLOR_BGR2RGB)
dilated_image_rgb = cv2.cvtColor(dilated_image, cv2.COLOR_BGR2RGB)
plt.figure(figsize=(10, 5))
```
# Original Image
```
# Original Image

lt.imshow(image_rgb)
plt.title("Original Image")
plt.axis("off")

plt.show()
```
![image](https://github.com/user-attachments/assets/03060ed9-18ec-41cb-84a7-b70b90a06a6b)

# Erode the image
```
plt.imshow(eroded_image_rgb)
plt.title("Eroded Image")
plt.axis("off")
```
![image](https://github.com/user-attachments/assets/7b6d9329-b839-4b1d-9917-b32156997445)

# Dilate the image
```
plt.imshow(dilated_image_rgb)
plt.title("Dilated Image")
plt.axis("off")
```
![image](https://github.com/user-attachments/assets/792d182f-0b9e-4d0f-abad-43bf90ff205f)

## Result
Thus the generated text image is eroded and dilated using python and OpenCV.
