# Dipt-exp-5

# Image Smoothing and Sharpening Using OpenCV

##  Developed By
## Name: Nara Guna Susmitha
## Register No: 212224230176

## Aim

To write a Python program using OpenCV to apply different smoothing filters (Averaging, Weighted Averaging, Gaussian, Median) and sharpening filters (Laplacian Kernel and Laplacian Operator) for image enhancement, and display each result separately along with the original image for comparison.

---

## The program performs the following operations:

- Read and display an input image  
- Apply Averaging filter  
- Apply Weighted Averaging filter  
- Apply Gaussian filter  
- Apply Median filter  
- Apply Laplacian sharpening using kernel  
- Apply Laplacian operator  
- Display all outputs for comparison  

---

##  Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (cv2)  
- NumPy  
- Matplotlib  

---

##  Algorithm

### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:
Read the input image (e.g., `image.jpg`).

### Step 3:
Convert the image from BGR to RGB format for display.

### Step 4:
Apply Averaging Filter using `cv2.blur()`.

### Step 5:
Apply Weighted Averaging Filter using a custom kernel with `cv2.filter2D()`.

### Step 6:
Apply Gaussian Filter using `cv2.GaussianBlur()`.

### Step 7:
Apply Median Filter using `cv2.medianBlur()`.

### Step 8:
Apply Laplacian Sharpening using Kernel with `cv2.filter2D()`.

### Step 9:
Convert image to grayscale and apply Laplacian Operator using `cv2.Laplacian()`.

### Step 10:
Display all filtered images using a grid layout for comparison.

---



---
## Program
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
img = cv2.imread("Qno. 1.jpeg")
img = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
plt.imshow(img)
plt.title("Original Image")
plt.axis("off")
plt.show()

avg = cv2.blur(img, (5,5))
plt.imshow(avg)
plt.title("Averaging Filter")
plt.axis("off")
plt.show()

kernel = np.array([[1,2,1],
                 [2,4,2],
                 [1,2,1]], np.float32) / 16
weighted = cv2.filter2D(img, -1, kernel)
plt.imshow(weighted)
plt.title("Weighted Averaging Filter")
plt.axis("off")
plt.show()

gaussian = cv2.GaussianBlur(img, (5,5), 0)
plt.imshow(gaussian)
plt.title("Gaussian Filter")
plt.axis("off")
plt.show()

median = cv2.medianBlur(img, 5)
plt.imshow(median)
plt.title("Median Filter")
plt.axis("off")
plt.show()

kernel = np.array([[0,-1,0],
                   [-1,5,-1],
                   [0,-1,0]])
sharp = cv2.filter2D(img, -1, kernel)<img width="572" height="451" alt="Screenshot 2026-11-16 220339" src="https://github.com/user-attachments/assets/4bf8faf6-6b4a-40b8-80b4-23c2e061acc9" />

plt.imshow(sharp)
plt.title("Laplacian Kernel")
plt.axis("off")
plt.show()

lap = cv2.Laplacian(img, cv2.CV_64F)
lap = np.uint8(np.absolute(lap))
plt.imshow(lap)
plt.title("Laplacian Operator")
plt.axis("off")
plt.show()
```

##  Output

<img width="382" height="445" alt="image" src="https://github.com/user-attachments/assets/a8d839fe-3699-4471-8c6e-2a71580b8f4d" />

<img width="385" height="441" alt="image" src="https://github.com/user-attachments/assets/8be70404-bfbb-4f66-bb22-3659c60108ff" />

<img width="385" height="446" alt="image" src="https://github.com/user-attachments/assets/1129851f-6c43-4f9c-ab98-df28442d771e" />

<img width="387" height="453" alt="image" src="https://github.com/user-attachments/assets/40ca64ae-8c1f-4e85-9906-b634500340f1" />

<img width="382" height="450" alt="image" src="https://github.com/user-attachments/assets/d44789f5-3dd7-49ba-ab5c-fdf031731187" />

<img width="412" height="453" alt="image" src="https://github.com/user-attachments/assets/0d9f730a-d792-4aca-963c-dfbf9309f326" />

<img width="387" height="452" alt="image" src="https://github.com/user-attachments/assets/b9528fe4-66e7-4930-8b9b-122e6239a044" />


##  Result

Thus, smoothing filters and sharpening filters are successfully implemented using OpenCV.

The smoothing filters reduce noise and improve image quality, while sharpening filters enhance edges and details for better feature extraction.
