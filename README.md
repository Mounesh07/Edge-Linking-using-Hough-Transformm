# Edge-Linking-using-Hough-Transformm
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:

### Step 1:
Import all the necessary modules for the program.
### Step 2:
Load a image using imread() from cv2 module.
### Step 3:
Convert the image to grayscale.
### Step 4:
Using Canny operator from cv2, detect the edges of the image.
### Step 5:
Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.

## Program:

```python
DEVELOPED BY: MOUNESH P
REGISTER NUMBER: 212222230084
```
### Import packages
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
```
### Load the image
```python
image = cv2.imread('cars.jpg')  
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
edges = cv2.Canny(gray_image, 50, 150, apertureSize=3)
```
### Detect lines using the probabilistic Hough transform
```python
lines = cv2.HoughLinesP(edges, rho=1, theta=np.pi/180, threshold=100, minLineLength=50, maxLineGap=10)
```
### Draw the lines on the original image
```python
output_image = image.copy()

if lines is not None:
    for line in lines:
        x1, y1, x2, y2 = line[0]
        cv2.line(output_image, (x1, y1), (x2, y2), (0, 255, 0), 2)
```
### Displaying results using Matplotlib
```python
plt.figure(figsize=(12, 12))
```
### Input Image and Grayscale Image
```python
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Input Image')
plt.axis('off')
plt.imshow(gray_image, cmap='gray')
plt.title('Grayscale Image')
plt.axis('off')
```
### Canny Edge Detection Output
```python
plt.imshow(edges, cmap='gray')
plt.title('Canny Edge Detector Output')
plt.axis('off')
```
### Hough Transform Result
```python
plt.imshow(cv2.cvtColor(output_image, cv2.COLOR_BGR2RGB))
plt.title('Hough Transform - Line Detection')
plt.axis('off')# Display all results
plt.show()
```
## Output

### Input image and grayscale image
![image](https://github.com/user-attachments/assets/e5885bb8-120b-4fcf-974f-a096f0783b13)

![image](https://github.com/user-attachments/assets/a7403a59-09a4-42f5-953e-ab105446b096)

### Canny Edge detector output
![image](https://github.com/user-attachments/assets/059f152f-b87a-44c4-a6c9-aa162e77e4ed)

### Display the result of Hough transform
![image](https://github.com/user-attachments/assets/e139166d-c66e-4308-82b5-7acb75ee42a8)

## Result:
Thus, the program to detect the lines using Hough Transform implemented successfully.
