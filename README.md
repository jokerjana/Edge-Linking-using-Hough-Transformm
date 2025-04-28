# Exp-7-Edge-Linking-using-Hough-Transformm
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:

Import all the necessary modules for the program.
### Step2:

Load a image using imread() from cv2 module.
### Step3:

Convert the image to grayscale.
### Step4:

Using Canny operator from cv2,detect the edges of the image.
### Step5:

Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.
## Program:
```
# Developed By: JANARTHANAN B
# Register Number: 212223100014
import cv2
import matplotlib.pyplot as plt
image = cv2.imread(r'C:\Users\admin\Downloads\eif.jpeg')  # Replace with your image path
# Display Input Image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Input Image')
plt.axis('off')
plt.show()
```
![Screenshot 2025-04-28 231255](https://github.com/user-attachments/assets/2c64b3b3-8f9f-4861-864a-ff8c64b30add)

```
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

# Display Grayscale Image
plt.imshow(gray_image, cmap='gray')
plt.title('Grayscale Image')
plt.axis('off')
plt.show()
```
![Screenshot 2025-04-28 231331](https://github.com/user-attachments/assets/d97d58c2-eeaf-4c83-94fc-ee30a5921d69)





```
edges = cv2.Canny(gray_image, 50, 150, apertureSize=3)
# Display Canny Edge Detection Output   
plt.imshow(edges, cmap='gray')
plt.title('Canny Edge Detector Output')
plt.axis('off')
plt.show()
```
![Screenshot 2025-04-28 231409](https://github.com/user-attachments/assets/13a87ad1-8f30-4963-b917-03e6371a13af)



```
# Detect lines using the probabilistic Hough transform
lines = cv2.HoughLinesP(edges, rho=1, theta=np.pi/180, threshold=100, minLineLength=50, maxLineGap=10)

# Draw the lines on the original image
output_image = image.copy()

if lines is not None:
    for line in lines:
        x1, y1, x2, y2 = line[0]
        cv2.line(output_image, (x1, y1), (x2, y2), (0, 255, 0), 2)

```
```
# Display Hough Transform Result
plt.imshow(cv2.cvtColor(output_image, cv2.COLOR_BGR2RGB))
plt.title('Hough Transform - Line Detection')
plt.axis('off')
plt.show()

```
![Screenshot 2025-04-28 231448](https://github.com/user-attachments/assets/5aff5c75-a0e5-4271-bfed-d42bba7752e1)




## Result: 
Thus the python program to detect the lines using Hough Transform was successfully completed.
 
