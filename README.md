# License plate recognition with EasyOCR


## Used the ["Car License Plate Detection" dataset by andrewmvd](https://www.kaggle.com/datasets/andrewmvd/car-plate-detection)
Example images:
![Examples](https://user-images.githubusercontent.com/40422650/213888623-a8072ee8-77ae-43fb-afe7-04b1e3b10f76.png)


## Load data and grayscale image
![image](https://user-images.githubusercontent.com/40422650/213888665-408791a6-88c7-4511-b472-64b50c857906.png)

## Noise reduction + edge detection
Using a bilateral filter to reduce unwanted noise and smooth out the image without removing edges as the only data we need is the licence plate numbers.
[1] found that the best settings to use are ```cv2.bilateralFilter(image, 11, 17, 17)```



Sources:

[1]
[License Plate Recognition using Raspberry Pi and OpenCV](https://circuitdigest.com/microcontroller-projects/license-plate-recognition-using-raspberry-pi-and-opencv)

[2]
[JaidedAI/EasyOCR](https://github.com/JaidedAI/EasyOCR)

[3]
[OpenCV docs](https://docs.opencv.org/4.x/d4/d13/tutorial_py_filtering.html)
