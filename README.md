# Edge-Linking-using-Hough-Transform
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
# Step1:
Import the packages.

# Step2:
Convert to gray scale.

# Step3:
Use canny edge detector.

# Step4:
Detect lines and apply hough transform.

# Step5:
Display result.

## Program:
```Python
Developed by : Gayathri A
Reg.no:212221230028

# Read image and convert it to grayscale image

import numpy as np
import  cv2
import matplotlib.pyplot as plt

img = cv2.imread("jb.jpg")
img = cv2.GaussianBlur(image,(3,3),0)

plt.axis('off')
plt.imshow(img)
plt.show()


# Find the edges in the image using canny detector and display

edge = cv2.Canny(img,50,50)
plt.imshow(edge,cmap='gray')
plt.title('Edge Image')
plt.xticks([])
plt.yticks([])
plt.show()

# Detect points that form a line using HoughLinesP
lines=cv2.HoughLinesP(edge,1,np.pi/180, threshold=80, minLineLength=40,maxLineGap=250)

# Draw lines on the image
for line in lines:
    x1,y1,x2,y2 = line[0]
    cv2.line(edge,(x1,y1),(x2,y2),(255,0,255),3)

# Display the result
plt.imshow(edge)
plt.axis('off')
plt.show()

```
## Output

### Input image and grayscale image

![d8 1](https://github.com/Gayathriraj18/Edge-Linking-using-Hough-Transform/assets/94154854/4d59f18e-8600-4f08-96a3-89d432b7cd4e)

![d8 2](https://github.com/Gayathriraj18/Edge-Linking-using-Hough-Transform/assets/94154854/ae06fbaf-1f41-4fb5-9a1c-cea756f92280)



### Canny Edge detector output

![d8 3](https://github.com/Gayathriraj18/Edge-Linking-using-Hough-Transform/assets/94154854/16f7fc9d-74cd-4ff1-a53a-6e47b611d673)



### Display the result of Hough transform

![d8 4](https://github.com/Gayathriraj18/Edge-Linking-using-Hough-Transform/assets/94154854/061acad9-4e86-4ad9-a0a3-4d8d33f91e61)




## Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform. 
