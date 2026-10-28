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

```
import cv2
import numpy as np
import matplotlib.pyplot as plt

# ==========================================
# 1. READ IMAGE IN GRAYSCALE
# ==========================================

img_gray = cv2.imread('scenery.png', cv2.IMREAD_GRAYSCALE)

if img_gray is None:
    print("Image not found!")
else:
    print("Image loaded successfully.")


# ==========================================
# 2. DISPLAY GRAYSCALE IMAGE AND HISTOGRAM
# ==========================================

plt.figure(figsize=(12, 5))

plt.subplot(1, 2, 1)
plt.imshow(img_gray, cmap='gray')
plt.title('Grayscale Image')
plt.axis('off')

plt.subplot(1, 2, 2)
plt.hist(img_gray.ravel(), bins=256, range=[0, 256], color='black')
plt.title('Histogram')
plt.xlabel('Pixel Intensity')
plt.ylabel('Frequency')

plt.tight_layout()
plt.show()


# ==========================================
# 3. HISTOGRAM EQUALIZATION
# ==========================================

equalized_img = cv2.equalizeHist(img_gray)

plt.figure(figsize=(12, 10))

# Original image
plt.subplot(2, 2, 1)
plt.imshow(img_gray, cmap='gray')
plt.title('Original Grayscale Image')
plt.axis('off')

# Original histogram
plt.subplot(2, 2, 2)
plt.hist(img_gray.ravel(), bins=256, range=[0, 256], color='black')
plt.title('Original Histogram')
plt.xlabel('Pixel Intensity')
plt.ylabel('Frequency')

# Equalized image
plt.subplot(2, 2, 3)
plt.imshow(equalized_img, cmap='gray')
plt.title('Equalized Image')
plt.axis('off')

# Equalized histogram
plt.subplot(2, 2, 4)
plt.hist(equalized_img.ravel(), bins=256, range=[0, 256], color='blue')
plt.title('Equalized Histogram')
plt.xlabel('Pixel Intensity')
plt.ylabel('Frequency')

plt.tight_layout()
plt.show()


# ==========================================
# 4. READ COLOR IMAGE
# ==========================================

img_color = cv2.imread('scenery.png')

# OpenCV reads images in BGR format.
# Convert BGR to RGB for displaying using Matplotlib.
img_color_rgb = cv2.cvtColor(img_color, cv2.COLOR_BGR2RGB)

plt.figure(figsize=(6, 5))
plt.imshow(img_color_rgb)
plt.title('Original Color Image')
plt.axis('off')
plt.show()


# ==========================================
# 5. SPLIT INTO BLUE, GREEN AND RED CHANNELS
# ==========================================

b, g, r = cv2.split(img_color)


# ==========================================
# 6. HISTOGRAMS OF B, G AND R CHANNELS
# ==========================================

plt.figure(figsize=(12, 8))

# Blue channel histogram
plt.subplot(3, 1, 1)
plt.hist(b.ravel(), 256, [0, 256], color='blue')
plt.title('Blue Channel Histogram')
plt.xlabel('Pixel Intensity')
plt.ylabel('Frequency')

# Green channel histogram
plt.subplot(3, 1, 2)
plt.hist(g.ravel(), 256, [0, 256], color='green')
plt.title('Green Channel Histogram')
plt.xlabel('Pixel Intensity')
plt.ylabel('Frequency')

# Red channel histogram
plt.subplot(3, 1, 3)
plt.hist(r.ravel(), 256, [0, 256], color='red')
plt.title('Red Channel Histogram')
plt.xlabel('Pixel Intensity')
plt.ylabel('Frequency')

plt.tight_layout()
plt.show()


# ==========================================
# 7. DISPLAY INDIVIDUAL COLOR CHANNELS
# ==========================================

plt.figure(figsize=(15, 5))

# Blue channel
plt.subplot(1, 3, 1)
plt.imshow(b, cmap='Blues')
plt.title('Blue Channel')
plt.axis('off')

# Green channel
plt.subplot(1, 3, 2)
plt.imshow(g, cmap='Greens')
plt.title('Green Channel')
plt.axis('off')

# Red channel
plt.subplot(1, 3, 3)
plt.imshow(r, cmap='Reds')
plt.title('Red Channel')
plt.axis('off')

plt.tight_layout()
plt.show()

```

### Developed By:
### Name: Hemapriya P 

### Register No: 21225040126 

---

##  Output

### Grayscale Histogram Equalization

- Original grayscale image is displayed  
- Histogram of original grayscale image is plotted  
- Enhanced image after histogram equalization is displayed  
- Histogram of enhanced grayscale image shows improved contrast

  <img width="1027" height="767" alt="image" src="https://github.com/user-attachments/assets/751abadb-041a-46e9-b20f-563348d73df8" />


### Color Image Histogram Equalization

- Original color image is displayed  
- Histogram of B, G, R channels is plotted  
- Enhanced image after HSV-based equalization is displayed  
- Histogram of enhanced image shows better intensity distribution


<img width="917" height="812" alt="image" src="https://github.com/user-attachments/assets/496e4b54-de31-417e-840d-4938ef376357" />


<img width="1287" height="282" alt="image" src="https://github.com/user-attachments/assets/7d9be433-f119-4747-a085-b95968a0281e" />

---

## Result

Thus, histogram equalization is successfully performed on both grayscale and color images using OpenCV. The contrast and brightness of the images are significantly improved, enhancing visual quality and feature visibility.
