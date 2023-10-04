# EDGE--LINKING-HOUGH-TRANSFORM
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
Using Canny operator from cv2,detect the edges of the image

### Step5:
Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.

### Step6:
Display the image and end the program.
## Program:
```python
Developed by : Lokesh N
Register no : 212222100023
```



# Read image and convert it to grayscale image
```python
import numpy as np
import matplotlib.pyplot as plt
import cv2
image = cv2.imread("road.png",0)
img = cv2.GaussianBlur(image,(3,3),0)
plt.axis('off')
plt.imshow(img)
plt.show()
```


# Find the edges in the image using canny detector and display

```python
import numpy as np
import matplotlib.pyplot as plt
import cv2
image = cv2.imread("road.png",0)
edge = cv2.Canny(image,100,200)
plt.imshow(edge,cmap='gray')
plt.title('Edge Image')
plt.xticks([])
plt.yticks([])
plt.show()
```

# Detect points that form a line using HoughLinesP

```python
edge = cv2.Canny(image,100,200)
lines=cv2.HoughLinesP(edge,1,np.pi/180, threshold=80, minLineLength=50,maxLineGap=250)

```

# Draw lines on the image

```python
for line in lines:
    x1,y1,x2,y2 = line[0]
    cv2.line(edge,(x1,y1),(x2,y2),(255,0,0),3)

```

# Display the result
```python
plt.imshow(edge)
plt.axis('off')
plt.show()

```





## Output

### Input image and grayscale image
![Screenshot from 2023-10-04 14-20-05](https://github.com/lokeshnarayanan/EDGE--LINKING-HOUGH-TRANSFORM/assets/119393019/ed5de8d2-b709-491a-8e08-c3b666c97cfd)


### Canny Edge detector output
![Screenshot from 2023-10-04 14-19-47](https://github.com/lokeshnarayanan/EDGE--LINKING-HOUGH-TRANSFORM/assets/119393019/8b5e34bb-9d2f-4c92-8ade-0a5dfa1c38b1)


### Display the result of Hough transform

![Screenshot from 2023-10-04 14-19-36](https://github.com/lokeshnarayanan/EDGE--LINKING-HOUGH-TRANSFORM/assets/119393019/c3eea0f1-53d7-4cc9-bd57-f7d327d3e358)


## Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform. 
