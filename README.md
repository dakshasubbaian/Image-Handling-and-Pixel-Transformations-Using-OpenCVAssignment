# EXP 1:Image-Handling-and-Pixel-Transformations-Using-OpenCV

## AIM

To write a Python program using OpenCV to perform the following operations:
1. Read and display an image.
2. Adjust the brightness of an image.
3. Modify the contrast of an image.
4. Generate a third image using bitwise operations.
5. Split and merge images in RGB and HSV color spaces.
## SOFTWARE REQUIRED
1. Anaconda – Python 3.7
2. Jupyter Notebook
3. OpenCV (cv2)
4. NumPy
5. Matplotlib
## PROGRAM DEVELOPED BY
```
Name: DAKSHA SUBBAIAN
Register Number: 212223230036
```

## ALGORITHM
1. Read and Display an Image
  Load the image Eagle_in_Flight.jpg in grayscale mode using cv2.imread().
  Print the image width, height, and number of channels.
  Display the image using matplotlib.pyplot.imshow().
  Save the image as a PNG file using cv2.imwrite().
2. Convert and Display Color Image
   Read the saved image and convert it into a color image using cv2.cvtColor().
  Display the color image and print its dimensions.
3. Crop, Resize, and Flip
  Crop the eagle from the image.
  Resize the cropped image by a factor of 2.
  Flip the image horizontally.
4. Annotate Apollo Launch Image
  Read Apollo-11-launch.jpg.
  Add the text:
  Apollo 11 Saturn V Launch, July 16, 1969
  Draw a magenta rectangle around the rocket and launch tower.
  Display the final annotated image.
5. Brightness Adjustment
  Read Boy.jpg.
  Create a matrix of ones using NumPy.
  Increase brightness using cv2.add().
  Decrease brightness using cv2.subtract().
  Display original, brighter, and darker images.
6. Contrast Adjustment
  Multiply pixel values by scaling factors 1.1 and 1.2.
  Generate higher contrast images.
  Display original and modified images.
7. RGB Channel Splitting and Merging
  Split the image into Blue, Green, and Red channels.
  Display each channel separately.
  Merge the channels back into the original image.
8. HSV Channel Splitting and Merging
  Convert the image to HSV color space.
  Split into Hue, Saturation, and Value channels.
  Display each channel.
  Merge the channels and convert back to RGB.

## OUTPUT
### Read and display grayscale and color images.
<img width="945" height="573" alt="image" src="https://github.com/user-attachments/assets/152f87e9-112f-4ec7-8f5a-2994f2f32472" />

### Cropped, resized, and flipped images.
<img width="1216" height="669" alt="image" src="https://github.com/user-attachments/assets/a0b8deb1-a5be-4c4c-89e0-f6a18a80f65a" />

<img width="871" height="579" alt="image" src="https://github.com/user-attachments/assets/b20106e8-b033-44f2-8e40-21a4b5a74f7d" />

<img width="891" height="622" alt="image" src="https://github.com/user-attachments/assets/3f449233-6d27-408b-8295-dadbb856de6b" />

### Apollo 11 image with text and rectangle annotations.
<img width="817" height="471" alt="image" src="https://github.com/user-attachments/assets/0ec401a9-7d08-4350-997d-c8dfe045c026" />

### Brighter and darker versions of Boy.jpg.
<img width="1220" height="357" alt="image" src="https://github.com/user-attachments/assets/5805c7b2-8485-42b9-b9a2-59ac31cd1d1e" />


### Higher contrast images.
<img width="1207" height="331" alt="image" src="https://github.com/user-attachments/assets/a399f032-ad7c-4621-85a5-ecc69acec9e0" />

### RGB and HSV channels displayed separately.

<img width="1052" height="753" alt="image" src="https://github.com/user-attachments/assets/4f340984-d3a2-4ce2-997c-6617cad71d50" />

<img width="966" height="752" alt="image" src="https://github.com/user-attachments/assets/8b306baf-b1ac-40b4-aeb7-571bd2293a0a" />


## RESULT

Thus, the Python program was successfully implemented using OpenCV to read and display images, adjust brightness and contrast, and split and merge images in RGB and HSV color spaces.
