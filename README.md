# Edge-Detection
## Aim:
To perform edge detection using Sobel, Laplacian, and Canny edge detectors.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
import the required packages

### Step2:
Read the image and cconvert into gray image

### Step3:
remove the noise of the image using gaussian operator

### Step4:
find the sobel edge,laplacian edge,canny edge using the built in modules available in opencv

### Step5:
plot the edged image using matplotlib

 
## Program:
```
# Import the packages
import cv2
import matplotlib.pyplot as plt

# Load the image, Convert to grayscale and remove noise

# load the image
img=cv2.imread("windows.jpg")
# convert to gray scale
gray=cv2.cvtColor(image,cv2.COLOR_BGR2GRAY)
# remove noise
img = cv2.GaussianBlur(gray,(3,3),0)

# SOBEL EDGE DETECTOR

# convolve with proper kernels
sobelx = cv2.Sobel(img,cv2.CV_64F,1,0,ksize=5)
sobely = cv2.Sobel(img,cv2.CV_64F,0,1,ksize=5)
sobelxy = cv2.Sobel(img,cv2.CV_64F,1,1,ksize=5)
#Plot the Sobel edge detector input and output
plt.figure(1)
plt.subplot(2,2,1),plt.imshow(img,cmap = 'gray')
plt.title('Original'), plt.xticks([]), plt.yticks([])
plt.show()
#sobelx
plt.figure(1)
plt.subplot(2,2,1),plt.imshow(sobelx,cmap = 'gray')
plt.title('sobelx'), plt.xticks([]), plt.yticks([])
plt.show()
#sobely
plt.figure(1)
plt.subplot(2,2,1),plt.imshow(sobely,cmap = 'gray')
plt.title('sobely'), plt.xticks([]), plt.yticks([])
plt.show()
#sobelxy
plt.figure(1)
plt.subplot(2,2,1),plt.imshow(sobelxy,cmap = 'gray')
plt.title('sobelxy'), plt.xticks([]), plt.yticks([])
plt.show()


# LAPLACIAN EDGE DETECTOR
laplacian = cv2.Laplacian(img,cv2.CV_64F)
plt.figure(1)
plt.subplot(2,2,1),plt.imshow(laplacian,cmap = 'gray')
plt.title('laplacian_operator'), plt.xticks([]), plt.yticks([])
plt.show()

# CANNY EDGE DETECTOR
canny_edges = cv2.Canny(img, 120, 150)
plt.figure(1)
plt.subplot(2,2,1),plt.imshow(canny_edges,cmap = 'gray')
plt.title('canny_operator'), plt.xticks([]), plt.yticks([])
plt.show()



```
## Output:
### SOBEL EDGE DETECTOR
![op](sobeledge.png)


### LAPLACIAN EDGE DETECTOR
1[op](laplacianedge.png)


### CANNY EDGE DETECTOR
![op](cannyedge.png)

## Result:
Thus the edges are detected using Sobel, Laplacian, and Canny edge detectors.
