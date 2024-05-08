# COLOR_CONVERSIONS_OF-IMAGE
## AIM
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

### Developed By: JOEL P
### Register Number: 212222230057



### i) Read and display the image
```Python
    import cv2
    image=cv2.imread('pristine-reflective-lake-show-image-260nw-2305485315.jpg',1)
    image=cv2.resize(image,(400,300))
    cv2.imshow('Original Image',image)
    cv2.waitKey(0)
    cv2.destroyAllWindows()
``` 
  </td>
  <td>

### OUTPUT:

 ![Screenshot 2024-02-14 200530](https://github.com/Mathiofficial/COLOR_CONVERSIONS_OF-IMAGE/assets/118787327/21f147ae-2762-4b4c-8e19-01459aab7efd)
</td>
  </tr>

   <tr>
    <td width=50%>

  
### ii)Write the image
```Python
    import cv2
    image=cv2.imread('pristine-reflective-lake-show-image-260nw-2305485315.jpg',0)
    cv2.imwrite('demos.jpg',image)
```

### OUTPUT:

![Screenshot 2024-02-14 111459](https://github.com/Mathiofficial/COLOR_CONVERSIONS_OF-IMAGE/assets/118787327/fd77bd08-b104-4a08-9d61-84283f16a0bb)
  </td>
  </tr>
  <tr>
    <td width=50%>

### iii)Shape of the Image
```Python
    import cv2
    image=cv2.imread('pristine-reflective-lake-show-image-260nw-2305485315.jpg',1)
    print(image.shape)
```
  </td>
  <td>

### OUTPUT:
![Screenshot 2024-02-14 111509](https://github.com/Mathiofficial/COLOR_CONVERSIONS_OF-IMAGE/assets/118787327/c87c78bd-e3d8-4e5a-b93c-e8025dce101a)
  </td>
  </tr>
  <tr>
    <td>
      
### iv)Access rows and columns
```Python
    import random
    import cv2
    image=cv2.imread('pristine-reflective-lake-show-image-260nw-2305485315.jpg',1)
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

 ![Screenshot 2024-02-14 111621](https://github.com/Mathiofficial/COLOR_CONVERSIONS_OF-IMAGE/assets/118787327/3a70e210-6d5c-41c6-a631-38daa8bcaf89)
  </td>
  </tr>
  <tr>
    <td width=50%>
      
### v)Cut and paste portion of image

 ```Python
    import cv2
    image=cv2.imread('pristine-reflective-lake-show-image-260nw-2305485315.jpg',1)
    image=cv2.resize(image,(400,400))
    tag =image[150:200,110:160]
    image[110:160,150:200] = tag
    cv2.imshow('partimage1',image)
    cv2.waitKey(0)
    cv2.destroyAllWindows()
```
  </td>
  <td>
    
### OUTPUT:

![Screenshot 2024-02-14 111837](https://github.com/Mathiofficial/COLOR_CONVERSIONS_OF-IMAGE/assets/118787327/7d261088-5eeb-47dc-ad1b-972901b86999)
  </td>
  </tr>
</table>

### vi) BGR and RGB to HSV and GRAY
```Python
import cv2
img = cv2.imread('pristine-reflective-lake-show-image-260nw-2305485315.jpg',1)
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

![Screenshot 2024-02-14 112235](https://github.com/Mathiofficial/COLOR_CONVERSIONS_OF-IMAGE/assets/118787327/5dcd3ab1-78d0-4ad4-9571-7db860323bbd)


### vii) HSV to RGB and BGR
```Python
import cv2
img = cv2.imread('pristine-reflective-lake-show-image-260nw-2305485315.jpg')
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

![Screenshot 2024-02-14 112829](https://github.com/Mathiofficial/COLOR_CONVERSIONS_OF-IMAGE/assets/118787327/5e5723a0-d127-416d-a473-72a415dd12a8)


### viii) RGB and BGR to YCrCb
```Python
import cv2
img = cv2.imread('pristine-reflective-lake-show-image-260nw-2305485315.jpg')
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

![Screenshot 2024-02-14 112951](https://github.com/Mathiofficial/COLOR_CONVERSIONS_OF-IMAGE/assets/118787327/709cd998-d9ef-4293-b4cb-7a881e8fc55d)


### ix) Split and merge RGB Image
```Python
import cv2
img = cv2.imread('pristine-reflective-lake-show-image-260nw-2305485315.jpg',1)
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

![Screenshot 2024-02-14 113247](https://github.com/Mathiofficial/COLOR_CONVERSIONS_OF-IMAGE/assets/118787327/92cc2059-7eb4-4da4-b014-65069e24309e)


### x) Split and merge HSV Image
```Python
import cv2
img = cv2.imread("pristine-reflective-lake-show-image-260nw-2305485315.jpg",1)
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

![Screenshot 2024-02-14 113515](https://github.com/Mathiofficial/COLOR_CONVERSIONS_OF-IMAGE/assets/118787327/8f673325-ff01-4f53-8d05-fe5596340482)


## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.







