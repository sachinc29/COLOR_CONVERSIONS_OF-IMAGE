# COLOR_CONVERSIONS_OF-IMAGE
## AIM
Write a Python program using OpenCV that performs the following tasks:

i) Read and Display an Image.

ii) Draw Shapes and Add Text.

iii) Image Color Conversion.

iv) Access and Manipulate Image Pixels.

v) Image Resizing

vi) Image Cropping

vii) Image Flipping

viii)	Write and Save the Modified Image


## Software Required:
Anaconda - Python 3.7
## Algorithm:
### Step1:
Load an image from your local directory and display it.
### Step2:
1.  Draw a line from the top-left to the bottom-right of the image.

2.	Draw a circle at the center of the image.

3.	Draw a rectangle around a specific region of interest in the image.

4.	Add the text "OpenCV Drawing" at the top-left corner of the image.

### Step3:
1.	Convert the image from RGB to HSV and display it.
2.	Convert the image from RGB to GRAY and display it.
3.	Convert the image from RGB to YCrCb and display it.
4.	Convert the HSV image back to RGB and display it.

### Step4:
1.	Access and print the value of the pixel at coordinates (100, 100).
2.	Modify the color of the pixel at (200, 200) to white.

### Step5:
Resize the original image to half its size and display it.
### Step6:
Crop a region of interest (ROI) from the image (e.g., a 100x100 pixel area starting at (50, 50)) and display it.
### Step7:
1.	Flip the original image horizontally and display it.
2.	Flip the original image vertically and display it.

### Step8:
Save the final modified image to your local directory.


## Program:
### Developed By: SACHIN C
### Register Number: 212222230125


## Output:

### 1. Read and display the image
i.Load an image from your local directory and display it.
```py
import cv2
import matplotlib.pyplot as plt
# Read the image using OpenCV
img = cv2.imread('image3.jpg', cv2.IMREAD_COLOR)
# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
# Display the image using Matplotlib
plt.imshow(img_rgb, cmap='viridis')  # You can change 'viridis' to another cmap or use None for RGB images
plt.title("Original Image")
plt.axis('off')  # Removes axis ticks and labels
plt.show()
```
![image](https://github.com/user-attachments/assets/2ff0fae4-cf9b-4ea2-a87b-cb3ca1fd0472)


### Draw Shapes and Add Text
(1) Draw a line from the top-left to the bottom-right of the image.
```py
import cv2
image = cv2.imread("image3.jpg")
image = cv2.resize(image, (612, 612))
res = cv2.line(img,(0,0),(612,612),(100,100,205),10)

# Display the HSV image
cv2.imshow('Image Window', res)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

![image](https://github.com/user-attachments/assets/3d5aed8d-9fbe-4249-aa7e-8790ceb46a66)


2. Draw a circle at the center of the image.
```py
circle_img = cv2.circle(img_rgb,(400,300),150,(255,0,0),10) # cv2.circle(image, center, radius, color, thickness)
plt.imshow(circle_img, cmap='viridis')  
plt.title("Image with Circle")
plt.axis('off')  
plt.show()
```

![image](https://github.com/user-attachments/assets/078e4de0-f9e4-46eb-9702-2e7a913d3397)


3.Draw a rectangle around a specific region of interest in the image.
```py
import cv2
image = cv2.imread("image3.jpg")
image = cv2.resize(image, (400, 300))
start = (150, 100)
stop = (300, 200)
color = (255, 255, 100)
thickness = 10           
res_img = cv2.rectangle(image, start, stop, color, thickness)
cv2.imshow('Sachin.C', res_img)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

![image](https://github.com/user-attachments/assets/627a6547-a8ef-449f-b6f7-37ea58627fe8)


4.Add the text "OpenCV Drawing" at the top-left corner of the image.
```py
# Load the image
image = cv2.imread('image3.jpg') 

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img.shape
text_img = cv2.putText(img_rgb, "OpenCV Drawing", (10, 30), cv2.FONT_HERSHEY_SIMPLEX, 1, (255, 255, 255), 10)  ## cv2.putText(image, text, position, font, font_scale, color, thickness)
plt.imshow(text_img, cmap='viridis')  
plt.title("Image with Text")
plt.axis('off')  
plt.show()
```
![image](https://github.com/user-attachments/assets/52855f57-8781-4bf5-be91-91c70afeb972)

### iii)Image Color Conversion
(i)Convert the image from RGB to HSV and display it
```py
import cv2
image = cv2.imread('image3.jpg',1)
image = cv2.resize(image,(300,200))
cv2.imshow('ORIGINAL IMAGE',image)
hsv = cv2.cvtColor(image,cv2.COLOR_RGB2HSV)
cv2.imshow('RGB2HSV',hsv)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

![image](https://github.com/user-attachments/assets/71675427-f19d-4a0a-85cd-bd37f3da3c6c)


(2) Convert the image from RGB to GRAY and display it.

```py
import cv2
image = cv2.imread('image3.jpg',1)
image = cv2.resize(image,(300,200))
cv2.imshow('ORIGINAL IMAGE',image)
gray = cv2.cvtColor(image,cv2.COLOR_RGB2GRAY)
cv2.imshow('RGB2GRAY',gray)
cv2.waitKey(0)
cv2.destroyAllWindows()
```


![image](https://github.com/user-attachments/assets/a20c6acc-f8fd-49fc-9c82-bc569c3b1d6b)


(3) Convert the image from RGB to YCrCb and display it.
```py
import cv2
image = cv2.imread('image3.jpg',1)
image = cv2.resize(image,(300,200))
cv2.imshow('ORIGINAL IMAGE',image)
YCrCb = cv2.cvtColor(image, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

![image](https://github.com/user-attachments/assets/38baa8c6-fe83-47b2-b0ff-f82b3341c814)



(4) Convert the HSV image back to RGB and display it.
```py
import cv2
image = cv2.imread('image3.jpg',1)
image = cv2.resize(image,(300,200))
cv2.imshow('ORIGINAL IMAGE',image)
RGB = cv2.cvtColor(image,cv2.COLOR_HSV2BGR)
cv2.imshow('HSV2RGB',RGB)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

![image](https://github.com/user-attachments/assets/67a0e4b9-ab72-4109-baf5-c799bc3c6545)



### iv)Access and Manipulate Image Pixels
(1) Access and print the value of the pixel at coordinates (100, 100)
```py
import cv2
image = cv2.imread("image3.jpg")
pixel_value = image[100, 100]
print(f"Pixel value at (100, 100): {pixel_value}")
```
![image](https://github.com/user-attachments/assets/f45c4a53-988f-42ec-9e15-d87b19738a90)




(2) Modify the color of the pixel at (200, 200) to white
```py
import cv2
image = cv2.imread('image3.jpg',1)
image = cv2.resize(image,(400,300))
cv2.imshow('ORIGINAL IMAGE',image)
image[200, 200] = [255, 255, 255] 
cv2.imshow('MODIFIED IMAGE', image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

![image](https://github.com/user-attachments/assets/3907a7c4-ab59-4d09-a783-b9199dd879d6)



### v)Image Resizing:
Resize the original image to half its size and display it.
```py
cv2.imshow('ORIGINAL IMAGE',image)
resized_image = cv2.resize(image, (image.shape[1] // 2, image.shape[0] // 2))
cv2.imshow('RESIZED IMAGE', resized_image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

![image](https://github.com/user-attachments/assets/91623fec-4131-4c1c-9061-129821e7f9b1)



### vi)Image Cropping
Crop a region of interest (ROI) from the image (e.g., a 100x100 pixel area starting at (50, 50)) and display it.
```py
import cv2
image = cv2.imread('image3.jpg',1)
image = cv2.resize(image,(400,300))
x, y = 50, 50
width, height = 100, 100
roi = image[y:y + height, x:x + width]
cv2.imshow('CROPPED IMAGE', roi)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

![image](https://github.com/user-attachments/assets/e10ee85b-0f70-41f1-b8a3-d490c12a4d9c)


### vii)Image Flipping:
(1) Flip the original image horizontally and display it.
```py
import cv2
image = cv2.imread("image3.jpg")
image = cv2.resize(image,(300,200))
res=cv2.rotate(image,cv2.ROTATE_180)
cv2.imshow('ORIGINAL IMAGE',image)
cv2.imshow('FLIPPED IMAGE', res)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

![image](https://github.com/user-attachments/assets/1743997f-450f-4287-a72a-51cd4b045c97)



(2) Flip the original image vertically and display it.
```py
import cv2
image = cv2.imread("image3.jpg")
image = cv2.resize(image,(300,200))
res=cv2.rotate(image,cv2.ROTATE_90_CLOCKWISE)
cv2.imshow('ORIGINAL IMAGE',image)
cv2.imshow('FLIPPED IMAGE', res)
cv2.waitKey(0)
cv2.destroyAllWindows()
```


![image](https://github.com/user-attachments/assets/99912f03-90a8-4b89-91eb-fa2ca22b4e74)


### viii)Write and Save the Modified Image
Save the final modified image to your local directory.
```py
import cv2
img = cv2.imread("image3.jpg")
img = cv2.resize(img,(300,200))
cv2.imwrite('nature_pic.jpg',img)
```

![image](https://github.com/user-attachments/assets/5c87a2fd-fc10-46af-a56c-138eb7dd077b)


## Result:

Thus the images are read, displayed, and written ,and color conversion was performed successfully using the python program.

