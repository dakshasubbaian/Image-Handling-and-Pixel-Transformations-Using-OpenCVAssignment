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

<img width="322" height="508" alt="image" src="https://github.com/user-attachments/assets/5266924c-50a2-47d0-b92e-8661ea32e08c" />

<img width="331" height="507" alt="image" src="https://github.com/user-attachments/assets/189952a2-2a21-47f8-a32b-87a181e3f546" />

<img width="323" height="506" alt="image" src="https://github.com/user-attachments/assets/04116a6e-8e3a-44c7-b9a2-fc83d45e9a55" />

<img width="332" height="510" alt="image" src="https://github.com/user-attachments/assets/00f79b14-5f45-4a98-a7a0-cd98453d341d" />

<img width="328" height="506" alt="image" src="https://github.com/user-attachments/assets/eed77c2e-bcef-4026-9f94-0aeeab950129" />

<img width="328" height="506" alt="image" src="https://github.com/user-attachments/assets/d649642f-23c8-4f51-b208-9a800c693174" />

<img width="328" height="506" alt="image" src="https://github.com/user-attachments/assets/da2784cc-aaef-4015-8ef3-0c889e8f93d7" />

<img width="330" height="503" alt="image" src="https://github.com/user-attachments/assets/d4c9733d-d11a-4bc3-9aa4-29ddd40ec3d2" />

<img width="323" height="507" alt="image" src="https://github.com/user-attachments/assets/5c69f61a-1a74-44b3-bfbe-2bc4278286c4" />

<img width="330" height="508" alt="image" src="https://github.com/user-attachments/assets/80bf1253-1f8e-454c-802d-ae8e6c61ace6" />

<img width="367" height="510" alt="image" src="https://github.com/user-attachments/assets/2b055453-479b-43d4-9581-c57cf49e94ec" />

<img width="615" height="507" alt="image" src="https://github.com/user-attachments/assets/a5a4fd92-ccd7-492a-ad61-4e48985bbf7e" />

<img width="478" height="507" alt="image" src="https://github.com/user-attachments/assets/68176fd8-46cf-4aac-a8c3-4d1cf2ed1b94" />

<img width="330" height="510" alt="image" src="https://github.com/user-attachments/assets/0f99435c-eb2c-4a5f-993d-20800fa2c29b" />

<img width="326" height="511" alt="image" src="https://github.com/user-attachments/assets/1954dba6-df48-42fc-96e8-2b5fe20aff73" />

## RESULT

Thus, the Python program was successfully implemented using OpenCV to read and display images, adjust brightness and contrast, and split and merge images in RGB and HSV color spaces.
