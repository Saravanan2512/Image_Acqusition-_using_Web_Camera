
Aim:
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
```
Import CV2,numpy and the other required libraries
```

### Step 2:
<br>Create an instance of Video Capture and save the displayed image</br>

### Step 3:
<br>Capture video and using numpy resize the shape of the window and display the video</br>
### Step 4:
<br>Rotate the captured image by 180*</br>

## Program:
```
### Developed By: Saravanan H
### Register No: 212223230194

## i) Write the frame as JPG file

import cv2
obj = cv2.VideoCapture(0)
while True:
    cap,frame = obj.read()
    if not cap:
        break
    cv2.imshow('video',frame)
    cv2.imwrite('picture.jpg',frame)
    if cv2.waitKey(1) == ord('q'):
        break
obj.release()
cv2.destroyAllWindows()

## ii) Display the video

img = cv2.VideoCapture(0)
while True:
    image,frame = img.read()
    cv2.imshow('pic',frame) 
    if cv2.waitKey(1)==ord('q'):
        break
img.release()
cv2.destroyAllWindows()

## iii) Display the video by resizing the window

import numpy as np
capture = cv2.VideoCapture(0)
while True:
    ret,frame=capture.read()
    if not ret:
        break
    height,width = frame.shape[:2]
    smaller_frame=cv2.resize(frame,(width//2,height//2))
    image = np.zeros((height,width,3),dtype=np.uint8)
    image[:height//2,:width//2]=smaller_frame
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=smaller_frame
    image[height//2:, width//2:]=smaller_frame

    cv2.imshow('PIC',smaller_frame)
    
    if cv2.waitKey(1)==ord('q'):
        break
capture.release()
cv2.destroyAllWindows()

## iv) Rotate and display the video

capture = cv2.VideoCapture(0)
while True:
    ret,frame=capture.read()
    if not ret:
        break
    height,width = frame.shape[:2]
    smaller_frame = cv2.resize(frame,(width//2,height//2))
    image = np.zeros((height,width,3),dtype=np.uint8)

    image[:height//2,:width//2]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=smaller_frame
    image[height//2:, width//2:]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
    
    cv2.imshow('ROTATE_PIC',image)
    if cv2.waitKey(1) == ord('q'):
        break
capture.release()
cv2.destroyAllWindows()

```





## Output

### i) Write the frame as JPG image
![Screenshot 2025-04-29 090020](https://github.com/user-attachments/assets/48b40bfb-a981-4652-8a8e-8732d48529c8)



### ii) Display the video

![Screenshot 2025-04-29 090141](https://github.com/user-attachments/assets/587a5354-0d8c-4530-9fa2-0a6eadbb2855)

### iii) Display the video by resizing the window

![Screenshot 2025-04-29 090253](https://github.com/user-attachments/assets/ac03dfaa-95fe-45d0-a893-654011faab3a)



### iv) Rotate and display the video
![Uploading Screenshot 2025-04-29 090401.png…]()





## Result:
Thus the image is accessed from webcamera and displayed using openCV.
