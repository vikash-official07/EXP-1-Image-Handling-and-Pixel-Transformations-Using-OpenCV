# Image-Handling-and-Pixel-Transformations-Using-OpenCV 

## AIM:
Write a Python program using OpenCV that performs the following tasks:

1) Read and Display an Image.  
2) Adjust the brightness of an image.  
3) Modify the image contrast.  
4) Generate a third image using bitwise operations.

## Software Required:
- Anaconda - Python 3.7
- Jupyter Notebook (for interactive development and execution)

## Algorithm:
### Step 1:
Load an image from your local directory and display it.

### Step 2:
Create a matrix of ones (with data type float64) to adjust brightness.

### Step 3:
Create brighter and darker images by adding and subtracting the matrix from the original image.  
Display the original, brighter, and darker images.

### Step 4:
Modify the image contrast by creating two higher contrast images using scaling factors of 1.1 and 1.2 (without overflow fix).  
Display the original, lower contrast, and higher contrast images.

### Step 5:
Split the image (boy.jpg) into B, G, R components and display the channels
### Ex. No. 01

#### 1. Read the image ('Eagle_in_Flight.jpg') using OpenCV imread() as a grayscale image.
```
import cv2
import matplotlib.pyplot as plt
img = cv2.imread('Eagle_in_Flight.jpg', cv2.IMREAD_COLOR)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
plt.imshow(img_rgb, cmap='viridis')  
plt.title("Original Image")
plt.axis('off')  
plt.show()


```

#### 2. Print the image width, height & Channel.
```
line_img = cv2.line(img_rgb, (0, 0), (768, 600), (255, 0, 0), 2)
plt.imshow(line_img, cmap='viridis')  
plt.title("Image with Line")
plt.axis('off')  
plt.show()

```

#### 3. Display the image using matplotlib imshow().
```
circle_img = cv2.circle(img_rgb,(400,300),150,(255,0,0),10)
plt.imshow(circle_img, cmap='viridis')  
plt.title("Image with Circle")
plt.axis('off')  
plt.show()
```

#### 4. Save the image as a PNG file using OpenCV imwrite().
```
rectangle_img = cv2.rectangle(img_rgb, (0, 0), (768, 600), (0, 0, 255), 10)
plt.imshow(rectangle_img, cmap='viridis')  
plt.title("Image with Rectangle")
plt.axis('off')  
plt.show()
```

#### 5. Read the saved image above as a color image using cv2.cvtColor().
```
text_img = cv2.putText(img_rgb, "OpenCV Drawing", (10, 30), cv2.FONT_HERSHEY_SIMPLEX, 1, (255, 255, 255), 10)
plt.imshow(text_img, cmap='viridis')  
plt.title("Image with Text")
plt.axis('off')  
plt.show()
```

#### 6. Display the Colour image using matplotlib imshow() & Print the image width, height & channel.
```
image_hsv = cv2.cvtColor(img_rgb, cv2.COLOR_RGB2HSV)
plt.imshow(image_hsv)
plt.title("HSV Image")
plt.axis("off")
```

#### 7. Crop the image to extract any specific (Eagle alone) object from the image.
```
image_gray = cv2.cvtColor(img_rgb, cv2.COLOR_RGB2GRAY)
plt.imshow(image_gray, cmap='gray')
plt.title("Grayscale Image")
plt.axis("off")
```

#### 8. Resize the image up by a factor of 2x.
```
image_ycrcb = cv2.cvtColor(img_rgb, cv2.COLOR_RGB2YCrCb)
plt.imshow(image_ycrcb)
plt.title("YCrCb Image")
plt.axis("off")
```

#### 9. Flip the cropped/resized image horizontally.
```
image_hsv_to_rgb = cv2.cvtColor(image_hsv, cv2.COLOR_HSV2RGB)
plt.imshow(image_hsv_to_rgb)
plt.title("HSV to RGB Image")
plt.axis("off")

```

#### 10. Read in the image ('Apollo-11-launch.jpg').
```
img[200:500, 200:500] = [255, 255, 255]
image_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
plt.imshow(image_rgb)
plt.title("Image with 300x300 White Block")
plt.axis("off")
plt.show()
```

#### 11. Add the following text to the dark area at the bottom of the image (centered on the image):
```
resized_image = cv2.resize(img, (768 // 2, 600 // 2))
resized_image_rgb = cv2.cvtColor(resized_image, cv2.COLOR_BGR2RGB)
plt.imshow(resized_image_rgb)
plt.title("Resized Image (Half Size)")
plt.axis("off")
plt.show()

```

#### 12. Draw a magenta rectangle that encompasses the launch tower and the rocket.
```
roi = img[50:350, 50:350]
roi_rgb = cv2.cvtColor(roi, cv2.COLOR_BGR2RGB)
plt.imshow(roi_rgb)
plt.title("Cropped Region of Interest (ROI)")
plt.axis("off")
plt.show()
```

#### 13. Display the final annotated image.
```
image = cv2.imread('Eagle_in_Flight.jpg')
flipped_horizontally = cv2.flip(image, 1)
flipped_horizontally_rgb = cv2.cvtColor(flipped_horizontally, cv2.COLOR_BGR2RGB)
plt.imshow(flipped_horizontally_rgb)
plt.title("Flipped Horizontally")
plt.axis("off")
```

#### 14. Read the image ('Boy.jpg').
```flipped_vertically = cv2.flip(image, 0)
flipped_vertically_rgb = cv2.cvtColor(flipped_vertically, cv2.COLOR_BGR2RGB)
plt.imshow(flipped_vertically_rgb)
plt.title("Flipped Vertically")
plt.axis("off")
```
#### 15. Adjust the brightness of the image.
```
cv2.imwrite(
"final_output.jpg",
flipped_horizontally
)
```



#### 18. Modify the image contrast.
```python
# Create two higher contrast images using the 'scale' option with factors of 1.1 and 1.2 (without overflow fix)
matrix1 = 
matrix2 = 
# img_higher1 = 
# img_higher2 = 
# YOUR CODE HERE
```

## Output:
Original Image
<img width="447" height="352" alt="image" src="https://github.com/user-attachments/assets/4a701c26-9f85-4421-80ec-40acae18c7f2" />

Image with Line

<img width="447" height="350" alt="image" src="https://github.com/user-attachments/assets/14541a9b-5092-4d7e-8514-7c1626aacefc" />
Image with Circle

<img width="452" height="351" alt="image" src="https://github.com/user-attachments/assets/67f6e7bd-7c6d-4804-b7d2-7bd0091e5cb5" />
Image with Rectangle

<img width="472" height="376" alt="image" src="https://github.com/user-attachments/assets/96b32af8-7f51-4da6-b07f-c173ef048369" />
Image with Text

<img width="458" height="356" alt="image" src="https://github.com/user-attachments/assets/4b272fef-82da-4916-981d-9736511acf67" />
HSV, Gray and YCrCb Images

<img width="462" height="358" alt="image" src="https://github.com/user-attachments/assets/a9fb2e15-b347-4c11-9aa3-64a1cde55ada" />

<img width="466" height="362" alt="image" src="https://github.com/user-attachments/assets/5d9b727c-44ab-4517-b929-2f5eb8a1c3bd" />

<img width="467" height="370" alt="image" src="https://github.com/user-attachments/assets/aa9122af-1a1e-4cf5-824b-ffd0cb5c1548" />
```Resized Image```

<img width="466" height="370" alt="image" src="https://github.com/user-attachments/assets/e71ef486-4605-4576-a413-20fbf4476736" />
Cropped ROI

<img width="466" height="370" alt="image" src="https://github.com/user-attachments/assets/8a1eb1fa-e4e2-4556-9093-0da176c2e16b" />
Flipped Images

<img width="472" height="377" alt="image" src="https://github.com/user-attachments/assets/a03a3ef1-d3ea-460c-a134-e399ef246463" />

<img width="463" height="375" alt="image" src="https://github.com/user-attachments/assets/98c4f933-4c73-485c-9611-68329f022d31" />











## Result:
Thus, the images were read, displayed, brightness and contrast adjustments were made, and bitwise operations were performed successfully using the Python program.

