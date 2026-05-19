# Histogram Equalization Using OpenCV (Grayscale & Color Images)
## Name: SRI HARI KRISHNA D T 
## Register No: 212224240160
## Aim
To write a Python program using OpenCV to perform histogram equalization on both grayscale and color images to enhance image contrast and brightness.

The program performs the following operations:

Read and display a grayscale image
Plot histogram of the grayscale image
Apply histogram equalization on grayscale image
Read and display a color image
Plot histogram of B, G, R channels
Convert image to HSV color space
Apply histogram equalization on the Value (V) channel
Convert the enhanced image back to BGR format
Display original and enhanced images with histograms
## Software Used
Anaconda – Python 3.7
Jupyter Notebook / VS Code
OpenCV (cv2)
NumPy
Matplotlib
## Algorithm
### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:
Read the image parrot.jpg in grayscale format.

### Step 3:
Display the grayscale image and plot its histogram.

### Step 4:
Apply histogram equalization using cv2.equalizeHist() to enhance contrast.

### Step 5:
Display original grayscale image, its histogram, enhanced image, and its histogram using a 2 × 2 grid.

### Step 6:
Read the same image in color format.

### Step 7:
Split the image into B, G, R channels and plot their histograms.

### Step 8:
Convert the image from BGR to HSV color space.

### Step 9:
Apply histogram equalization on the V (Value) channel.

### Step 10:
Merge the channels and convert the image back to BGR format.

### Step 11:
Display original color image, histogram, enhanced image, and enhanced histogram using a 2 × 2 grid.

## Program
```
import cv2
import numpy as np
import matplotlib.pyplot as plt

img = cv2.imread('parrot.jpg', cv2.IMREAD_GRAYSCALE)

plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()

plt.hist(img.ravel(),256,range = [0, 256]);
plt.title('Original Image')
plt.show()

img_eq = cv2.equalizeHist(img)

plt.hist(img_eq.ravel(), 256, range = [0, 256])
plt.title('Equalized Histogram')

plt.imshow(img_eq, cmap='gray')
plt.title('Original Image')
plt.show()

img = cv2.imread('parrot.jpg', cv2.IMREAD_COLOR)

img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)

img_hsv[:,:,2] = cv2.equalizeHist(img_hsv[:, :, 2])

img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)

 plt.imshow(img_eq[:,:,::-1]); plt.title('Equalized Image');plt.show()

plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized');plt.show()

plt.figure(figsize = (20,10))
plt.subplot(221); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(222); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')
plt.show()
```
## Output
### Grayscale Histogram Equalization
 -Original grayscale image is displayed
 
 <img width="564" height="374" alt="image" src="https://github.com/user-attachments/assets/9f81f089-30ac-469d-9e29-a29e8e6c1573" />

 -Histogram of original grayscale image is plotted 
 
 <img width="657" height="415" alt="image" src="https://github.com/user-attachments/assets/69eb6841-2d96-41ad-9cf1-242430744ec0" />

 -Enhanced image after histogram equalization is displayed
 
 <img width="669" height="427" alt="image" src="https://github.com/user-attachments/assets/2a0a2446-8249-4fdb-a29d-e8ed1a263f25" />

 -Histogram of enhanced grayscale image shows improved contrast
 
 <img width="586" height="376" alt="image" src="https://github.com/user-attachments/assets/d676876e-61d9-402f-81ab-49779713f369" />

## Color Image Histogram Equalization
  -Original color image is displayed
  
  <img width="624" height="374" alt="image" src="https://github.com/user-attachments/assets/55ac5770-e301-473e-9c9e-b12e79388361" />

  <img width="778" height="408" alt="image" src="https://github.com/user-attachments/assets/a3541dbc-4e01-4e9e-928b-d2133bd10bcd" />


  -Enhanced image after HSV-based equalization is displayed

  <img width="1049" height="742" alt="image" src="https://github.com/user-attachments/assets/a4d5e204-c19b-4b60-a1f3-cf9e4c55bad8" />

## Result
Thus, histogram equalization is successfully performed on both grayscale and color images using OpenCV. The contrast and brightness of the images are significantly improved, enhancing visual quality and feature visibility.







