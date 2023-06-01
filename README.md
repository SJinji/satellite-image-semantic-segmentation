# satellite-image-semantic-segmentation
Hurricane Harvey Challenge [2022-2023]

## Team Members
Mengyu LIANG: mengyu.liang@student-cs.fr  
Jinji SHEN: jinji.shen@student-cs.fr

## Project Description
This project aims to use deep learning to accurately segment buildings and roads from satellite images in the aftermath of Hurricane Harvey. Accurate segmentation can help emergency responders and aid organizations to efficiently allocate resources and aid in the recovery process.

## Dataset
There are 299 images for training and 75 images for testing, the detailed information of dataset as follows:

<img width="310" alt="image" src="https://github.com/SJinji/satellite-image-semantic-segmentation/assets/103330181/5031f78f-97ea-4d72-9ac5-817f77bd5a42">

## Modeling
### Image Pre-processing
1. Resize Images Using Rescaling  
To ensure all images have the same input size for the neural network, we resize all images to 4096 x 4096. We then downscale the images of training set, validation dataset and test set to 1024 x 1024, 512 x 512, and 512 x 512 respectively using Gaussian pyramid to reduce the computational requirements.

2. Image Augmentation  
We apply several image augmentation techniques to the training set to prevent the neural network from learning irrelevant features. These include random cropping, position manipulation, CLANE, color manipulation and sharpening. We generate 10 new images from each original image, increasing the size of the training set by 10.

### Model Architecture
1. U-Net

2. DeepLapv3+  

3. PSPNet


### Results Evaluation
We evaluate the model using Dice score, which ranges from 0 to 1. Our final model achieved a Dice score of 75.9%, ranking 9th on the leaderboard. We also compared our model with U-Net and PSPNet, and found that DeepLabv3+ with ResNet101 achieved the best performance.

<img width="823" alt="image" src="https://user-images.githubusercontent.com/103330181/235303710-70fac066-72a1-4bdb-8f46-fe751169d3d7.png">

Considering the performences, we choose DeepLabV3+ with the backbone Resnet101 as our final model.  
The mask predicted by our model is shown in the right picture below, while the left and middle pictures represent the image and the true mask, respectively.

<img width="722" alt="image" src="https://user-images.githubusercontent.com/103330181/235303800-ab0afaac-c2f8-448d-84bf-b5bf33c9a522.png">

### Conclusion
Our model achieved accurate segmentation of buildings and roads from satellite images, which can help emergency responders and aid organizations to allocate resources and aid in the recovery process. DeepLabv3+ with ResNet101 is a suitable model for this task, although other models such as U-Net and PSPNet may be used depending on hardware resources and training time.

