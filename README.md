## Image Acquisition using Web Camera

## Aim:
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm

Step 1:
Use cv2.VideoCapture(0) to access web camera.

Step 2:
Use cv2.imread to read the video or image.

Step 3:
Use cv2.imwrite to save the image.

Step 4:
Use cv2.imshow to show the video.

Step 5:
End the program and close the output video window by pressing 'q'.

## Program:
``` Python
### Developed By: HENRIPRASATH S
### Register No: 212223230077

## i) Write the frame as JPG file

import cv2

cap = cv2.VideoCapture(0)
ret, frame = cap.read()
if ret:
    cv2.imwrite("captured_frame.jpg", frame)
cap.release()

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

![Screenshot 2025-04-29 221746](https://github.com/user-attachments/assets/5f780a64-c91a-47cf-bc49-f349a5e3c5ec)


### ii) Display the video

![Screenshot 2025-04-29 221746](https://github.com/user-attachments/assets/dda7c824-a720-46b3-9b42-69dd9ff94785)


### iii) Display the video by resizing the window

![Screenshot 2025-04-29 221754](https://github.com/user-attachments/assets/1095614c-c2eb-4b2b-b467-edb9bc185e62)


### iv) Rotate and display the video

![Screenshot 2025-04-29 221800](https://github.com/user-attachments/assets/3d35837a-c366-43b4-a9de-f862443afd65)


## Result:
Thus the image is accessed from webcamera and displayed using openCV.
