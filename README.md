![foreground_frames_AVGFrame](https://github.com/Sagnick0907/Background-Extraction-using-GMM/assets/76872499/ce2d723f-3a36-4c23-8e0b-c28656a946e1)# Background-Extraction-using-GMM

## Table of Content
  * [Demo](#demo)
  * [Overview](#overview)
  * [Goal](#goal)
  * [Technical Aspect](#technical-aspect)
  * [Technologies Used](#technologies-used)

## Demo
1. GIF generated using Foreground Frames from calcuating using mean training frames.
![foreground_frames_AVGFrame](https://github.com/Sagnick0907/Background-Extraction-using-GMM/assets/76872499/0fa2d524-c73e-4332-ab07-1f723fbdbba2)
2.  GIF generated using Foreground Frames from calcuating using GMM.
![foreground_frames_restored](https://github.com/Sagnick0907/Background-Extraction-using-GMM/assets/76872499/ca7a448c-5cab-46ed-aed9-db417d5ade5c)
  
## Overview  
We attempted to solve the task of background subtraction using Multivariate Gaussian Mixture Models. We extracted the background image from a given set of training frames, and use the extracted background to display foreground objects in the test frames by subtracting that background image and then thresholding it accordingly.

## Motivation and Goal  
To accurately identify and track moving objects in video sequences for applications like surveillance, human-computer interaction, and traffic monitoring. So we use Multivariate Gaussian Mixture Models for background subtraction, aiming to model the background, detect foreground objects, and adapt to dynamic changes in real-time video environments.

## Technical Aspect  
Here, we are going to try different baselines to extract background from low resolution camera footage:  

1. Frame Averaging:  
    - Just take the average of every training frame, which gives us an approximate background image.
    
2. GMM Per Pixel:  
    - We will maintain per pixel GMMs of 2 components, and then fit these GMMs considering every training from for its corresponding pixel.
    - And then use these GMMs to predict the pixel labels for every subsequent frame.
    - Most of the time, the Gaussian with the higher weight corresponds to the background.
    - We can implement this in a simpler way but with worse prediction results, you can extract a mean background image similar to the first baseline above.
    - To extract the Mean background image, we can assign values of the Means corresponding to the highest weighted Gaussian for each pixel.
    - This method is much simpler to implement but, this could give worse results.

## Technologies Used
- Google Colab  
- Concepts used : Multivariate GMM.    
- Libraries: numpy, matplotlib.pyplot, multivariate_normal, train_test_split, os.
