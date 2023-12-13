# DeepFusionMOT

This is the offical implementation of paper "[DeepFusionMOT: A 3D Multi-Object Tracking Framework Based on Camera-LiDAR Fusion with Deep Association](https://arxiv.org/abs/2202.12100) "


## Examples of Output Images
### Training data
<img src="https://github.com/Lee-Gahyun/DeepFusionMOT/blob/master/assets/ex_training.png">

### Testing data
<img src="https://github.com/Lee-Gahyun/DeepFusionMOT/blob/master/assets/ex_testing.png">

## Dependencies
- Google Colab
- "[Our colab link](https://colab.research.google.com/drive/1SzuVFcqdtcjZpVlRX-SKjkDtJcwAHazI?usp=sharing)"

## Getting Started

#### *1. Clone the github repository.*

```
!git clone https://github.com/wangxiyang2022/DeepFusionMOT
```

#### *2. Dataset preparation*

 Please download the official KITTI [object tracking dataset](http://www.cvlibs.net/datasets/kitti/eval_tracking.php).

The final dataset organization should be like this:

```
DeepFusionMOT
├── data
│   ├── kitti
│   │   │── tracking
│   │   │   │──training
|   │   │   │   ├──calib
|   │   │   │   |    ├──0000.txt
|   │   │   │   |    ├──....txt
|   │   │   │   |    └──0028.txt
|   │   │   │   ├──image_02
|   │   │   │   |    ├──0000
|   │   │   │   |    ├──....
|   │   │   │   |    └──0028
|   │   │   │   ├──oxts
|   │   │   │   |    ├──0000.txt
|   │   │   │   |    ├──....
|   │   │   │   |    └──0028.txt
|   │   │   │   ├──label_02
|   │   │   │   |    ├──0000.txt
|   │   │   │   |    ├──....txt
|   │   │   │   |    └──0028.txt
|   │   │   │   ├──velodyne
|   │   │   │   |    ├──0000
|   │   │   │   |    ├──....
|   │   │   │   |    └──0028  
│   │   │   │──testing  # the structure is same as training set
|   │   │   │   ├──calib
|   │   │   │   ├──image_02
|   │   │   │   ├──oxts
|   │   │   │   ├──label_02
|   │   │   │   └──velodyne 
```

##### NOTICE: Here are some errors in the Kitti dataset. Some data in folder 0008 and 0009 do not conform to the format of this code, and they are resulting in errors. Therefore, we copied folder 0000 and 0006 and replaced folders 0008 and 0009 when we executed.

#### *3. Mount google drive.*
```
from google.colab import drive
drive.mount('/content/drive')
```

#### *4. Install dependency*

```
!pip install -r /content/drive/MyDrive/DeepFusionMOT/requirements.txt
```

#### *5. Run main.py*
Using Training Datasets
```
!python /content/drive/MyDrive/DeepFusionMOT/main.py
```
And we can check the output images in 'DeepFusionMOT\results\KITTI\Car\image'

##### NOTICE: Please save the result folder before run main_test.py


#### *6. Run main_test.py*
Using Testing Datasets
```
!python /content/drive/MyDrive/DeepFusionMOT/main_test.py
```
Also we can check the output images in 'DeepFusionMOT\results\KITTI\Car\image'
