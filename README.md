# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm
### Step1:
Import the necessary packages.

### Step2:
Create the Text using cv2.putText.

### Step3:
Create the Global thresholding to segment the image.

### Step4:
Create Adaptive thresholding to segment the image.

### Step5:
Otsu's method to segment the image.

### Step6:
End the program.

## Program
```
# Load the necessary packages
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Read the Image and convert to grayscale
image=cv2.imread("cat.jpeg")
plt.imshow(image)
plt.title('original image')
plt.axis('off')
gray_img=cv2.cvtColor(image,cv2.COLOR_BGR2GRAY)
plt.imshow(gray_img,'gray')
plt.title('Gray image')
plt.axis('off')

# Use Global thresholding to segment the image
ret,thresh_img1=cv2.threshold(gray_img,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(gray_img,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(gray_img,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(gray_img,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(gray_img,100,255,cv2.THRESH_TRUNC)

# Use Adaptive thresholding to segment the image
thresh_img7=cv2.adaptiveThreshold(gray_img,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(gray_img,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)

# Use Otsu's method to segment the image 
ret,thresh_img6=cv2.threshold(gray_img,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)

# Display the results
titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[gray_img,thresh_img1,thresh_img2,thresh_img3,thresh_img4,thresh_img5,thresh_img6,thresh_img7,thresh_img8]

for i in range(0,9):
    plt.figure(figsize=(5,5))
    plt.subplot(1,2,1)
    plt.title("Original Image")
    plt.imshow(image)
    plt.axis("off")
    plt.subplot(1,2,2)
    plt.title(titles[i])
    plt.imshow(cv2.cvtColor(images[i],cv2.COLOR_BGR2RGB))
    plt.axis("off")
    plt.show()
```
## Output

### Original Image
![170170536-8edc137b-bb84-4a04-8be5-e0d7bcb4dd75](https://github.com/MOHAMED-FAREED-22001617/THRESHOLDING/assets/121412904/a141492d-2a1e-42ab-8cc7-71ad8b33d482)


### Global Thresholding

![170170543-c7621dfe-323b-46cf-8ec0-a67a13a3f60b](https://github.com/MOHAMED-FAREED-22001617/THRESHOLDING/assets/121412904/5bd09732-d195-4d83-b755-99b1019e5d82)

![170170558-066bc197-3872-4421-95c0-d50a4aa614bb](https://github.com/MOHAMED-FAREED-22001617/THRESHOLDING/assets/121412904/a8170f66-71e3-4c64-a93c-331a209b3cb1)


![170170576-f83db0ba-9ae1-4171-9b32-9acd47245041](https://github.com/MOHAMED-FAREED-22001617/THRESHOLDING/assets/121412904/e55e889d-5d0b-478e-b3c3-444a57cdf874)

![170170617-40146bfc-cfed-42da-97b5-4e44242f9823](https://github.com/MOHAMED-FAREED-22001617/THRESHOLDING/assets/121412904/52cf7379-6867-4cfa-9c38-d6c319b88a4d)


![170170754-3c39aa6e-e4da-4b83-9767-9a6e5fa994ba](https://github.com/MOHAMED-FAREED-22001617/THRESHOLDING/assets/121412904/34f772ad-690a-4727-96af-033fe3250b5c)

### Adaptive Thresholding

![170170822-becbd2c0-875e-42a3-a691-18bd550a9d6e](https://github.com/MOHAMED-FAREED-22001617/THRESHOLDING/assets/121412904/f0df5d2f-5cd3-483f-8fe1-6dd7288783b1)

![170170830-a7e73967-c9c7-421b-9ff7-6f3e38226481](https://github.com/MOHAMED-FAREED-22001617/THRESHOLDING/assets/121412904/47548c5b-5154-4a77-9731-7aff1eeb8a5e)

### Optimum Global Thesholding using Otsu's Method
![170170845-e5d0d914-f3c7-4406-a223-a4ce1f52064b](https://github.com/MOHAMED-FAREED-22001617/THRESHOLDING/assets/121412904/2a119b8a-21f6-413a-b71a-1ab5e6c1b056)


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
