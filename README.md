# Image-Cartoonifying-
Applying Image Processing Filters For Image
Cartoonifying
1) Generating a black-and-white sketch
 We read the original image using cv.imread.
 
 ![image](https://user-images.githubusercontent.com/48353755/142763275-abe9d49b-1446-4252-8cf5-79f718707110.png)
 
 We read the original image using cv.imread passing 0 in the function to
show a gray scale image .

![image](https://user-images.githubusercontent.com/48353755/142763284-edbd1635-f44d-4e75-a4e2-2bd7a55b5169.png)

1.1 Noise Reduction Using Median Filter
We passed the gray scale image to cv2.medianBlur along with the kernel size
to get the image after median filter.

![image](https://user-images.githubusercontent.com/48353755/142763297-0f412c35-6400-491c-9e3e-eb9d38fbafc9.png)

1.2 Edge Detection Using Laplacian Filter
We passed the gray scale image to cv2.Laplacian along with the kernel
size and cv2.CV_165 to get the image edges be white the we applied
binary thresholding by
![image](https://user-images.githubusercontent.com/48353755/142763317-c77f64cd-e631-483f-a9a0-3de39cc00f8d.png)

passing the image after Laplacian filter to
cv2.threshhold with the boundaries ( 25,255 )

![image](https://user-images.githubusercontent.com/48353755/142763306-19cf3dbb-e11f-4c38-9447-fc1001bfb660.png)

![image](https://user-images.githubusercontent.com/48353755/142763323-567718e8-23f3-47cd-a496-ed32417f2891.png)

2) Generating a color painting and a cartoon
To apply bilateral filter, we resized the image to make it smaller then
we passed smaller image through a smaller bilateral filter 200 times
then resized it to its original size.

![image](https://user-images.githubusercontent.com/48353755/142763341-9bcab244-745c-41d5-9e3b-bdc7d9e37414.png)

Then we combined the image after the image thresholding with the
image after the bilateral filter using cv2.bitwise_and to get the
cartoonified image.

![image](https://user-images.githubusercontent.com/48353755/142763335-4c0448d8-6b40-413b-870b-ae6eeb408755.png)

