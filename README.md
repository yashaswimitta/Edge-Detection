# Edge-Detection
## Aim:
To perform edge detection using Sobel, Laplacian, and Canny edge detectors.

## Software Required:
Anaconda - Python 3.7

## Algorithm:

Step1:

Import the necessary modules.
Step2:

Load the image to operate on.
Step3:

Convert the image to grayscale image.
Step4:

Use Sobel operator along x,y and xy directions.
Step5:

Operate the image using Laplacian operator.
Step6:

Operate the image using Canny Edge operator.
Step7:

Show all the operated images output

 
## Program:

``` Python
# Import the packages
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1=cv2.imread ('dip7.jpg') 
gray_image = cv2.cvtColor(image1,cv2.COLOR_BGR2GRAY)


# Load the image, Convert to grayscale and remove noise
plt.title('GRAY IMAGE')
plt.imshow(gray_image,cmap = 'gray')

img = cv2.GaussianBlur(gray_image,(3,3),0)
sobelx = cv2.Sobel(gray_image,cv2.CV_64F,1,0,ksize=5)
sobely = cv2.Sobel(gray_image,cv2.CV_64F,0,1,ksize=5)
sobelxy =cv2.Sobel(gray_image,cv2.CV_64F,1,1,ksize=5)
plt.figure(1)
plt.subplot(2,2,1)
plt.imshow(gray_image,cmap = 'gray')
plt.title('Original'), plt.xticks([]), plt.yticks([])


# SOBEL EDGE DETECTOR
plt.subplot(2,2,2)
plt.imshow(sobelx,cmap='gray')
plt.title('sobelx')
plt.xticks([]), plt.yticks([])

plt.subplot(2,2,3)
plt.imshow(sobely,cmap='gray')
plt.title('sobely')
plt.xticks([]), plt.yticks([])

plt.subplot(2,2,4)
plt.imshow(sobelxy,cmap='gray')
plt.title('sobelxy')
plt.xticks([]), plt.yticks([])
plt.show()


# LAPLACIAN EDGE DETECTOR

laplacian = cv2.Laplacian(gray_image,cv2.CV_64F)
plt.imshow(laplacian,cmap='gray')
plt.title('laplacian')
plt.show()

# CANNY EDGE DETECTOR
canny_edges = cv2.Canny(gray_image, 120, 150)
plt.imshow(canny_edges,cmap='gray')
plt.title('canny_edges')
plt.show()




```
## Output:
### SOBEL EDGE DETECTOR

![dip y7-1](https://user-images.githubusercontent.com/94619247/233027909-f11b9189-32ff-44a7-9011-2d88468ac773.jpg)


![dip y7-2](https://user-images.githubusercontent.com/94619247/233027885-258aa96f-47d7-4d1f-9fe3-1e3dde1b4c2e.jpg)

### LAPLACIAN EDGE DETECTOR

![dip y7-3](https://user-images.githubusercontent.com/94619247/233027998-7ed5edf8-80a6-4c4e-8082-e0a6525862ea.jpg)


### CANNY EDGE DETECTOR
![dip y7-4](https://user-images.githubusercontent.com/94619247/233028374-a0162cb5-87f5-47d9-a965-63615720c692.jpg)


## Result:
Thus the edges are detected using Sobel, Laplacian, and Canny edge detectors.
