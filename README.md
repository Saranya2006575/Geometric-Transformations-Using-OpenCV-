# Exp-4-Record Image Transformations

## Aim
To perform image transformations such as Translation, Scaling, Shearing, Reflection, Rotation, and Cropping using OpenCV and Python.

## Software Required
Anaconda – Python 3.7
OpenCV (cv2) library
NumPy library

## Algorithm
### Step 1:
Import the necessary libraries such as cv2 and numpy.

### Step 2:
Read the input image using cv2.imread() and display the original image using cv2.imshow().

### Step 3:
Perform various geometric transformations:

Translation: Shift the image position using a transformation matrix.
Scaling: Resize the image using cv2.resize().
Shearing: Apply an affine transformation to skew the image.
Reflection: Flip the image using cv2.flip().
Rotation: Rotate the image using cv2.getRotationMatrix2D() and cv2.warpAffine().
Cropping: Slice the image array to extract a specific region.

### Step 4:
Display all the transformed images in separate windows using cv2.imshow().

### Step 5:
Wait for a key press using cv2.waitKey(0) and then close all OpenCV windows using cv2.destroyAllWindows().

## Program

#### Name: SARANYA.J
#### Reg.No: 212224240146

```
# Import Python necessary libraries

import cv2
import numpy as np
import matplotlib.pyplot as plt

# Step 1: Load the image

image = cv2.imread('railway_station.jpg')  # Load the image from file

# Display the original image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert BGR to RGB for correct display
plt.title("Original Image")  
plt.axis('off') 
```
<img width="550" height="550" alt="image" src="https://github.com/user-attachments/assets/acef30bf-eab7-4ba7-aa28-771292fef28f" />

```
# Step 2: Image Translation

tx, ty = 100, 50  
M_translation = np.float32([[1, 0, tx], [0, 1, ty]]) 

translated_image = cv2.warpAffine(image, M_translation, (image.shape[1], image.shape[0]))

plt.imshow(cv2.cvtColor(translated_image, cv2.COLOR_BGR2RGB))  
plt.title("Translated Image")  
plt.axis('off')
```
<img width="550" height="550" alt="image" src="https://github.com/user-attachments/assets/454e5b0d-90c0-454b-a269-26b72a0ec9e3" />

```
# Step 3: Image Scaling

fx, fy = 5.0, 2.0  # Scaling factors (1.5x scaling for both width and height)
scaled_image = cv2.resize(image, None, fx=fx, fy=fy, interpolation=cv2.INTER_LINEAR)


plt.imshow(cv2.cvtColor(scaled_image, cv2.COLOR_BGR2RGB))  # Display the scaled image
plt.title("Scaled Image")  # Set title
plt.axis('off')
```
<img width="550" height="550" alt="image" src="https://github.com/user-attachments/assets/b609ab89-e613-4614-befc-ae70a7abc021" />

```
# Step 4: Image Shearing

shear_matrix = np.float32([[1, 0.5, 0], [0.5, 1, 0]])  # Shearing matrix
sheared_image = cv2.warpAffine(image, shear_matrix, (image.shape[1], image.shape[0]))

plt.imshow(cv2.cvtColor(sheared_image, cv2.COLOR_BGR2RGB))  # Display the sheared image
plt.title("Sheared Image")  # Set title
plt.axis('off')
```
<img width="550" height="550" alt="image" src="https://github.com/user-attachments/assets/1778a004-5689-475d-84f2-4bd6d98f631e" />

```
# Step 5: Image Reflection

reflected_image = cv2.flip(image, 2)  # Flip the image horizontally (1 means horizontal flip)

plt.imshow(cv2.cvtColor(reflected_image, cv2.COLOR_BGR2RGB))  # Display the reflected image
plt.title("Reflected Image")  # Set title
plt.axis('off')
```
<img width="550" height="550" alt="image" src="https://github.com/user-attachments/assets/194b2260-4dde-4300-a32a-be59506b7f50" />

```
# Step 6: Image Rotation

(height, width) = image.shape[:2]  
angle = 45  
center = (width // 2, height // 2) 
M_rotation = cv2.getRotationMatrix2D(center, angle, 1)  
rotated_image = cv2.warpAffine(image, M_rotation, (width, height))  

plt.imshow(cv2.cvtColor(rotated_image, cv2.COLOR_BGR2RGB))  
plt.title("Rotated Image")  
plt.axis('off')
```
<img width="550" height="550" alt="image" src="https://github.com/user-attachments/assets/10dcd1b7-5045-4f66-9539-faaa4ea40cce" />

```
# Step 7: Image Cropping
x, y, w, h = 100, 100, 200, 150  
cropped_image = image[y:y+h, x:x+w]

plt.imshow(cv2.cvtColor(cropped_image, cv2.COLOR_BGR2RGB)) 
plt.title("Cropped Image")  
plt.axis('off')
```
<img width="550" height="550" alt="image" src="https://github.com/user-attachments/assets/fca0dd9d-5f42-4764-9cf6-801a18aa775c" />

## Result
Thus, the given experiment on image transformations has been successfully executed using the OpenCV library in Python.
