# EX 04 IMAGE-TRANSFORMATIONS

## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step 1: 
Import numpy module as np and pandas as pd.
### Step 2: 
Assign the values to variables in the program.
### Step 3: 
Get the values from the user appropriately.
### Step 4: 
Continue the program by implementing the codes of required topics.
### Step 5: 
Thus the program is executed in google colab.

## Program:

#### Developed By : NIRAUNJANA GAYATHRI G R
#### Register Number : 212222230096

### Installing OpenCV , importing necessary libraries and displaying images  

```py
# Install OpenCV library
!pip install opencv-python-headless

import cv2
import numpy as np
from matplotlib import pyplot as plt

# Function to display images 
def show_image(image):
    plt.figure(figsize=(6, 6))
    plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
    plt.axis('off')
    plt.show()

```

#### (i) Image Translation
```py
# Load an image from URL or file path
image_url = 'one.jpg'  
image = cv2.imread(image_url)

# Define translation matrix
tx = 50  # Translation along x-axis
ty = 30  # Translation along y-axis
translation_matrix = np.float32([[1, 0, tx], [0, 1, ty]])  # Create translation matrix

# Apply translation to the image
translated_image = cv2.warpAffine(image, translation_matrix, (image.shape[1], image.shape[0]))

# Display original and translated images
print("Original Image:")
show_image(image)
print("Translated Image:")
show_image(translated_image)
```

#### (ii) Image Scaling
```py

# Load an image from URL or file path
image_url = '2.jpg'  # Replace with your image URL or file path
image = cv2.imread(image_url)


# Define scale factors
scale_x = 1.5  # Scaling factor along x-axis
scale_y = 1.5  # Scaling factor along y-axis


# Apply scaling to the image
scaled_image = cv2.resize(image, None, fx=scale_x, fy=scale_y, interpolation=cv2.INTER_LINEAR)

# Display original and scaled images
print("Original Image:")
show_image(image)
print("Scaled Image:")
show_image(scaled_image)

```




#### (iii) Image shearing
```py
# Load an image from URL or file path
image_url = '3.jpg'  # Replace with your image URL or file path
image = cv2.imread(image_url)

# Define shear parameters
shear_factor_x = 0.5  # Shear factor along x-axis
shear_factor_y = 0.2  # Shear factor along y-axis

# Define shear matrix
shear_matrix = np.float32([[1, shear_factor_x, 0], [shear_factor_y, 1, 0]])

# Apply shear to the image
sheared_image = cv2.warpAffine(image, shear_matrix, (image.shape[1], image.shape[0]))

# Display original and sheared images
print("Original Image:")
show_image(image)
print("Sheared Image:")
show_image(sheared_image)

```



#### (iv) Image Reflection

```py
# Load an image from URL or file path
image_url = '4.jpg'  # Replace with your image URL or file path
image = cv2.imread(image_url)

# Reflect the image horizontally
reflected_image_horizontal = cv2.flip(image, 1)

# Reflect the image vertically
reflected_image_vertical = cv2.flip(image, 0)

# Reflect the image both horizontally and vertically
reflected_image_both = cv2.flip(image, -1)

```

##### (a) → Reflecting Horizontally

```py
# Display original and reflected images

show_image(image)
print("↑ Original Image")
show_image(reflected_image_horizontal)
print("↑ Reflected Horizontally")
```

##### (b) → Reflected Vertically

```py
show_image(image)
print("↑ Original Image")
show_image(reflected_image_vertical)
print("↑ Reflected Vertically")

```

##### (c) → Reflecting Horizontally & Vertically
```py

show_image(image)
print("↑ Original Image")
show_image(reflected_image_both)
print("↑ Reflected Both")

```

### (v) Image Rotation

```py
# Load an image from URL or file path
image_url = '5.jpg'  # Replace with your image URL or file path
image = cv2.imread(image_url)


# Define rotation angle in degrees
angle = 45

# Get image height and width
height, width = image.shape[:2]

# Calculate rotation matrix
rotation_matrix = cv2.getRotationMatrix2D((width / 2, height / 2), angle, 1)

# Perform image rotation
rotated_image = cv2.warpAffine(image, rotation_matrix, (width, height))

# Display original and rotated images
print("Original Image:")
show_image(image)
print("Rotated Image:")
show_image(rotated_image)

```



### (vi) Image Cropping

```py
# Load an image from URL or file path
image_url = '6.jpg'  # Replace with your image URL or file path
image = cv2.imread(image_url)

# Define cropping coordinates (x, y, width, height)
x = 100  # Starting x-coordinate
y = 50   # Starting y-coordinate
width = 200  # Width of the cropped region
height = 150  # Height of the cropped region

# Perform image cropping
cropped_image = image[y:y+height, x:x+width]

# Display original and cropped images
print("Original Image:")
show_image(image)
print("Cropped Image:")
show_image(cropped_image)

```


## Output:

### (i) Image Translation

![WhatsApp Image 2024-03-19 at 11 25 18_d368cc95](https://github.com/niraunjana/IMAGE-TRANSFORMATIONS/assets/119395610/21dc9998-5f8c-4b32-893c-b1f189e8558a)

![WhatsApp Image 2024-03-19 at 11 25 38_99e20c53](https://github.com/niraunjana/IMAGE-TRANSFORMATIONS/assets/119395610/c3746468-c7b0-4659-8b25-886aad3e2383)




### (ii) Image Scaling

![WhatsApp Image 2024-03-19 at 11 26 16_acd63dfa](https://github.com/niraunjana/IMAGE-TRANSFORMATIONS/assets/119395610/4a122c79-7814-4d1f-933f-af8f699a2536)

![WhatsApp Image 2024-03-19 at 11 26 31_f9639284](https://github.com/niraunjana/IMAGE-TRANSFORMATIONS/assets/119395610/c6f0163b-78df-4775-9be1-14b03420f31e)


### (iii) Image shearing

![image](https://github.com/niraunjana/IMAGE-TRANSFORMATIONS/assets/119395610/036899b2-7992-448b-adfe-e9f9b906e786)

![image](https://github.com/niraunjana/IMAGE-TRANSFORMATIONS/assets/119395610/6d098f21-1656-4967-bdd5-3a3162a1337c)



### (iv) Image Reflection

#### Reflecting Horizontally

![image](https://github.com/niraunjana/IMAGE-TRANSFORMATIONS/assets/119395610/86db9e42-c4a6-420a-a77e-a0983959fd8a)

![image](https://github.com/niraunjana/IMAGE-TRANSFORMATIONS/assets/119395610/30dd8343-4fdc-4733-9ba0-6ce611f597fe)




#### Reflecting Vertically

![image](https://github.com/niraunjana/IMAGE-TRANSFORMATIONS/assets/119395610/22522898-741a-4987-92e9-b795fcf3824a)

![image](https://github.com/niraunjana/IMAGE-TRANSFORMATIONS/assets/119395610/e8d476e4-e435-475d-bb31-f425fe221eab)




#### Reflecting Horizontally & Vertically
![image](https://github.com/niraunjana/IMAGE-TRANSFORMATIONS/assets/119395610/54fbaa4c-1cce-4427-80f5-78208b627aa9)

![image](https://github.com/niraunjana/IMAGE-TRANSFORMATIONS/assets/119395610/a728b4f4-2414-455a-8f3f-11863bce8f06)




### (v) Image Rotation

![image](https://github.com/niraunjana/IMAGE-TRANSFORMATIONS/assets/119395610/af342f4f-a07a-4c77-be9a-86e936eb0b70)

![image](https://github.com/niraunjana/IMAGE-TRANSFORMATIONS/assets/119395610/0932ef7a-11b2-4823-8243-fe5d70459f27)



### (vi) Image Cropping

![image](https://github.com/niraunjana/IMAGE-TRANSFORMATIONS/assets/119395610/6745bdf5-126e-4ea9-9525-5f37085dae3e)

![image](https://github.com/niraunjana/IMAGE-TRANSFORMATIONS/assets/119395610/533ecb1a-882c-4717-9a5c-fb4e8d0f2e7b)


## Result: 
Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
