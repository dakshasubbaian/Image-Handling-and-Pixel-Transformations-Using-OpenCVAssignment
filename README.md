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
## Name: DAKSHA SUBBAIAN
## Register Number: 212223230036

## ALGORITHM
Step 1: Load an image from your local directory and display it.

Step 2: Create a matrix of ones (with data type float64) to adjust brightness.

Step 3: Create brighter and darker images by adding and subtracting the matrix from the original image. Display the original, brighter, and darker images.

Step 4: Modify the image contrast by creating two higher contrast images using scaling factors of 1.1 and 1.2 (without overflow fix). Display the original, lower contrast, and higher contrast images.

Step 5: Split the image (boy.jpg) into B, G, R components and display the channels
## PROGRAM
```
import cv2
import matplotlib.pyplot as plt
img = cv2.imread('PIC.jpeg', cv2.IMREAD_COLOR)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
plt.imshow(img_rgb, cmap='viridis')  # You can change 'viridis' to another cmap or use None for RGB images
plt.title("Original Image")
plt.axis('off')  # Removes axis ticks and labels
plt.show()
image = cv2.imread('pic.jpeg')
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img_rgb.shape
line_img = cv2.line(img_rgb, (0, 0), (768, 600), (255, 0, 0), 2)
plt.imshow(line_img, cmap='viridis')  
plt.title("Image with Line")
plt.axis('off')  
plt.show()
image = cv2.imread('pic.jpeg')
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img_rgb.shape
circle_img = cv2.circle(img_rgb,(400,300),150,(255,0,0),10)
plt.imshow(circle_img, cmap='viridis')  
plt.title("Image with Circle")
plt.axis('off')  
plt.show()
image = cv2.imread('pic.jpeg') 
# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img.shape
rectangle_img = cv2.rectangle(img_rgb, (0, 0), (768, 600), (0, 0, 255), 10) 
plt.imshow(rectangle_img, cmap='viridis')  
plt.title("Image with Rectangle")
plt.axis('off')  
plt.show()
image = cv2.imread('pic.jpeg') 
# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
text_img = cv2.putText(img_rgb, "OpenCV Drawing", (10, 30), cv2.FONT_HERSHEY_SIMPLEX, 1, (255, 255, 255), 10)  ## cv2.putText(image, text, position, font, font_scale, color, thickness)
plt.imshow(text_img, cmap='viridis')  
plt.title("Image with Text")
plt.axis('off')  
plt.show()
image = cv2.imread('pic.jpeg')
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
plt.imshow(image_rgb)
plt.title("Original RGB Image")
plt.axis("off")
image_hsv = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2HSV)
plt.imshow(image_hsv)
plt.title("HSV Image")
plt.axis("off")
image_gray = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2GRAY)
plt.imshow(image_gray, cmap='gray')
plt.title("Grayscale Image")
plt.axis("off")
image_ycrcb = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2YCrCb)
plt.imshow(image_ycrcb)
plt.title("YCrCb Image")
plt.axis("off")
image_hsv_to_rgb = cv2.cvtColor(image_hsv, cv2.COLOR_HSV2RGB)
plt.imshow(image_hsv_to_rgb)
plt.title("HSV to RGB Image")
plt.axis("off")
image[200:500, 200:500] = [255, 255, 255]  # Rows: 200-499, Columns: 200-499
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
plt.imshow(image_rgb)
plt.title("Image with 300x300 White Block")
plt.axis("off")
plt.show()
image = cv2.imread('pic.jpeg')
image.shape
roi = image[50:350, 50:350]  # Rows: 50-349, Columns: 50-349
# Convert BGR to RGB for displaying with Matplotlib
roi_rgb = cv2.cvtColor(roi, cv2.COLOR_BGR2RGB)
# Display the cropped region (ROI)
plt.imshow(roi_rgb)
plt.title("Cropped Region of Interest (ROI)")
plt.axis("off")
plt.show()
# Load the image
image = cv2.imread('pic.jpeg')
# Flip the image horizontally (left-right)
flipped_horizontally = cv2.flip(image, 1)
# Convert BGR to RGB for displaying with Matplotlib
flipped_horizontally_rgb = cv2.cvtColor(flipped_horizontally, cv2.COLOR_BGR2RGB)
# Horizontal flip
plt.imshow(flipped_horizontally_rgb)
plt.title("Flipped Horizontally")
plt.axis("off")
# Flip the image vertically (up-down)
flipped_vertically = cv2.flip(image, 0)
# Convert BGR to RGB for displaying with Matplotlib
flipped_vertically_rgb = cv2.cvtColor(flipped_vertically, cv2.COLOR_BGR2RGB)
# Vertical flip
plt.imshow(flipped_vertically_rgb)
plt.title("Flipped Vertically")
plt.axis("off")
```
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
