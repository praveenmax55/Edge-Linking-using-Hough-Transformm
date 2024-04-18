# Edge-Linking-using-Hough-Transformm
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:

Import all the necessary modules for the program.
### Step2:

Load a image using imread() from cv2 module.
### Step3:

Convert the image to grayscale.
### Step4:

Using Canny operator from cv2,detect the edges of the image.
### Step5:

Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.

## Program:
```
Name : Praveen D
Ref.No : 212222240076
```
```Python

# Read image and convert it to grayscale image
import cv2
import numpy as np
r=cv2.imread('catt.jpg',-1)
gray=cv2.cvtColor(r,cv2.COLOR_BGR2GRAY)
img = cv2.GaussianBlur(gray,(3,3),0)
cv2.imshow('origianl',r)
cv2.waitKey(0)
cv2.destroyAllWindows()
cv2.imshow('gray',gray)
cv2.waitKey(0)
cv2.destroyAllWindows()


# Find the edges in the image using canny detector and display
canny_edges = cv2.Canny(img, 50, 120)
cv2.imshow('canny',canny_edges)
cv2.waitKey(0)
cv2.destroyAllWindows()


# Detect points that form a line using HoughLinesP
lines =cv2.HoughLinesP(canny_edges, 1, np.pi/180,threshold = 15, minLineLength =5 ,
maxLineGap = 7)



# Draw lines on the image
for line in lines:
 x1,y1,x2,y2 = line[0]
 cv2.line(r, (x1,y1),(x2,y2),(255,0,0),3)



# Display the result
cv2.imshow('hough_detected',r)
cv2.waitKey(0)
cv2.destroyAllWindows()



```
## Output

### Input image and grayscale image
![image](https://github.com/praveenmax55/Edge-Linking-using-Hough-Transformm/assets/113497509/7ff82c6e-bc5a-464f-b3fe-8e2959d8fd11)

### Canny Edge detector output
![image](https://github.com/praveenmax55/Edge-Linking-using-Hough-Transformm/assets/113497509/3290841e-d399-4e18-bbd6-a86fd3253791)

### Display the result of Hough transform
![image](https://github.com/praveenmax55/Edge-Linking-using-Hough-Transformm/assets/113497509/c97d56d3-fc61-4f73-936b-6802b026cbe2)

Result:
Thus the program is written with Python and OpenCV to detect lines using Hough transform.
