# road-surface-segmentation
This is a project developed by Biomechanics of Human Movements lab in KTH. We want to identify intention of exoskeleton user based on terrain identification, eye gazing and multiple sensors. Here we public our code and dataset related to road surface segmentation
# Enviroment
fastai 2.7.12 + python 3.10 + torch 2.0.1+cu118
Due to limited RAM on local computer, the training model is running on Colab.
# Dataset
Our datasets contain two parts, ones are RGB pictures shot by Intel® RealSense and the camera in a Pupil Invisible Eye Tracker. Pictures shot by eye tracker have a broader perspective and high resolution. The other part is point-cloud which contains depth information on the terrain. We use this information to identify the distance between the exoskeleton user and stairs or obstacles
# Terrain Type
We want to identify 8 types of terrain. Here is the list. The corresponding color codes are:
               Hex      RGB
background   #050505  5, 5, 5
littlebrick  #e7e025     
bigbrick     #1b1b9a  154, 27, 27 Here may be a bug in OpenCV library. Hex: #1b1b9a should be blue RGB:(27,27,154). But OpenCv considers it as RGB(154, 27, 27) which is actually supposed to be red. Here we will follow the definition in OpenCV
littleStone	 #2ebbde
bigStone		 #883808
stair				 #0b8808  8, 136, 11
Asphalt			 #d4aaff		
other				 #464546	70, 69, 70
