# Histogram Equalization Using OpenCV (Grayscale & Color Images)

---

## Aim

To write a Python program using OpenCV to perform histogram equalization on both grayscale and color images to enhance image contrast and brightness.

The program performs the following operations:

- Read and display a grayscale image  
- Plot histogram of the grayscale image  
- Apply histogram equalization on grayscale image  
- Read and display a color image  
- Plot histogram of B, G, R channels  
- Convert image to HSV color space  
- Apply histogram equalization on the Value (V) channel  
- Convert the enhanced image back to BGR format  
- Display original and enhanced images with histograms  

---

## Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (`cv2`)  
- NumPy  
- Matplotlib  

---

## Algorithm

### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:
Read the image `parrot.jpg` in grayscale format.

### Step 3:
Display the grayscale image and plot its histogram.

### Step 4:
Apply histogram equalization using `cv2.equalizeHist()` to enhance contrast.

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

---

## Program

### Developed By:
**Name:** _S.Tinku___________________________  

### Register No:212225220116

~~
# Import the required libraries
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Read grayscale image
img_gray = cv2.imread(r"C:\Users\acer\Desktop\Peacock_on_tree_.jpg", cv2.IMREAD_GRAYSCALE)

# Display grayscale and histogram
plt.figure(figsize=[12,10])
plt.subplot(221); plt.imshow(img_gray, cmap='gray'); plt.title("Original Grayscale")
plt.subplot(222); plt.hist(img_gray.ravel(), 256, [0,256]); plt.title("Original Histogram")

# Equalize grayscale
img_gray_eq = cv2.equalizeHist(img_gray)
plt.subplot(223); plt.imshow(img_gray_eq, cmap='gray'); plt.title("Equalized Grayscale")
plt.subplot(224); plt.hist(img_gray_eq.ravel(), 256, [0,256]); plt.title("Equalized Histogram")
plt.show()

# Read color image
img_color = cv2.imread(r"C:\Users\acer\Desktop\Peacock_on_tree_.jpg", cv2.IMREAD_COLOR)

# Convert to HSV and equalize V channel
img_hsv = cv2.cvtColor(img_color, cv2.COLOR_BGR2HSV)
img_hsv[:,:,2] = cv2.equalizeHist(img_hsv[:,:,2])
img_color_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)

# Display original vs enhanced
plt.figure(figsize=[12,10])
plt.subplot(121); plt.imshow(cv2.cvtColor(img_color, cv2.COLOR_BGR2RGB)); plt.title("Original Color")
plt.subplot(122); plt.imshow(cv2.cvtColor(img_color_eq, cv2.COLOR_BGR2RGB)); plt.title("Enhanced Color")
plt.show()



~~

---

##  Output

<img width="1187" height="531" alt="Screenshot 2026-08-21 085301" src="https://github.com/user-attachments/assets/c9b0f4e4-3fc2-4d3c-8a91-c9881e132f4b" />



<img width="630" height="277" alt="Screenshot 2026-08-21 085311" src="https://github.com/user-attachments/assets/9e5bd9b2-e4ca-4b03-807d-d352df308826" />



<img width="929" height="659" alt="Screenshot 2026-08-21 085359" src="https://github.com/user-attachments/assets/d8d7f713-9afe-4773-84ec-0695c1dcf610" />



---

## Result

Thus, histogram equalization is successfully performed on both grayscale and color images using OpenCV. The contrast and brightness of the images are significantly improved, enhancing visual quality and feature visibility.
