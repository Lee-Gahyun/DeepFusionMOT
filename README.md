# DeepFusionMOT

This is the offical implementation of paper "[DeepFusionMOT: A 3D Multi-Object Tracking Framework Based on Camera-LiDAR Fusion with Deep Association](https://arxiv.org/abs/2202.12100) "


### Video examples on benchmarks dataset

![Video examples](https://github.com/wangxiyang2022/DeepFusionMOT/raw/master/assets/Video_examples.gif)

## Dependencies
- Google Colab

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

##### Here are some errors in the Kitti dataset. Some data in folder 0008 and 0009 of the training data do not conform to the format of this code, resulting in errors. Therefore, we copied folder 0000 and 0006 and replaced folders 0008 and 0009 when we executed.

#### *3. mount google drive.*
```
from google.colab import drive
drive.mount('/content/drive')
```

#### *4. Install dependency*

```
!pip install -r /content/drive/MyDrive/DeepFusionMOT/requirements.txt
```

#### *5. Change files' path
in main.py line 89
```
file_path = '/content/drive/MyDrive/DeepFusionMOT/results'```

in main.py line 96
```
default='/content/drive/MyDrive/DeepFusionMOT/config/kitti.yaml'```



#### *6. Run main.py*

```
python main.py
```


#### *6. KITTI MOT Evaluation*

If you want to evaluate the tracking results using the evaluation tool on the KITTI website, you will need to go https://github.com/JonathonLuiten/TrackEval to download the evaluation code and follow the appropriate steps to set.

Using  3D detections of PointRCNN  and 2D detections of RRC,  the following results will be obtained.

|                      | HOAT( **↑)** | **DetA( **↑)**** | **AssA**(**↑)** | IDSW（↓） | MOTP(**↑)** | MOTA(**↑)** | FPS（↑） |
| :------------------: | :----------: | :--------------: | :-------------: | :-------: | :---------: | :---------: | :------: |
| **Training dataset** |    77.45%    |      75.35%      |     79.85%      |    83     |   86.60%    |   87.28%    |   104    |
| **Testing dataset**  |    75.46%    |      71.54%      |     80.05%      |    84     |   85.02%    |   84.63%    |   110    |

### Acknowledgement

A portion  code is borrowed from [AB3DMOT](https://github.com/xinshuoweng/AB3DMOT) and [Deepsort](https://github.com/nwojke/deep_sort), and the visualization code from [3D-Detection-Tracking-Viewer](https://github.com/hailanyi/3D-Detection-Tracking-Viewer).  Many thanks to their wonderful work!


### Citation


If you find this work useful, please consider to cite our paper:

```
@ARTICLE{9810346,  
author={Wang, Xiyang and Fu, Chunyun and Li, Zhankun and Lai, Ying and He, Jiawei},  
journal={IEEE Robotics and Automation Letters},   
title={DeepFusionMOT: A 3D Multi-Object Tracking Framework Based on Camera-LiDAR Fusion With Deep Association},   
year={2022},  volume={7},  number={3},  pages={8260-8267},  doi={10.1109/LRA.2022.3187264}}

```
