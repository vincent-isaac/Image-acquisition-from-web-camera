# Image-Acquisition-from-Web-Camera
## Aim
 
Aim:
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations. <br>
i) Write the frame as JPG <br>
ii) Display the video <br>
iii) Display the video by resizing the window <br>
iv) Rotate and display the video <br>

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:Use VideoCapture(0) to access web camera
<br>

### Step 2: Use imread to read the video or image
<br>

### Step 3:Use imwrite to save the image
<br>

### Step 4:Use imshow to show the video
<br>

### Step 5:End the program and close the output video windows by pressing 'q'.
<br>

## Program:
``` Python
### Developed By:J Vincent isaac jeyaraj
### Register No:212220230060

## i) Write the frame as JPG file
import cv2
import numpy as np
cap=cv2.VideoCapture(0)
ret,frame=cap.read()
cv2.imwrite("live.jpg",frame) 
cap.release() 
cv2.destroyAllWindows()



## ii) Display the video
import cv2 
import numpy as np 
cap=cv2.VideoCapture(0) 
while True: 
    ret,frame=cap.read()
    cv2.imshow('frame',frame)
    if cv2.waitKey(1)==ord('q'): 
        break 
cap.release()
cv2.destroyAllWindows()



## iii) Display the video by resizing the window
import cv2 
import numpy as np 
cap=cv2.VideoCapture(0) 
while True: 
    ret,frame=cap.read()
    width=int(cap.get(3)) 
    height=int(cap.get(4)) 
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2,:width//2]=smaller_frame 
    image[height//2: , :width//2]=smaller_frame
    image[:height//2,width//2:]= smaller_frame 
    image[height//2:,width//2:]=smaller_frame
    cv2.imshow('frame',image) 
    if cv2.waitKey(1)==ord('q'): 
        break 
cap.release()  
cv2.destroyAllWindows()




## iv) Rotate and display the video
import cv2 
import numpy as np 
cap=cv2.VideoCapture(0) 
while True: 
    ret,frame=cap.read()
    width=int(cap.get(3)) 
    height=int(cap.get(4)) 
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2,:width//2]=image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180) 
    image[height//2: , :width//2]=smaller_frame
    image[:height//2,width//2:]= image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180) 
    image[height//2:,width//2:]=smaller_frame
    cv2.imshow('frame',image) 
    if cv2.waitKey(1)==ord('q'): 
        break 
cap.release()
cv2.destroyAllWindows()


```
## Output

### i) Write the frame as JPG image
</br>![Screenshot (20)](https://user-images.githubusercontent.com/75234588/162613622-0f1b4d6e-8784-4a32-908a-5d072feb92b9.png)
</br>


### ii) Display the video
</br>![Screenshot (17)](https://user-images.githubusercontent.com/75234588/162613630-aead3d8d-a79c-4aba-b749-264362aee83b.png)
</br>


### iii) Display the video by resizing the window
</br>![Screenshot (18)](https://user-images.githubusercontent.com/75234588/162613639-08bb657e-5fb1-40f3-8a8e-b108ee7d3261.png)
</br>



### iv) Rotate and display the video
</br>![Screenshot (19)](https://user-images.githubusercontent.com/75234588/162613643-c4c2d884-bbd3-4721-9e59-f8366fe5ff20.png)
</br>





## Result:
Thus the image is accessed from webcamera and displayed using openCV.
