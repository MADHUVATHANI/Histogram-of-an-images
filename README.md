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
gray_image = cv2.imread('download.jpeg', cv2.IMREAD_GRAYSCALE)
plt.title("Grayscale Image")
plt.imshow(gray_image, cmap='gray')
plt.axis('off')
# Step 3: Plot the histogram of the grayscale image
plt.title("Histogram of Grayscale Image")
plt.hist(gray_image.ravel(), bins=256, color='black', alpha=0.6)
plt.xlim(0, 255)
plt.tight_layout()
plt.show()
# Step 4: Apply histogram equalization using OpenCV
equalized_gray_image = cv2.equalizeHist(gray_image)
# Step 5: Display the histogram of the equalized image
plt.title("Histogram of Equalized Grayscale Image")
plt.hist(equalized_gray_image.ravel(), bins=256, color='black', alpha=0.6)
plt.xlim(0, 255)
# Step 6: Display the enhanced grayscale image
plt.title("Enhanced Grayscale Image")
plt.imshow(equalized_gray_image, cmap='gray')
plt.axis('off')
import cv2
import numpy as np
import matplotlib.pyplot as plt
# Step 1: Get the input color image
color_image = cv2.imread('Eagle_in_Flight.jpg')
# Step 2: Display the input color image
plt.title("Input Color Image")
plt.imshow(cv2.cvtColor(color_image, cv2.COLOR_BGR2RGB))
plt.axis('off')
# Step 3: Plot the histogram of the input color image (combined channels)
# Calculate the histogram for all channels separately
hist_b = cv2.calcHist([color_image], [0], None, [256], [0, 256])
hist_g = cv2.calcHist([color_image], [1], None, [256], [0, 256])
hist_r = cv2.calcHist([color_image], [2], None, [256], [0, 256])
# Plot the histograms
plt.title("Histogram of Input Color Image")
plt.plot(hist_b, color='blue', label='Blue channel')
plt.plot(hist_g, color='green', label='Green channel')
plt.plot(hist_r, color='red', label='Red channel')
plt.show()
plt.title("Histogram Equalized Image")
plt.imshow(equalized_color_image[:,:,::-1])
plt.axis('off')
# Step 4: Apply histogram equalization to each channel of the color image
blue_channel_eq = cv2.equalizeHist(color_image[:, :, 0])
green_channel_eq = cv2.equalizeHist(color_image[:, :, 1])
red_channel_eq = cv2.equalizeHist(color_image[:, :, 2])
# Step 5: Merge the equalized channels back into a color image
equalized_color_image = cv2.merge([blue_channel_eq, green_channel_eq, red_channel_eq])

```
## Output:
### Input Grayscale Image and Color Image
<img width="378" height="384" alt="image" src="https://github.com/user-attachments/assets/f0f97261-92bf-41d7-a9f6-ce32b1109f7d" />

<img width="445" height="382" alt="image" src="https://github.com/user-attachments/assets/63a903f7-2409-4c09-bd96-1987ed53f36b" />

### Histogram of Grayscale Image and any channel of Color Image
<img width="625" height="434" alt="image" src="https://github.com/user-attachments/assets/50d78ac9-cae2-4cf1-b3f2-9aad2685a35e" />

<img width="585" height="413" alt="image" src="https://github.com/user-attachments/assets/b11768ce-6f94-4fdf-8793-074237970e77" />


### Histogram Equalization of Grayscale Image.
<img width="491" height="387" alt="image" src="https://github.com/user-attachments/assets/b0ad4613-b1d6-45e1-9d9c-72e197bdcaa4" />

<img width="605" height="419" alt="image" src="https://github.com/user-attachments/assets/8ecb09a8-4ead-4cfe-ba47-21a57e97219b" />

## Result: 
Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.
