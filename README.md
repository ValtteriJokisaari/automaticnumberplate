# License plate recognition with EasyOCR

![image](https://user-images.githubusercontent.com/40422650/213945718-f7cc2d59-4439-4558-8455-ef0420554f11.png)


## Used the ["Car License Plate Detection" dataset by andrewmvd](https://www.kaggle.com/datasets/andrewmvd/car-plate-detection)
Example images:
![Examples](https://user-images.githubusercontent.com/40422650/213888623-a8072ee8-77ae-43fb-afe7-04b1e3b10f76.png)


## Load data and grayscale image
![image](https://user-images.githubusercontent.com/40422650/213888665-408791a6-88c7-4511-b472-64b50c857906.png)

## Noise reduction + edge detection
![image](https://user-images.githubusercontent.com/40422650/213938121-915ce6a2-aa78-4421-93ac-7101f99fcec3.png)

Using a bilateral filter to reduce unwanted noise and smooth out the image without removing edges as the only data we need is the licence plate numbers.
[1] Article found that the best settings to use are ```cv2.bilateralFilter(image, 11, 17, 17)``` where (source_image, diameter of pixel, sigmaColor, sigmaSpace)

Edge detection is easily done by using the OpenCV canny edge method.

## Contours and license plate location points
![image](https://user-images.githubusercontent.com/40422650/213945058-362be24c-e4df-4fc7-915f-622b81ed1e1a.png)

Checks for contours and sorts the 10 biggest.

Add loop to check the list for contours with a rectangle shape (license plate).

Then mask everything else but the license plate.

![image](https://user-images.githubusercontent.com/40422650/213945112-09a0d33f-ec0e-4427-85a8-578f7cdc37e4.png)

## EasyOCR for text

![image](https://user-images.githubusercontent.com/40422650/213945330-e60f53dd-44e6-4675-abc2-a19402ae89d9.png)

Outputs a list containing the text and accuracy.
**'AB 44887', 0.980...**

# Final result
![image](https://user-images.githubusercontent.com/40422650/213945645-90197509-1adb-49a5-a6ac-883a66b318be.png)







Sources:

[1]
[License Plate Recognition using Raspberry Pi and OpenCV](https://circuitdigest.com/microcontroller-projects/license-plate-recognition-using-raspberry-pi-and-opencv)

[2]
[JaidedAI/EasyOCR](https://github.com/JaidedAI/EasyOCR)

[3]
[OpenCV docs](https://docs.opencv.org/4.x/d4/d13/tutorial_py_filtering.html)
