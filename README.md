# Ex. No: 5 – Implementation of Filters
### Developed By : HARISH KUMAR S
### Register Number : 212224230091
### Aim :
To implement various image filtering techniques using Python and OpenCV to smooth images, reduce noise, and enhance image details.
### Requirements :
Hardware Requirements:
- Computer or Laptop
- Minimum 4 GB RAM
Software Requirements:
- Python
- Jupyter Notebook
- OpenCV
- NumPy
- Matplotlib
### Procedure :
1. Import the required libraries such as OpenCV, NumPy, and Matplotlib.
2. Read the input image using cv2.imread().
3. Convert the image from BGR to RGB format.
4. Apply an Average Filter using a predefined kernel.
5. Apply a Weighted Average Filter to smooth the image.
6. Apply a Gaussian Filter to reduce image noise.
7. Apply a Median Filter to remove noise while preserving edges.
8. Apply a Laplacian Kernel to highlight image details.
9. Apply the Laplacian Operator to detect edges.
10. Display the original and filtered images using Matplotlib.

### Program : 
```python
import cv2
import matplotlib.pyplot as plt
import numpy as np
image1=cv2.imread("ex.jpg")
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)
kernel=np.ones((11,11),np.float32)/169
image3=cv2.filter2D(image2,-1,kernel)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("on")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Average Filter Image")
plt.axis("on")
plt.show()
```
```python
kernel1=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)
image3=cv2.filter2D(image2,-1,kernel1)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("on")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Weighted Average Filter Image")
plt.axis("on")
plt.show()
```
```python
gaussian_blur=cv2.GaussianBlur(image2,(33,33),0,0)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("on")
plt.subplot(1,2,2)
plt.imshow(gaussian_blur)
plt.title("Gaussian Blur")
plt.axis("on")
plt.show()
```
```python
median=cv2.medianBlur(image2,13)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("on")
plt.subplot(1,2,2)
plt.imshow(median)
plt.title("Median Blur")
plt.axis("on")
plt.show()
```
```python
kernel2=np.array([[-1,-1,-1],[2,-2,1],[2,1,-1]])
image3=cv2.filter2D(image2,-1,kernel2)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("on")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Laplacian Kernel")
plt.axis("on")
plt.show()
```
```python
laplacian=cv2.Laplacian(image2,cv2.CV_64F)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("on")
plt.subplot(1,2,2)
plt.imshow(laplacian)
plt.title("Laplacian Operator")
plt.axis("on")
plt.show()
```

### Output : 
<img width="887" height="561" alt="Screenshot 2026-11-17 235030" src="https://github.com/user-attachments/assets/7b78afa5-fbca-4297-8364-468fe62a3797" />



<img width="657" height="418" alt="Screenshot 2026-11-17 235039" src="https://github.com/user-attachments/assets/23c8be63-8be0-44b8-8124-29a96d0bf998" />

<img width="620" height="417" alt="Screenshot 2026-11-17 235047" src="https://github.com/user-attachments/assets/eeb05432-2afb-410c-8b89-ad041e3d6a74" />


<img width="871" height="570" alt="Screenshot 2026-11-17 235056" src="https://github.com/user-attachments/assets/04f11b0b-2420-4728-8273-d1a1e0dfe3d1" />



<img width="631" height="416" alt="Screenshot 2026-11-17 235104" src="https://github.com/user-attachments/assets/3731a8ea-0469-45b3-b2a0-cc31198adc4f" />


<img width="630" height="411" alt="Screenshot 2026-11-17 235112" src="https://github.com/user-attachments/assets/2d2b93cc-029b-443d-879d-d372b093da7a" />


### Result :
Thus, various image filtering techniques such as Average Filter, Weighted Average Filter, Gaussian Blur, Median Blur, and Laplacian Operator were successfully implemented using Python and OpenCV. The filtered images were displayed and their effects were observed.
