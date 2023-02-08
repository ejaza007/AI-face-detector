# AI-face-detector
AI Face detector in python using Opencv library

## Abstract
This is a beginner AI face detector application project made on python using the library [Opencv](https://github.com/opencv/opencv).

## Working

A trained dataset is used available on the opencv github repository. The data is trained by an algorithm that recognizes faces from the frontal view, more trained data can be found on the repository that is trained for animal faces, side faces.

- The program starts with uploading the trained data and storing it in a variable using a built-in opencv function `cv2.CascadeClassifier('haarcascade_frontalface_default.xml')`.
- To recognize a face from a picture the picture can be stored in a variable using the function `cv2.imgread('image_name.jpeg')`; however I decided to use the app on my webcam for which I used the function `webcam.read()`. 
- The algorithm recognizes the face in grayscale, and by using coordinates of the image resolution. Hence the image was converted to grayscale using `cv2.cvtColor(frame, cv2.COLOR_BGR2GRAY)`, and coordinated were fetched using `face_coordinates = trained_face_data.detectMultiScale(grayscaled_img)`.
- The coordinates are then stored in a tuple and passed in a for-loop that continuously draws a rectangle around the coordinates to show the recognized face. 
- The colour of the rectangle is defined by RGB values (BGR in python) 
```bash
 for (x, y, w, h) in face_coordinates:
        cv2.rectangle(frame, (x, y), (x + w, y + h), (0, 252, 0), 4)
```
- Lastly 
```bash
 cv2.imshow('face detector', frame)
    cv2.waitKey(1)
```
is used for display, the (1) in `cv2.waitKey(1)` is supposed to refresh the display every 1 millisecond to show the output as a video.

### For more info:
- [Trained data](https://github.com/opencv/opencv/tree/4.x/data/haarcascades) 
- [Opencv.org](https://opencv.org/) 
- [Opencv documentation](https://docs.opencv.org/) 

