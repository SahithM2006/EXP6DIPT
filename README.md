## Exp-6 Record EDGE DETECTION
## Aim
To perform edge detection using Sobel, Roberts, Prewitt, Laplacian, and Canny edge detectors.

## Software Required
Anaconda – Python 3.7
Jupyter Notebook / VS Code
OpenCV (cv2)
NumPy
Matplotlib
## ⚙️ Algorithm
Step 1:
Import all the necessary modules for the program.

Step 2:
Load an image using cv2.imread().

Step 3:
Convert the image to grayscale.

Step 4:
Apply Sobel operator using OpenCV to detect edges.

Step 5:
Apply Prewitt operator using custom kernels.

Step 6:
Apply Roberts operator using custom kernels.

Step 7:
Apply Laplacian operator using OpenCV.

Step 8:
Apply Canny edge detector using OpenCV.

Step 9:
Display all edge-detected images for comparison.

## Developed By
Name: SAHITH M
Register No: 212224230236

## OUTPUT
```
import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread('spidey.jpg') 
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Original Image')
plt.axis('off')
```
<img width="742" height="454" alt="image" src="https://github.com/user-attachments/assets/0e12a995-7e96-4407-ad02-3a6e78c2b106" />

## Sobel Edge Detector
```
sobel_x = cv2.Sobel(gray_image, cv2.CV_64F, 1, 0, ksize=5)  
sobel_y = cv2.Sobel(gray_image, cv2.CV_64F, 0, 1, ksize=5)  
sobel_combined = cv2.magnitude(sobel_x, sobel_y)  
plt.imshow(sobel_combined, cmap='gray')
plt.title('Sobel Edge Detection')
plt.axis('off')
```
<img width="687" height="432" alt="image" src="https://github.com/user-attachments/assets/b3843d4f-3dd1-4535-a47e-5672a18e4c2f" />

## Laplacian Edge Detection
```
laplacian = cv2.Laplacian(gray_image, cv2.CV_64F)

plt.imshow(laplacian, cmap='gray')
plt.title('Laplacian Edge Detection')
plt.axis('off')
plt.show()
```
<img width="682" height="573" alt="image" src="https://github.com/user-attachments/assets/709de830-a27a-4f5b-a1b0-8bf030de1f6d" />

## Canny Edge Detection
```
Canny_edges = cv2.Canny(gray_image, 50, 150)
plt.imshow(Canny_edges, cmap='gray')
plt.title('Canny Edge Detection')
plt.axis('off')
plt.show()
```
<img width="694" height="410" alt="image" src="https://github.com/user-attachments/assets/94f8f802-9b6f-4515-b803-d5f42dbdfdd8" />

## Prewitt Edge Detection
```
image = cv2.imread("spidey.jpg")

gray = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

prewitt_x = np.array([[1, 0, -1],
                      [1, 0, -1],
                      [1, 0, -1]])

prewitt_y = np.array([[1, 1, 1],
                      [0, 0, 0],
                      [-1, -1, -1]])

prewitt_x_edge = cv2.filter2D(gray, -1, prewitt_x)
prewitt_y_edge = cv2.filter2D(gray, -1, prewitt_y)

prewitt = cv2.magnitude(prewitt_x_edge.astype(np.float32),
                        prewitt_y_edge.astype(np.float32))

plt.imshow(prewitt, cmap='gray')
plt.title('Prewitt Edge Detection')
plt.axis('off')
plt.show()
```
<img width="667" height="400" alt="image" src="https://github.com/user-attachments/assets/c7896189-0dff-41a2-8236-f24fe0f1f984" />
## Result
Thus, edges are successfully detected using Sobel, Prewitt, Roberts, Laplacian, and Canny edge detection techniques. Each method highlights edges differently based on gradient and intensity variations, improving feature extraction and analysis.
