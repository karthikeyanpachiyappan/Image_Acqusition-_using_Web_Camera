# Image Acquisition using Web Camera

## Aim:
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7

## Algorithm
### Step 1:
Import the cv2 and numpy package.
<br>

### Step 2:
Read the Video frame using the cv2.VideoCapture(0)
<br>

### Step 3:
Write the image using imwrite().
<br>

### Step 4:
Display the frame using the imshow().
<br>

### Step 5:
Divide the frame into halves and assign the smaller frame and Rotate the frame using the cv2.rotate().
<br>


## Program:
``` Python
### Developed By:KARTHIKEYAN P
### Register No:212223230102

## i) Write the frame as JPG file

import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time
cap = cv2.VideoCapture(0)
ret, frame = cap.read()
if ret:
    cv2.imwrite("captured_frame.jpg", frame)
cap.release()
captured_image = cv2.imread('captured_frame.jpg')
plt.imshow(captured_image[:,:,::-1])
plt.title('Captured Frame')
plt.axis('off')
plt.show()


## ii) Display the video
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



## iii) Display the video by resizing the window

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


## iv) Rotate and display the video

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
## Output

### i) Write the frame as JPG image
</br>
<img width="693" height="527" alt="Screenshot 2025-10-16 150657" src="https://github.com/user-attachments/assets/8f56d5e8-c70c-46d8-97ea-3d8d2e90f797" />
</br>


### ii) Display the video
</br>
<img width="688" height="490" alt="Screenshot 2025-10-16 150706" src="https://github.com/user-attachments/assets/4dbe1fe3-72c0-447b-a513-d54c01b4d24b" />
</br>


### iii) Display the video by resizing the window
</br>
<img width="396" height="492" alt="Screenshot 2025-10-16 150712" src="https://github.com/user-attachments/assets/746771d8-d9fd-4298-8f4a-45c350d67aed" />
</br>



### iv) Rotate and display the video
</br>
<img width="395" height="480" alt="Screenshot 2025-10-16 150721" src="https://github.com/user-attachments/assets/32aecfbd-4930-451a-833f-0e0c5d42006a" />
</br>





## Result:
Thus the image is accessed from webcamera and displayed using openCV.
