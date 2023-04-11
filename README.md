# Histogram and Histogram Equalization of an image
## Aim
To obtain a histogram for finding the frequency of pixels in an Image with pixel values ranging from 0 to 255. Also write the code using OpenCV to perform histogram equalization.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import cv2, matplotlib.py libraries and display the saved images using cv2.imshow().

### Step2:
Use cv2.calcHist(images, channels, mask, histSize, ranges[, hist[, accumulate]]) to find the histogram of the image.

### Step3:
Plot the image and its stem plots using the plt.show() and plt.stem() functions.

### Step4:
Equalize the grayscale image using the in-built function cv2.equalizeHist().

### Step5:
Print the original and equalized image using cv2.imshow() and end the program.

## Program:
```
# Developed By: M.Suwetha
# Register Number: 212221230112
import cv2
import matplotlib.pyplot as plt

# Write your code to find the histogram of gray scale image and color image channels.
gray_image = cv2.imread("bb.jpg",0)
color_image = cv2.imread("ab.jpg",-1)
cv2.imshow("Gray Image",gray_image)
cv2.imshow("Colour Image",color_image)
cv2.waitKey(0)
cv2.destroyAllWindows()

# Display the histogram of gray scale image and any one channel histogram from color image
color_hist = cv2.calcHist([color_image],[0],None,[256],[0,256])
plt.imshow(color_image)
plt.show()
plt.title("Histogram of Color Image - Green Channel")
plt.xlabel("Intensity Value")
plt.ylabel("Pixel Count")
plt.stem(color_hist)
plt.show()

gray_hist = cv2.calcHist([gray_image],[0],None,[256],[0,256])
plt.figure()
plt.imshow(gray_image)
plt.show()
plt.title("Histogram")
plt.xlabel("Grayscale Value")
plt.ylabel("Pixel Count")
plt.stem(gray_hist)
plt.show()


# Write the code to perform histogram equalization of the image. 

gray_image = cv2.imread("gray.jpg",0)
cv2.imshow("Gray Image",gray_image)
equ = cv2.equalizeHist(gray_image)
cv2.imshow("Equalized Image",equ)
cv2.waitKey(0)
cv2.destroyAllWindows
```
## Output:
### Input Grayscale Image and Color Image
![i-3](https://user-images.githubusercontent.com/94165336/231243946-f4c47737-86ab-481f-b6a0-23ab8ecee133.png)


### Histogram of Grayscale Image and any channel of Color Image
![i-4](https://user-images.githubusercontent.com/94165336/231244002-b9ea0217-a413-4af2-b863-e8d4e64eb333.png)

![i-5](https://user-images.githubusercontent.com/94165336/231244313-11c91cb3-c2fc-4653-8697-58054497200e.png)

### Histogram Equalization of Grayscale Image
![i-6](https://user-images.githubusercontent.com/94165336/231244084-7c8386c9-7f56-42bf-92b4-d2b7bb7a06ba.png)


## Result: 
Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.
