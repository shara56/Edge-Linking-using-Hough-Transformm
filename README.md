# Edge-Linking-using-Hough-Transformm
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:

Import all the necessary modules for the program.
### Step2:

Load a image using imread() from cv2 module.
### Step3:

Convert the image to grayscale.
### Step4:

Using Canny operator from cv2,detect the edges of the image.
### Step5:

Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.

### Name:Sharangini T K
### Reg no:212222230143
## Output
```
 import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('cat.png')
# Input Image and Grayscale Image
plt.imshow(image)
plt.title('Input Image')
plt.axis('off')
plt.show()

```
![Screenshot 2024-10-16 174245](https://github.com/user-attachments/assets/92571e48-9399-430d-8ce6-e17b5bec420d)

### Input image and grayscale image
```
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.subplot(2, 2, 2)
plt.imshow(gray_image, cmap='gray')
plt.title('Grayscale Image')
plt.axis('off')

```
![Screenshot 2024-10-16 174251](https://github.com/user-attachments/assets/ba49db1c-5043-44db-b777-6070281e3059)

### Canny Edge detector output
```
edges = cv2.Canny(gray_image, 50, 150, apertureSize=3)
plt.subplot(2, 2, 3)
plt.imshow(edges, cmap='gray')
plt.title('Canny Edge Detector Output')
plt.axis('off')
```
![Screenshot 2024-10-16 174258](https://github.com/user-attachments/assets/31e08a4a-c30e-436c-8c06-88d140ca44a9)

### Display the result of Hough transform
```
# Detect lines using the probabilistic Hough transform
lines = cv2.HoughLinesP(edges, rho=1, theta=np.pi/180, threshold=100, minLineLength=50, maxLineGap=10)

# Draw the lines on the original image
output_image = image.copy()

if lines is not None:
    for line in lines:
        x1, y1, x2, y2 = line[0]
        cv2.line(output_image, (x1, y1), (x2, y2), (0, 255, 0), 2)
# Hough Transform Result
plt.imshow(output_image)
plt.title('Hough Transform - Line Detection')
plt.axis('off')
plt.show()
# Displaying results using Matplotlib
plt.figure(figsize=(12, 12))
# Display all results
plt.show()

```
![Screenshot 2024-10-16 174306](https://github.com/user-attachments/assets/cefce07d-7237-4c33-97f4-8ed5b5626361)

## Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform.
