# Document-Scanner

## Description

The python script prepared using openCV and numpy functions can be used to convert the image of a document into a cleaner and sharpened version.
We first resize the image, apply gaussian blur on it and use a canny edge detection algorithm to identify the edges present in the image. The image is accentuated via dilation and white noises are removed via erosion. After this, the contours are detected and the largest contour is used for applying Warp perspective to the image to remove the skewness present in the image and for the final effect, we have used adaptive thresholding coupled with bitwise not and median blurring operation.






