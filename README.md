# Image Smoothing and Sharpening Using OpenCV

## Aim

To write a Python program using OpenCV to apply different smoothing filters (Averaging, Weighted Averaging, Gaussian, Median) and sharpening filters (Laplacian Kernel and Laplacian Operator) for image enhancement, and display each result separately along with the original image for comparison.

## The program performs the following operations:

- Read and display an input image
- Apply Averaging filter
- Apply Weighted Averaging filter
- Apply Gaussian filter
- Apply Median filter
- Apply Laplacian sharpening using kernel
- Apply Laplacian operator
- Display all outputs for comparison

## Software Used

- Anaconda – Python 3.7
- Jupyter Notebook / VS Code
- OpenCV (cv2)
- NumPy
- Matplotlib
  
## Algorithm

### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:
Read the input image (e.g., image.jpg).

### Step 3:
Convert the image from BGR to RGB format for display.

### Step 4:
Apply Averaging Filter using cv2.blur().

### Step 5:
Apply Weighted Averaging Filter using a custom kernel with cv2.filter2D().

### Step 6:
Apply Gaussian Filter using cv2.GaussianBlur().

### Step 7:
Apply Median Filter using cv2.medianBlur().

### Step 8:
Apply Laplacian Sharpening using Kernel with cv2.filter2D().

### Step 9:
Convert image to grayscale and apply Laplacian Operator using cv2.Laplacian().

### Step 10:
Display all filtered images using a grid layout for comparison.

### Developed By
#### Name: DEVI S
#### Register No: 212225100008

## Program 

### Smoothing Filters

- Averaging filter produces blurred image
- Weighted averaging provides smoother result with less distortion
- Gaussian filter preserves edges better while reducing noise
- Median filter removes salt-and-pepper noise effectively

```
import cv2
import matplotlib.pyplot as plt
import numpy as np
image1=cv2.imread(r"C:\Users\sdhan\Downloads\WhatsApp Image 2026-10-17 at 3.09.40 PM.jpeg")
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)
kernel=np.ones((11,11),np.float32)/169
image3=cv2.filter2D(image2,-1,kernel)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Average Filter Image")
plt.axis("off")
plt.show()
```


<img width="686" height="412" alt="image" src="https://github.com/user-attachments/assets/ac89cac3-45cf-4f5e-8a93-e4106dcc8935" />


```
kernel1=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)
image3=cv2.filter2D(image2,-1,kernel1)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Weighted Average Filter Image")
plt.axis("off")
plt.show()
```


<img width="480" height="302" alt="image" src="https://github.com/user-attachments/assets/ecc29b19-6d60-4fbe-8c49-071af43d6cac" />


```
gaussian_blur=cv2.GaussianBlur(image2,(33,33),0,0)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(gaussian_blur)
plt.title("Gaussian Blur")
plt.axis("off")
plt.show()
```


<img width="450" height="297" alt="image" src="https://github.com/user-attachments/assets/0f11fe6f-16ad-4bde-8b3d-22b7412091c0" />


```
median=cv2.medianBlur(image2,13)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(median)
plt.title("Median Blur")
plt.axis("off")
plt.show()
```


<img width="650" height="418" alt="image" src="https://github.com/user-attachments/assets/dcf95097-7f7a-45b8-a4ee-56e43aabf15f" />


### Sharpening Filters
- Laplacian kernel enhances edges and fine details
- Laplacian operator detects edges clearly in grayscale

```
kernel2=np.array([[-1,-1,-1],[2,-2,1],[2,1,-1]])
image3=cv2.filter2D(image2,-1,kernel2)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Laplacian Kernel")
plt.axis("off")
plt.show()
```


<img width="463" height="312" alt="image" src="https://github.com/user-attachments/assets/48196e69-e59a-4252-8da0-6d773f114e9b" />

```
laplacian = cv2.Laplacian(image2, cv2.CV_64F)
laplacian = np.clip(laplacian, 0, 1)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(laplacian)
plt.title("Laplacian Operator")
plt.axis("off")
plt.show()
```

<img width="471" height="312" alt="image" src="https://github.com/user-attachments/assets/701679e0-8f2a-4d06-a629-dedf803f02f6" />

## Result

Thus, smoothing filters and sharpening filters are successfully implemented using OpenCV.

The smoothing filters reduce noise and improve image quality, while sharpening filters enhance edges and details for better feature extraction.
