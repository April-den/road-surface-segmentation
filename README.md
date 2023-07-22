![image](https://github.com/April-den/road-surface-segmentation/blob/main/logo.png)

https://www.kth.se/en/sci/kth-moveability-lab
# road-surface-segmentation
This is a project developed by Biomechanics of Human Movements lab in KTH. We want to identify intention of exoskeleton user based on terrain identification, eye gazing and multiple sensors. Here we public our code and dataset related to road surface segmentation based on RGB and point cloud.
# Install
fastai 2.7.12 + python 3.10 + torch 2.0.1+cu118
Due to limited RAM on local computer, the training model is running on Colab.
# Dataset
Our datasets contain two parts, ones are RGB pictures shot by Intel® RealSense and the camera in a Pupil Invisible Eye Tracker. Pictures shot by eye tracker have a broader perspective and high resolution. The other part is point-cloud which contains depth information on the terrain. We use this information to identify the distance between the exoskeleton user and stairs or obstacles.
## RGB Dataset
└─src
    └─main
We manually labeled different terrains in pictures. The number of these labeled pictures is 295. 70% of them(206) are used for training and 30% of them(89) are used for validation. Pictures for validation are randomly chosen and listed in [valid.txt](https://github.com/April-den/road-surface-segmentation/blob/main/valid.txt).
## Point Cloud Dataset
# Terrain Type
We want to identify 8 types of terrain. Here is the list. The corresponding color codes are:
|             | RGB         | Label |
|-------------|-------------|-------|
| background  | 5, 5, 5     |   0   |
| littlebrick | 222, 187, 46|   1   |
| bigbrick    | 154, 27, 27 |   2   |
| littleStone | 37, 224, 231|   3   |
| bigStone    | 8, 56, 136  |   4   |
| stair       | 8, 136, 11  |   5   |
| asphalt     | 255,170,212 |   6   |
| other       | 70, 69, 70  |   7   |


The label is represented by pixel values of gray image (mask) shown in [label folder](https://github.com/April-den/road-surface-segmentation/tree/main/label): label which will be used as the target label in deep learning. That's why the pixel value should be within the range of the number of terrain types. Here we have 8 types, so the labels is within [0, 7]. If you use image with pixel value larger than 7, you will get an error: target ** is out of bounds.
# RGB Segmentation Training Model

# Point Cloud Segmentation
