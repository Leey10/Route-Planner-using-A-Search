# Traffic Light Color Classification
This is the final project for the nanodegree. The task is to build a traffic light color classifier 
which can correctly identify red, yellow and green light, and red/green mis-classification must be forbidden.
### Tools
OpenCV, Python
### Algorithm Description
If the traffic light is "Red", by applying red_mask, green_mask and yellow_mask respectively, only the image after red_mask  should have the red light kept, the other two images using green_mask and yellow_mask should be a black iamge theoretically. By adding up all the pixel value of the masked pictures, there should be three scores corresponding to three images after the three masks, and theorectically, the all black images should add up to 0, while the one after red_mask should be some high value. In this way, the masked image with the highest score can indicate the color of traffic light.  
  In implementation, since noises are inevitable, the green_masked and yellow_masked images may not be all black, therefore, the image label corresponding to the highest socre will be chosen.
### Weaknesses of the algorithm  
(1) it's an emperical approach to select the lower and upper bound for the mask, therefore, for some images with blurry lights, the mask may not work well;  
(2) for 'arrow' lights which inherently have small area, the scores obtained by adding up all the pixel values can be very vulnerable to disturbances;  
(3) yellow light, in particular, can be harder to identify than red and green, since it's closer to 'white' in some images.
### Other Resources
Followings are three other implementations that have a better performance than above:  
1.[Yaima's implementation](https://github.com/Yaima/intro-self-driving-cars/tree/master/traffic-light-classifier-py)  
2.[wgcv's implementation](https://github.com/wgcv/Intro-to-Self-Driving-Cars/tree/master/Project%207%20-%20Traffic%20Light%20Classifier)  
3.[Alyxion's implementation](https://github.com/wgcv/Intro-to-Self-Driving-Cars/tree/master/Project%207%20-%20Traffic%20Light%20Classifier)
