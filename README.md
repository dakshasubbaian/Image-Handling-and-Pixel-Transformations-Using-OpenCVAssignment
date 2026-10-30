# Image-Handling-and-Pixel-Transformations-Using-OpenCV

## AIM:
Write a Python program using OpenCV that performs the following tasks:

1. Read and Display an Image.
2. Adjust the brightness of an image.
3. Modify the image contrast.
4. Generate a third image using bitwise operations.

## Software Required:
- Anaconda - Python 3.7
- Jupyter Notebook (for interactive development and execution)

## Algorithm:

### Step 1:
Load an image from your local directory and display it.

### Step 2:
Create a matrix of ones (with data type float64) to adjust brightness.

### Step 3:
Create brighter and darker images by adding and subtracting the matrix from the original image. Display the original, brighter, and darker images.

### Step 4:
Modify the image contrast by creating two higher contrast images using scaling factors of 1.1 and 1.2 (without overflow fix). Display the original, lower contrast, and higher contrast images.

### Step 5:
Split the image (`cat.jpg`) into B, G, R components and display the channels.

## Program Developed By:
- **Name:** DAKSHA SUBBAIAN
- **Register Number:** 212223230036

## Ex. No. 01

### 1. Read the image (`cat.jpg`) using OpenCV `imread()` as a grayscale image.

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

img = cv2.imread('cat.jpg', cv2.IMREAD_GRAYSCALE)
```

### 2. Print the image width, height & Channel.

```python
height, width = img.shape
channels = 1

print("Width:", width)
print("Height:", height)
print("Channel:", channels)
```

### 3. Display the image using matplotlib `imshow()`.

```python
plt.imshow(img, cmap='gray')
plt.title('Cat - Grayscale')
plt.axis('off')
plt.show()
```

### 4. Save the image as a PNG file using OpenCV `imwrite()`.

```python
cv2.imwrite('cat.png', img)
```

### 5. Read the saved image above as a color image using `cv2.cvtColor()`.

```python
img_color = cv2.cvtColor(img, cv2.COLOR_GRAY2BGR)
```

### 6. Display the Colour image using matplotlib `imshow()` & Print the image width, height & channel.

```python
height, width, channels = img_color.shape

img_rgb = cv2.cvtColor(img_color, cv2.COLOR_BGR2RGB)

plt.imshow(img_rgb)
plt.title('Cat - Color')
plt.axis('off')
plt.show()

print("Width:", width)
print("Height:", height)
print("Channel:", channels)
```

### 7. Crop the image to extract any specific object from the image.

```python
cropped_img = img_color[100:400, 100:500]

cropped_img_rgb = cv2.cvtColor(cropped_img, cv2.COLOR_BGR2RGB)

plt.imshow(cropped_img_rgb)
plt.title('Cropped Cat')
plt.axis('off')
plt.show()
```

### 8. Resize the image up by a factor of 2x.

```python
resized_img = cv2.resize(
    cropped_img,
    None,
    fx=2,
    fy=2,
    interpolation=cv2.INTER_LINEAR
)

resized_img_rgb = cv2.cvtColor(resized_img, cv2.COLOR_BGR2RGB)

plt.imshow(resized_img_rgb)
plt.title('Resized Cat (2x)')
plt.axis('off')
plt.show()
```

### 9. Flip the cropped/resized image horizontally.

```python
flipped_horizontally = cv2.flip(resized_img, 1)

flipped_horizontally_rgb = cv2.cvtColor(
    flipped_horizontally, cv2.COLOR_BGR2RGB
)

plt.imshow(flipped_horizontally_rgb)
plt.title("Flipped Horizontally")
plt.axis("off")
plt.show()
```

### 10. Read in the image (`cat.jpg`).

```python
img = cv2.imread('cat.jpg', cv2.IMREAD_COLOR)

img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

plt.imshow(img_rgb)
plt.title('Original Cat Image')
plt.axis('off')
plt.show()
```

### 11. Add text to the bottom of the image (centered on the image).

```python
text = 'Cat Image'
font_face = cv2.FONT_HERSHEY_PLAIN

height, width = img.shape[:2]
font_scale = 1.5
thickness = 2

text_size = cv2.getTextSize(
    text, font_face, font_scale, thickness
)[0]

x = (width - text_size[0]) // 2
y = height - 20

cv2.putText(
    img,
    text,
    (x, y),
    font_face,
    font_scale,
    (255, 255, 255),
    thickness,
    cv2.LINE_AA
)
```

### 12. Draw a magenta rectangle around a specific area of the image.

```python
rect_color = (255, 0, 255)

start_point = (100, 100)
end_point = (400, 400)

cv2.rectangle(
    img,
    start_point,
    end_point,
    rect_color,
    2
)
```

### 13. Display the final annotated image.

```python
img_annotated_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

plt.imshow(img_annotated_rgb)
plt.title('Annotated Cat Image')
plt.axis('off')
plt.show()
```

### 14. Read the image (`cat.jpg`).

```python
img = cv2.imread('cat.jpg', cv2.IMREAD_COLOR)

plt.imshow(cv2.cvtColor(img, cv2.COLOR_BGR2RGB))
plt.title('Original Cat Image')
plt.axis('off')
plt.show()
```

### 15. Adjust the brightness of the image.

```python
# Create a matrix of ones (with data type float64)
matrix_ones = np.ones(img.shape, dtype=np.float64)

matrix = matrix_ones * 50
```

### 16. Create brighter and darker images.

```python
img_brighter = cv2.add(img, matrix.astype(np.uint8))
img_darker = cv2.subtract(img, matrix.astype(np.uint8))
```

### 17. Display the images (Original Image, Darker Image, Brighter Image).

```python
plt.figure(figsize=(15, 5))

plt.subplot(1, 3, 1)
plt.imshow(cv2.cvtColor(img, cv2.COLOR_BGR2RGB))
plt.title('Original Image')
plt.axis('off')

plt.subplot(1, 3, 2)
plt.imshow(cv2.cvtColor(img_darker, cv2.COLOR_BGR2RGB))
plt.title('Darker Image')
plt.axis('off')

plt.subplot(1, 3, 3)
plt.imshow(cv2.cvtColor(img_brighter, cv2.COLOR_BGR2RGB))
plt.title('Brighter Image')
plt.axis('off')

plt.tight_layout()
plt.show()
```

### 18. Modify the image contrast.

```python
# Create two higher contrast images using scaling factors of 1.1 and 1.2
# without overflow fix

matrix1 = np.ones(img.shape, dtype=np.float64) * 1.1
matrix2 = np.ones(img.shape, dtype=np.float64) * 1.2

img_lower = cv2.multiply(img, 0.8)
img_higher1 = cv2.multiply(img, matrix1)
img_higher2 = cv2.multiply(img, matrix2)
```

### 19. Display the images (Original, Lower Contrast, Higher Contrast).

```python
plt.figure(figsize=(15, 5))

plt.subplot(1, 4, 1)
plt.imshow(cv2.cvtColor(img, cv2.COLOR_BGR2RGB))
plt.title('Original Image')
plt.axis('off')

plt.subplot(1, 4, 2)
plt.imshow(cv2.cvtColor(img_lower, cv2.COLOR_BGR2RGB))
plt.title('Lower Contrast')
plt.axis('off')

plt.subplot(1, 4, 3)
plt.imshow(cv2.cvtColor(img_higher1, cv2.COLOR_BGR2RGB))
plt.title('Higher Contrast 1.1')
plt.axis('off')

plt.subplot(1, 4, 4)
plt.imshow(cv2.cvtColor(img_higher2, cv2.COLOR_BGR2RGB))
plt.title('Higher Contrast 1.2')
plt.axis('off')

plt.tight_layout()
plt.show()
```

### 20. Split the image (`cat.jpg`) into the B, G, R components & Display the channels.

```python
b, g, r = cv2.split(img)

plt.figure(figsize=(15, 5))

plt.subplot(1, 3, 1)
plt.imshow(b, cmap='gray')
plt.title('Blue Channel')
plt.axis('off')

plt.subplot(1, 3, 2)
plt.imshow(g, cmap='gray')
plt.title('Green Channel')
plt.axis('off')

plt.subplot(1, 3, 3)
plt.imshow(r, cmap='gray')
plt.title('Red Channel')
plt.axis('off')

plt.tight_layout()
plt.show()
```

### 21. Merge the R, G, B channels and display them along with the original image.

```python
merged_img = cv2.merge([b, g, r])

plt.figure(figsize=(10, 5))

plt.subplot(1, 2, 1)
plt.imshow(cv2.cvtColor(img, cv2.COLOR_BGR2RGB))
plt.title('Original Image')
plt.axis('off')

plt.subplot(1, 2, 2)
plt.imshow(cv2.cvtColor(merged_img, cv2.COLOR_BGR2RGB))
plt.title('Merged RGB Image')
plt.axis('off')

plt.tight_layout()
plt.show()
```

### 22. Split the image into the H, S, V components & Display the channels.

```python
hsv_img = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)

h, s, v = cv2.split(hsv_img)

plt.figure(figsize=(15, 5))

plt.subplot(1, 3, 1)
plt.imshow(h, cmap='gray')
plt.title('Hue Channel')
plt.axis('off')

plt.subplot(1, 3, 2)
plt.imshow(s, cmap='gray')
plt.title('Saturation Channel')
plt.axis('off')

plt.subplot(1, 3, 3)
plt.imshow(v, cmap='gray')
plt.title('Value Channel')
plt.axis('off')

plt.tight_layout()
plt.show()
```

### 23. Merge the H, S, V channels and display them along with the original image.

```python
merged_hsv = cv2.merge([h, s, v])

merged_bgr = cv2.cvtColor(
    merged_hsv, cv2.COLOR_HSV2BGR
)

plt.figure(figsize=(10, 5))

plt.subplot(1, 2, 1)
plt.imshow(cv2.cvtColor(img, cv2.COLOR_BGR2RGB))
plt.title('Original Image')
plt.axis('off')

plt.subplot(1, 2, 2)
plt.imshow(cv2.cvtColor(merged_bgr, cv2.COLOR_BGR2RGB))
plt.title('Merged HSV Image')
plt.axis('off')

plt.tight_layout()
plt.show()
```
### 24.
### i) Adjust Brightness
```
matrix = np.ones(img.shape, dtype=np.float64) * 50
brighter = cv2.add(img, matrix.astype(np.uint8))
darker = cv2.subtract(img, matrix.astype(np.uint8))

plt.figure(figsize=(10, 3))
for i, (image, title) in enumerate([(img, 'Original'), (brighter, 'Brighter'), (darker, 'Darker')]):
    plt.subplot(1, 3, i + 1)
    plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
    plt.title(title)
    plt.axis('off')
plt.show()
```
### ii) Modify Contrast
```
high1 = cv2.multiply(img, 1.1)
high2 = cv2.multiply(img, 1.2)

plt.figure(figsize=(10, 3))
for i, (image, title) in enumerate([(img, 'Original'), (high1, 'Contrast 1.1'), (high2, 'Contrast 1.2')]):
    plt.subplot(1, 3, i + 1)
    plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
    plt.title(title)
    plt.axis('off')
plt.show()
```
### iii) Generate Image Using Bitwise Operation
```
result = cv2.bitwise_xor(img, brighter)

plt.imshow(cv2.cvtColor(result, cv2.COLOR_BGR2RGB))
plt.title('Bitwise XOR')
plt.axis('off')
plt.show()
```
## Output:

- **i)** Read and Display an Image.
  
  <img width="460" height="507" alt="image" src="https://github.com/user-attachments/assets/b58a71ad-a6de-499a-a8ba-c406a25b640d" />
 
- **ii)** Adjust Image Brightness.
  
  <img width="982" height="335" alt="image" src="https://github.com/user-attachments/assets/7159dcc8-2539-4255-b54e-f282b2f4ee5c" />
 
- **iii)** Modify Image Contrast.

  <img width="987" height="347" alt="image" src="https://github.com/user-attachments/assets/fa9b1da6-c24b-4ac0-b8c1-3d23f7683b8d" />

- **iv)** Generate Third Image Using Bitwise Operations.
  
 <img width="463" height="507" alt="image" src="https://github.com/user-attachments/assets/ec3af0e6-198f-44b7-9e28-cfc121db2646" />


## Result:

Thus, the image was read and displayed, brightness and contrast adjustments were performed, the BGR and HSV channels were split and merged, and bitwise operations were performed using the Python program.

                                                                                                  
