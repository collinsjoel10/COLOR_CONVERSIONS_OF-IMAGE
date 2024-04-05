# COLOR_CONVERSIONS_OF-IMAGE
## AIM:
To write a python program using OpenCV to do the following image manipulations.

i) Read, display, and write an image.

ii) Access the rows and columns in an image.

iii) Cut and paste a small portion of the image.

iv)To perform the color conversion between RGB, BGR, HSV, and YCbCr color models.


## Software Required:
Anaconda - Python 3.7
## Algorithm:
### Step1: Choose an image and save it as a filename.jpg ,
### Step2: Use imread(filename, flags) to read the file.
### Step3: Use imshow(window_name, image) to display the image.
### Step4: Use imwrite(filename, image) to write the image.
### Step5: End the program and close the output image windows.
### Step6: Convert BGR and RGB to HSV and GRAY
### Step7: Convert HSV to RGB and BGR
### Step8: Convert RGB and BGR to YCrCb
### Step9: Split and Merge RGB Image
### Step10: Split and merge HSV Image

## Program:
```
### Developed By: JOEL P
### Register Number: 212222230057
```
<table>
  <tr>
    <td width=50%>

### i) Read and display the image
```Python
    import cv2
    image=cv2.imread('space1.jpg',1)
    image=cv2.resize(image,(400,300))
    cv2.imshow('Abishek Xavier A',image)
    cv2.waitKey(0)
    cv2.destroyAllWindows()
``` 
  </td>
  <td>

### OUTPUT:

 ![out 1](https://github.com/AbishekAnand15/COLOR_CONVERSIONS_OF-IMAGE/assets/118706942/81c894f1-f34f-47a3-9597-ce777430fc23)

  </td>
  </tr>

   <tr>
    <td width=50%>

### ii)Write the image
```Python
    import cv2
    image=cv2.imread('space1.jpg',0)
    cv2.imwrite('d.jpg',image)
```
  </td>
  <td>

### OUTPUT:

![Screenshot 2024-02-14 200035](https://github.com/AbishekAnand15/COLOR_CONVERSIONS_OF-IMAGE/assets/118706942/d5dfd19a-6adb-4c43-b42f-661c48f9f8ec)


  </td>
  </tr>
  <tr>
    <td width=50%>

### iii)Shape of the Image
```Python
    import cv2
    image=cv2.imread('space1.jpg',1)
    print(image.shape)
```
  </td>
  <td>

### OUTPUT:
![Screenshot 2024-02-14 200045](https://github.com/AbishekAnand15/COLOR_CONVERSIONS_OF-IMAGE/assets/118706942/0ff2f0f6-4e04-451b-b7b2-d8306692dffa)

  </td>
  </tr>
  <tr>
    <td>
      
### iv)Access rows and columns
```Python
    import random
    import cv2
    image=cv2.imread('space1.jpg',1)
    image=cv2.resize(image,(400,400))
    for i in range (150,200):
      for j in range(image.shape[1]):
          image[i][j]=[random.randint(0,255),
                       random.randint(0,255),
                       random.randint(0,255)] 
    cv2.imshow('part image',image)
    cv2.waitKey(0)
    cv2.destroyAllWindows()
```
  </td>
  <td width="50%">

### OUTPUT:

 ![out2](https://github.com/AbishekAnand15/COLOR_CONVERSIONS_OF-IMAGE/assets/118706942/d1ee7a7d-37f1-461c-91f2-770672c1350d)

  </td>
  </tr>
  <tr>
    <td width=50%>
      
### v)Cut and paste portion of image

 ```Python
    import cv2
    image=cv2.imread('space1.jpg',1)
    image=cv2.resize(image,(400,400))
    tag =image[130:200,110:190]
    image[110:180,120:200] = tag
    cv2.imshow('partimage1',image)
    cv2.waitKey(0)
    cv2.destroyAllWindows()
```
  </td>
  <td>
    
### OUTPUT:
![out3](https://github.com/AbishekAnand15/COLOR_CONVERSIONS_OF-IMAGE/assets/118706942/cbf20d49-2cab-4c75-bece-44302ac31959)

  </td>
  </tr>
</table>

### vi) BGR and RGB to HSV and GRAY
```Python
import cv2
img = cv2.imread('space1.jpg',1)
img = cv2.resize(img,(300,200))
cv2.imshow('Original Image',img)
hsv1 = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
cv2.imshow('BGR2HSV',hsv1)
hsv2 = cv2.cvtColor(img,cv2.COLOR_RGB2HSV)
cv2.imshow('RGB2HSV',hsv2)
gray1 = cv2.cvtColor(img,cv2.COLOR_BGR2GRAY)
cv2.imshow('BGR2GRAY',gray1)
gray2 = cv2.cvtColor(img,cv2.COLOR_RGB2GRAY)
cv2.imshow('RGB2GRAY',gray2)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

### OUTPUT:
![out 4](https://github.com/AbishekAnand15/COLOR_CONVERSIONS_OF-IMAGE/assets/118706942/c2437235-ac09-452b-8ff9-0a39b8a93d10)
![out5](https://github.com/AbishekAnand15/COLOR_CONVERSIONS_OF-IMAGE/assets/118706942/9b4a4b0f-91e5-4a28-b3d5-0060f9a840d1)
![out6](https://github.com/AbishekAnand15/COLOR_CONVERSIONS_OF-IMAGE/assets/118706942/b4f86926-f934-4bb3-a087-4b66022ba44b)
![out7](https://github.com/AbishekAnand15/COLOR_CONVERSIONS_OF-IMAGE/assets/118706942/0c5fd01f-6c8a-4ab8-81d6-12147a781e71)
![out8](https://github.com/AbishekAnand15/COLOR_CONVERSIONS_OF-IMAGE/assets/118706942/0ecdce33-2db9-498e-903c-2df89ee6fbc1)



### vii) HSV to RGB and BGR
```Python
import cv2
img = cv2.imread('space1.jpg')
img = cv2.resize(img,(300,200))
img = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
cv2.imshow('Original HSV Image',img)
RGB = cv2.cvtColor(img,cv2.COLOR_HSV2RGB)
cv2.imshow('2HSV2BGR',RGB)
BGR = cv2.cvtColor(img,cv2.COLOR_HSV2BGR)
cv2.imshow('HSV2RGB',BGR)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

### OUTPUT:
![out9](https://github.com/AbishekAnand15/COLOR_CONVERSIONS_OF-IMAGE/assets/118706942/52d2f56e-1a18-4156-88c0-6b14962ffbb9)
![out10](https://github.com/AbishekAnand15/COLOR_CONVERSIONS_OF-IMAGE/assets/118706942/fd2d03c3-9d09-46e0-9de9-119e151528be)
![out11](https://github.com/AbishekAnand15/COLOR_CONVERSIONS_OF-IMAGE/assets/118706942/783b443b-2fb3-43e2-b2a3-6bf1cb5ddc3e)


### viii) RGB and BGR to YCrCb
```Python
import cv2
img = cv2.imread('space1.jpg')
img = cv2.resize(img,(300,200))
cv2.imshow('Original RGB Image',img)
YCrCb1 = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb1)
YCrCb2 = cv2.cvtColor(img, cv2.COLOR_RGB2YCrCb)
cv2.imshow('BGR-2-YCrCb',YCrCb2)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

### OUTPUT:
![out12](https://github.com/AbishekAnand15/COLOR_CONVERSIONS_OF-IMAGE/assets/118706942/2c8fe1ac-c9c9-439e-82e1-e473d39bd945)
![out13](https://github.com/AbishekAnand15/COLOR_CONVERSIONS_OF-IMAGE/assets/118706942/08aba78d-aae0-4664-9a4c-a1eedb3b7b94)
![out14](https://github.com/AbishekAnand15/COLOR_CONVERSIONS_OF-IMAGE/assets/118706942/10eec2fa-4590-43f7-95fb-89602b50836c)



### ix) Split and merge RGB Image
```Python
import cv2
img = cv2.imread('space1.jpg',1)
img = cv2.resize(img,(300,200))
R = img[:,:,2]
G = img[:,:,1]
B = img[:,:,0]
cv2.imshow('R-Channel',R)
cv2.imshow('G-Channel',G)
cv2.imshow('B-Channel',B)
merged = cv2.merge((B,G,R))
cv2.imshow('Merged RGB image',merged)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

### OUTPUT:
![out15](https://github.com/AbishekAnand15/COLOR_CONVERSIONS_OF-IMAGE/assets/118706942/0cab0028-2155-40e0-961e-cf6c72f99de7)
![out16](https://github.com/AbishekAnand15/COLOR_CONVERSIONS_OF-IMAGE/assets/118706942/16c9d1b9-dba3-49eb-afbc-412ab869a8c7)
![out17](https://github.com/AbishekAnand15/COLOR_CONVERSIONS_OF-IMAGE/assets/118706942/c1ff11f0-2b2a-41d6-8007-74ae6aaf5d90)
![out18](https://github.com/AbishekAnand15/COLOR_CONVERSIONS_OF-IMAGE/assets/118706942/cac59a97-e83b-46ed-be77-eb714a262775)



### x) Split and merge HSV Image
```Python
import cv2
img = cv2.imread("space1.jpg",1)
img = cv2.resize(img,(300,200))
img=cv2.cvtColor(img,cv2.COLOR_RGB2HSV)
H,S,V=cv2.split(img)
cv2.imshow('Hue',H)
cv2.imshow('Saturation',S)
cv2.imshow('Value',V)
merged = cv2.merge((H,S,V))
cv2.imshow('Merged',merged)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

### OUTPUT:

![out19](https://github.com/AbishekAnand15/COLOR_CONVERSIONS_OF-IMAGE/assets/118706942/a77602e9-49f5-43a5-ac90-914625b624fc)
![out20](https://github.com/AbishekAnand15/COLOR_CONVERSIONS_OF-IMAGE/assets/118706942/ddebcc26-e266-4e71-a1e9-5157e8d4a3c6)
![out21](https://github.com/AbishekAnand15/COLOR_CONVERSIONS_OF-IMAGE/assets/118706942/e12453cb-481c-46f7-be68-59ddb0aaabe1)
![out22](https://github.com/AbishekAnand15/COLOR_CONVERSIONS_OF-IMAGE/assets/118706942/57793e99-9a00-47f3-9406-0f8d50824b0f)

## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.
