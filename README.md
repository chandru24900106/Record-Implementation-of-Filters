# Implementation-of-filter

## Aim

To implement filters for smoothing and sharpening images in the spatial domain.

## Software Required

- Anaconda - Python 3.7
- OpenCV
- NumPy
- Matplotlib

## Algorithm

### Step 1
Import the required libraries.

### Step 2
Read the image and convert it from BGR to RGB.

### Step 3
Apply the required smoothing and sharpening filters to the image separately.

### Step 4
Plot and display the original and filtered images using `matplotlib.pyplot`.

### Step 5
End the program.

## Program

**Developed By:** Chandru V

**Register Number:** 212224230043

## 1. Smoothing Filters

### i) Using Averaging Filter

```python
import cv2
import matplotlib.pyplot as plt
import numpy as np
image1=cv2.imread(r"C:\Users\admin\Downloads\chan.png")
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

### ii) Using Weighted Averaging Filter

```python
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
plt.show())
```

### iii) Using Gaussian Filter

```python
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

### iv) Using Median Filter

```python
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

## 2. Sharpening Filters

### i) Using Laplacian Linear Kernel

```python
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

### ii) Using Laplacian Operator

```python
laplacian=cv2.Laplacian(image2,cv2.CV_64F)
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

## Output

### 1. Smoothing Filters

#### i) Using Averaging Filter

<img width="760" height="450" alt="image" src="https://github.com/user-attachments/assets/58d18beb-de7b-4f8e-ba93-4fe47b85d835" />


#### ii) Using Weighted Averaging Filter

<img width="685" height="400" alt="image" src="https://github.com/user-attachments/assets/776edfd2-f7f2-48f7-a789-938b22dade27" />



#### iii) Using Gaussian Filter

<img width="662" height="398" alt="image" src="https://github.com/user-attachments/assets/d2d18362-acca-4128-addb-e1a509062cfb" />



#### iv) Using Median Filter

<img width="770" height="470" alt="image" src="https://github.com/user-attachments/assets/84c1e206-9c7f-410a-b4dc-6c6718dbd120" />



### 2. Sharpening Filters

#### i) Using Laplacian Kernel

<img width="676" height="393" alt="image" src="https://github.com/user-attachments/assets/4ffe43b6-ec99-4c1a-9f51-68df4c826a6c" />



#### ii) Using Laplacian Operator

<img width="706" height="413" alt="image" src="https://github.com/user-attachments/assets/2bb0344d-a10f-46a0-a916-1343ff39501b" />



## Result

Thus, filters were implemented for smoothing and sharpening images in the spatial domain using OpenCV and Python.
