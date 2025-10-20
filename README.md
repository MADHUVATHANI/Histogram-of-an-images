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
# Developed By: MADHUVATHANI V
# Register Number: 212223040107

import cv2
import numpy as np
import matplotlib.pyplot as plt
img = cv2.imread('a.jpg', cv2.IMREAD_GRAYSCALE)
# Display the images.
plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()
# Display the images
plt.hist(img.ravel(),256,range = [0, 256]);
plt.title('Original Image')
plt.show()
img_eq = cv2.equalizeHist(img)
# Display the images.
plt.hist(img_eq.ravel(), 256, range = [0, 256])
plt.title('Equalized Histogram')
# Display the images.
plt.imshow(img_eq, cmap='gray')
plt.title('Original Image')
plt.show()
# Read the color image.
img = cv2.imread('parrot.jpg', cv2.IMREAD_COLOR)
import cv2
img = cv2.imread('Chennai_Central.jpg')  # make sure extension is correct
if img is None:
    print("Image not loaded. Check path or filename.")
else:
    img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
    print("Converted to HSV successfully.")
# Convert to HSV.
img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
# Perform histogram equalization only on the V channel, for value intensity.
img_hsv[:,:,2] = cv2.equalizeHist(img_hsv[:, :, 2])
# Convert back to BGR format.
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)
plt.imshow(img_eq[:,:,::-1]); plt.title('Equalized Image');plt.show()
plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized');plt.show()
# Display the images.
#plt.figure(figsize = (20,10))
plt.subplot(221); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(222); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')
plt.subplot(223); plt.hist(img.ravel(),256,range = [0, 256]); plt.title('Original Image')
plt.subplot(224); plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized');plt.show()
# Display the histograms.
plt.figure(figsize = [15,4])
plt.subplot(121); plt.hist(img.ravel(),256,range = [0, 256]); plt.title('Original Image')
plt.subplot(122); plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized')
```
## Output:
<img width="749" height="481" alt="image" src="https://github.com/user-attachments/assets/77c38ec2-2b0a-4c20-bd51-c40e543c43e8" />
<img width="736" height="539" alt="image" src="https://github.com/user-attachments/assets/564b2f6e-daa2-4ee3-968d-17678b4871e2" />
<img width="724" height="529" alt="image" src="https://github.com/user-attachments/assets/59fe7c89-da3e-4c56-b63b-64ca22f602b5" />
<img width="717" height="486" alt="image" src="https://github.com/user-attachments/assets/3facf81c-e507-422b-a273-abb1524e512f" />
<img width="725" height="485" alt="image" src="https://github.com/user-attachments/assets/b7b2e313-0363-43ed-b36c-61dd1e58f9f8" />
<img width="730" height="541" alt="image" src="https://github.com/user-attachments/assets/15ca813a-90aa-41b6-8943-3a7d176237db" />
<img width="1365" height="437" alt="image" src="https://github.com/user-attachments/assets/1a59d8b7-570d-454f-8178-aae2e3f53bef" />
<img width="1390" height="698" alt="image" src="https://github.com/user-attachments/assets/b7026c30-bdc4-4b55-adcc-118e792fb779" />

## Result: 
Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.
