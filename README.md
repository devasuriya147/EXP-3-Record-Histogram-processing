# EXP-3-Record-Histogram-processing


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
Read the image `sunimg.jpg` in grayscale format.

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
**Name:** DEVASURYA M

### Register No: 212225230048

```
Import cv2
import numpy as np
import matplotlib.pyplot

img = cv2.imread('sunimg.png', cv2.IMREAD_GRAYSCALE)
plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()
```
<img width="350" height="410" alt="image" src="https://github.com/user-attachments/assets/41c6b6ba-f9a0-47a4-8034-cd5421041a6a" />
```
plt.hist(img.ravel(),256,range = [0, 256]);
plt.title('Original Image')
plt.show()
```

<img width="547" height="403" alt="image" src="https://github.com/user-attachments/assets/e499e3ff-0148-47c3-8656-36b1023449d7" />
```
img_eq = cv2.equalizeHist(img)
plt.hist(img_eq.ravel(), 256, range = [0, 256])
plt.title('Equalized Histogram')

Text(0.5, 1.0, 'Equalized Histogram')
```

<img width="540" height="412" alt="image" src="https://github.com/user-attachments/assets/7fa59694-b9a4-4c11-979c-00237e63a898" />
```
plt.imshow(img_eq, cmap='gray')
plt.title('Original Image')
plt.show()
```
<img width="347" height="411" alt="image" src="https://github.com/user-attachments/assets/6c36e2e5-1abf-4d67-9860-9f0bfa2e4a6d" />
```
img = cv2.imread('sunimg.png', cv2.IMREAD_COLOR)
img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
img_hsv[:,:,2] = cv2.equalizeHist(img_hsv[:, :, 2])
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)
plt.imshow(img_eq[:,:,::-1]); plt.title('Equalized Image');plt.show()
```

<img width="350" height="416" alt="image" src="https://github.com/user-attachments/assets/b863081d-8954-4e03-b3b3-dc392e41774a" />
```

plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized');plt.show()
```

<img width="515" height="411" alt="image" src="https://github.com/user-attachments/assets/6d85c466-1645-4861-945a-ab7c9d148696" />
```
plt.figure(figsize = (20,10))
plt.subplot(221); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(222); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')
plt.show()
```

<img width="1017" height="357" alt="image" src="https://github.com/user-attachments/assets/1d14b776-2342-4c35-85a3-cc12a2810276" />
```
plt.figure(figsize = [15,4])
plt.subplot(121); plt.hist(img.ravel(),256,range = [0, 256]); plt.title('Original Image')
plt.subplot(122); plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized')

Text(0.5, 1.0, 'Histogram Equalized')
```
<img width="1017" height="315" alt="image" src="https://github.com/user-attachments/assets/17d45730-ad9d-4601-abf8-098455314d63" />


```


---

##  Output

### Grayscale Histogram Equalization

- Original grayscale image is displayed  
- Histogram of original grayscale image is plotted  
- Enhanced image after histogram equalization is displayed  
- Histogram of enhanced grayscale image shows improved contrast  

### Color Image Histogram Equalization

- Original color image is displayed  
- Histogram of B, G, R channels is plotted  
- Enhanced image after HSV-based equalization is displayed  
- Histogram of enhanced image shows better intensity distribution  

---

## Result

Thus, histogram equalization is successfully performed on both grayscale and color images using OpenCV. The contrast and brightness of the images are significantly improved, enhancing visual quality and feature visibility.
