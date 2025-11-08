# Histogram-of-an-images
## Aim
To obtain a histogram for finding the frequency of pixels in an Image with pixel values ranging from 0 to 255. Also write the code using OpenCV to perform histogram equalization.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Read the gray and color image using imread()

### Step2:
Print the image using imshow().



### Step3:
Use calcHist() function to mark the image in graph frequency for gray and color image.

### step4:
Use calcHist() function to mark the image in graph frequency for gray and color image.

### Step5:
The Histogram of gray scale image and color image is shown.


## Program:
```python
# Name : AANKARSH
# Reg.No.: 212223233001
import cv2
import matplotlib.pyplot as plt

gray_image = cv2.imread("bird.jpg", 0)
color_image = cv2.imread("color.jpg")

plt.figure(figsize=(10,5))
plt.subplot(1,2,1)
plt.imshow(gray_image, cmap='gray')
plt.title("Gray Image")
plt.axis("off")
plt.subplot(1,2,2)
color_rgb = cv2.cvtColor(color_image, cv2.COLOR_BGR2RGB)
plt.imshow(color_rgb)
plt.title("Color Image")
plt.axis("off")
plt.show()

hist_gray = cv2.calcHist([gray_image], [0], None, [256], [0, 256])
hist_blue = cv2.calcHist([color_image], [0], None, [256], [0, 256])

plt.figure(figsize=(12, 5))
plt.subplot(1, 2, 1)
plt.plot(hist_gray, color='black')
plt.title("Grayscale Histogram")
plt.xlabel("Pixel Intensity")
plt.ylabel("Count")
plt.subplot(1, 2, 2)
plt.plot(hist_blue, color='blue')
plt.title("Blue Channel Histogram (Color Image)")
plt.xlabel("Pixel Intensity")
plt.ylabel("Count")
plt.tight_layout()
plt.show()

equalized = cv2.equalizeHist(gray_image)

plt.figure(figsize=(10,5))
plt.subplot(1,2,1)
plt.imshow(gray_image, cmap='gray')
plt.title("Original Grayscale")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(equalized, cmap='gray')
plt.title("Equalized Grayscale")
plt.axis("off")
plt.show()

hist_original = cv2.calcHist([gray_image], [0], None, [256], [0, 256])
hist_equalized = cv2.calcHist([equalized], [0], None, [256], [0, 256])

plt.figure(figsize=(12, 5))
plt.subplot(1, 2, 1)
plt.plot(hist_original, color='gray')
plt.title("Original Grayscale Histogram")
plt.subplot(1, 2, 2)
plt.plot(hist_equalized, color='gray')
plt.title("Equalized Grayscale Histogram")
plt.tight_layout()
plt.show() 






```
## Output:
### Input Grayscale Image and Color Image


### Histogram of Grayscale Image and any channel of Color Image



### Histogram Equalization of Grayscale Image.




## Result: 
Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.
