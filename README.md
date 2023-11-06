# EX-8 EDGE LINKING HOUGH TRANSFORM
### Aim:
To write a Python program to detect the lines using Hough Transform.
### Software Required:
Anaconda - Python 3.7
### Algorithm:
- Step1: Read image and convert it to grayscale image.
- Step2: Find the edges in the image using canny detector and display.
- Step3: Detect points that form a line using HoughLinesP.
- Step4: Draw lines on the image.
- Step5: Display the result.
```
Developed By: Lubindher
Register No: 212222240056
```
### Program:
- Read image and convert it to grayscale image
  ```Python
  import numpy as np
  import cv2
  import matplotlib.pyplot as plt
  img=cv2.imread("blue.jpg",0)
  img_c=cv2.imread("blue.jpg",1)
  img=cv2.resize(img,(200,200))
  img_c=cv2.resize(img_c,(200,200))
  img_c=cv2.cvtColor(img_c,cv2.COLOR_BGR2RGB)
  gray=cv2.cvtColor(img,cv2.COLOR_GRAY2RGB)
  gray = cv2.GaussianBlur(gray,(3,3),0)
  plt.subplot(1,2,1)
  plt.imshow(img_c)
  plt.title("Original Image")
  plt.axis("off")
  plt.subplot(1,2,2)
  plt.imshow(gray)
  plt.title("Gray Image")
  plt.axis("off")
  plt.show()
  ```
  <img height=10% width=55% src="https://github.com/ROHITJAIND/EX-8-EDGE-LINKING-HOUGH-TRANSFORM/assets/118707073/e88f1df9-c32d-48b4-b384-3ef310029b7d">


- Find the edges in the image using canny detector and display
  ```Python
  canny=cv2.Canny(gray,120,150)
  plt.imshow(canny)
  plt.title("Canny Edge Detector")
  plt.axis("off")
  plt.show()
  ```
<img height=17% width=40% src="https://github.com/ROHITJAIND/EX-8-EDGE-LINKING-HOUGH-TRANSFORM/assets/118707073/ee10b805-d935-4dcc-b05e-140faa11bdf9">


- Detect points that form a line using HoughLinesP
  ```Python
  lines=cv2.HoughLinesP(canny,1,np.pi/180,threshold=80,minLineLength=50,maxLineGap=250)
  ```


- Draw lines on the image
  ```Python
  for line in lines:
    x1,y1,x2,y2=line[0]
    cv2.line(img_c,(x1,y1),(x2,y2),(255,0,0),3)
  ```


- Display the result
  ```Python
  plt.imshow(img_c)
  plt.title("Result Image")
  plt.axis("off")
  plt.show()
  ```
<img height=20% width=40% src="https://github.com/ROHITJAIND/EX-8-EDGE-LINKING-HOUGH-TRANSFORM/assets/118707073/e748b6eb-f61d-417b-8f00-87c7fc45207a">

  
## Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform. 
