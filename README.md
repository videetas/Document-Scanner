# Document-Scanner

## Description

The python script prepared using openCV and numpy functions can be used to convert the image of a document into a cleaner and sharpened version.
We first resize the image, apply gaussian blur on it and use a canny edge detection algorithm to identify the edges present in the image. The image is accentuated via dilation and white noises are removed via erosion. After this, the contours are detected and the largest contour is used for applying Warp perspective to the image to remove the skewness present in the image and for the final effect, we have used adaptive thresholding coupled with bitwise not and median blurring operation.

### 1 . Resize
We have used the function cv2.resize to convert all the images to dimension 480X640.

### 2.Gray image- Function used- cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
A digital image is composed of groups of three pixels with colors of red, green and blue (RGB). Each channel also contains a luminance value to determine how light or dark the color is. To get a grayscale image, the color information from each channel is removed, leaving only the luminance values, and that is why the image becomes a pattern of light and dark areas devoid of color, essentially a black and white image. 
The way it is done is: The 3 channels of the colored image(pixel values for Red,Green and Blue) are separated, 
The values in the channel corresponding to red are scaled by 0.299
The values in the channel corresponding to green are scaled by 0.587
The values in the channel corresponding to blue are scaled by 0.114
The values of these 3 channels are summed up to form the pixel values of the final gray image which has a single channel only.

### 3.Blur image
It is implemented with the help of the cv2.gaussianblur() function.We should specify the width and height of the kernel which should be positive and odd. We also should specify the standard deviation in the X and Y directions, sigmaX and sigmaY respectively. If only sigmaX is specified, sigmaY is taken as equal to sigmaX. If both are given as zeros, they are calculated from the kernel size. Gaussian filtering is highly effective in removing Gaussian noise from the image.
It is a method of blurring an image through the use of a Gaussian function. 
If the Gaussian distribution is superimposed over a group of pixels in an image, it is apparent looking at the graph, that if we took a weighted average of the pixel’s values and the height of the curve at that point, the pixels in the center of the group would contribute most significantly to the resulting value. This is, in essence, how Gaussian blur works. While the kernel can technically be an arbitrary size, we should scale σ in proportion to the kernel size. If we have a large kernel radius, but a small sigma, then all of the new pixels we’re introducing with our larger radius aren’t really affecting the computation.
The Gaussian Kernel is first defined which is then used for convolution with the original image to give the output.

A Gaussian Kernel of size (2n+1,2n+1) is given by 
G[i,j]=1/(2π↽2  )*e(-1*((i-n)2+(j-n)2)/(2↽2))
We have used a 5x5 Gaussian Kernel.




