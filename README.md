# Image Acquisition using Web Camera

### Aim:
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used:
Anaconda - Python 3.7
## Algorithm
### Step 1:
Import the cv2 and numpy package.

### Step 2:
Read the Video frame using the cv2.VideoCapture(0)

### Step 3:
Write the image using imwrite().

### Step 4:
Display the frame using the imshow().

### Step 5:
Divide the frame into halves and assign the smaller frame and Rotate the frame using the cv2.rotate().

## Program:
``` Python
### Developed By:Rakshitha J
### Register No: 212223240135

## i) Write the frame as JPG file

import cv2

cap = cv2.VideoCapture(0)
ret, frame = cap.read()
if ret:
    cv2.imwrite("captured_frame.jpg", frame)
cap.release()
```
```
## ii) Display the video

import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time

cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    frame_rgb = cv2.cvtColor(frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()
```

```
## iii) Display the video by resizing the window

#  iii) Display the video by resizing the window
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    resized_frame = cv2.resize(frame, (100, 150))  # Resize to 320x240
    frame_rgb = cv2.cvtColor(resized_frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()

```

```
## iv) Rotate and display the video

#iv) Rotate and display the video
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    rotated_frame = cv2.rotate(frame, cv2.ROTATE_90_CLOCKWISE)
    frame_rgb = cv2.cvtColor(rotated_frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()


```
## Output:

### Display the video

![Screenshot 2025-04-22 152019](https://github.com/user-attachments/assets/47462b9b-e95c-4cc3-8556-290c4b6aae71)


### Display the video by resizing the window

![Screenshot 2025-04-22 152027](https://github.com/user-attachments/assets/c767a6e0-22f2-4930-b074-11708a7f9641)


### Rotate and display the video

![Screenshot 2025-04-22 152034](https://github.com/user-attachments/assets/81b7c4bb-294f-478e-86fc-a8c85e6eac11)


## Result:
Thus the image is accessed from webcamera and displayed using openCV.
