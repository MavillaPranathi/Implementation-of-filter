# Implementation of filter
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step 1:
Import necessary libraries: OpenCV, NumPy, and Matplotlib.Read an image, convert it to RGB format, define an 11x11 averaging kernel, and apply 2D convolution filtering.Display the original and filtered images side by side using Matplotlib.

### Step 2:
Define a weighted averaging kernel (kernel2) and apply 2D convolution filtering to the RGB image (image2).Display the resulting filtered image (image4) titled 'Weighted Averaging Filtered' using Matplotlib's imshow function.

### Step 3:

Apply Gaussian blur with a kernel size of 11x11 and standard deviation of 0 to the RGB image (image2).Display the resulting Gaussian-blurred image (gaussian_blur) titled 'Gaussian Blurring Filtered' using Matplotlib's imshow function.
### Step 4:
Apply median blur with a kernel size of 11x11 to the RGB image (image2).Display the resulting median-blurred image (median) titled 'Median Blurring Filtered' using Matplotlib's imshow function.

### Step 5 :
Define a Laplacian kernel (kernel3) and perform 2D convolution filtering on the RGB image (image2).Display the resulting filtered image (image5) titled 'Laplacian Kernel' using Matplotlib's imshow function.
### Step 6 :
Apply the Laplacian operator to the RGB image (image2) using OpenCV's cv2.Laplacian function.Display the resulting image (new_image) titled 'Laplacian Operator' using Matplotlib's imshow function.

## Program:

 ### Developed By:M.Pranathi
 ### Register Number:212222240064

### 1. Smoothing Filters

#### i) Using Averaging Filter
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1 = cv2.imread('mahi1.jpg')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

kernel = np.ones((11,11), np. float32)/121
image3 = cv2.filter2D(image2, -1, kernel)

plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title('Original')
plt.axis('off')

plt.subplot(1,2,2)
plt.imshow(image3)
plt.title('Filtered')
plt.axis('off')
```
#### ii) Using Weighted Averaging Filter
```python
image1 = cv2.imread('mahi1.jpg')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

kernel2 = np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image4 = cv2.filter2D(image2, -1, kernel2)
plt.imshow(image4)
plt.title('Weighted Averaging Filtered')
```
#### iii) Using Gaussian Filter
```python
image1 = cv2.imread('mahi1.jpg')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

gaussian_blur = cv2.GaussianBlur(src=image2, ksize=(11,11), sigmaX=0, sigmaY=0)
plt.imshow(gaussian_blur)
plt.title(' Gaussian Blurring Filtered')
```

#### iv) Using Median Filter
```python
image1 = cv2.imread('mahi1.jpg')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)
median=cv2.medianBlur (src=image2, ksize=11)
plt.imshow(median)
plt.title(' Median Blurring Filtered')
```

### 2. Sharpening Filters
#### i) Using Laplacian Kernel
```python
image1 = cv2.imread('mahi1.jpg')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

kernel3 = np.array([[0,1,0], [1, -4,1],[0,1,0]])
image5 =cv2.filter2D(image2, -1, kernel3)
plt.imshow(image5)
plt.title('Laplacian Kernel')
```
#### ii) Using Laplacian Operator
```python
image1 = cv2.imread('mahi1.jpg')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

new_image = cv2.Laplacian (image2, cv2.CV_64F)
plt.imshow(new_image)
plt.title('Laplacian Operator')
```

## OUTPUT:
### 1. Smoothing Filters

#### i) Using Averaging Filter

![image](https://github.com/MavillaPranathi/Implementation-of-filter/assets/118343610/abf26c10-bc56-4175-a895-c643155ba1c2)

![image](https://github.com/MavillaPranathi/Implementation-of-filter/assets/118343610/374478ae-2beb-4d84-828b-01a366c2c5ec)


#### ii) Using Weighted Averaging Filter

![image](https://github.com/MavillaPranathi/Implementation-of-filter/assets/118343610/aff446af-a1e9-45bb-963d-384dacaaf9b6)



#### iii) Using Gaussian Filter

![image](https://github.com/MavillaPranathi/Implementation-of-filter/assets/118343610/625f2b7d-f1bf-4c64-a41a-a9074476553b)



#### iv) Using Median Filter

![image](https://github.com/MavillaPranathi/Implementation-of-filter/assets/118343610/ce2dbf69-c175-4542-aaad-1b177b7af021)


### 2. Sharpening Filters

#### i) Using Laplacian Kernel

![image](https://github.com/MavillaPranathi/Implementation-of-filter/assets/118343610/9153a13f-befd-4459-8ad8-a063cb3c00da)


#### ii) Using Laplacian Operator

![image](https://github.com/MavillaPranathi/Implementation-of-filter/assets/118343610/5bbc3bcb-a1d5-4f51-9a31-298fc92c3336)



## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
