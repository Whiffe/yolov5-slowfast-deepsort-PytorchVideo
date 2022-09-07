# Yolov5+SlowFast+deepsort: Action Detection（PytorchVideo）
 

### A realtime action detection frame work based on PytorchVideo. 

#### Here are some details about our modification:

- we choose yolov5 as an object detector instead of Faster R-CNN, it is faster and more convenient
- we use a tracker(deepsort) to allocate action labels to all objects(with same ids) in different frames
- our processing speed reached 24.2 FPS at 30 inference batch size (on a single RTX 2080Ti GPU)

> 参考: 
> 
> [FAIR/PytorchVideo](https://github.com/facebookresearch/pytorchvideo); 
> 
> [Ultralytics/Yolov5](https://github.com/ultralytics/yolov5)
> 
> [yolo_slowfast](https://github.com/wufan-tb/yolo_slowfast)


#### Demo comparison between original and ours.



![image](https://img-blog.csdnimg.cn/92e00516f2984dfcb3ba4888fddde9dd.gif)
![image](https://img-blog.csdnimg.cn/c01edc763a744b9d8114b3973a4d0385.gif)


## Installation

使用AI平台：[https://cloud.videojj.com/auth/register?inviter=18452&activityChannel=student_invite](https://cloud.videojj.com/auth/register?inviter=18452&activityChannel=student_invite)

0. environment 环境
   ```
   Pytorch 1.10.1
   Python 3.8
   Cuda 11.1
   ```
1. 安装PytorchVideo:
   ```
   cd /home
   git clone https://gitee.com/YFwinston/pytorchvideo.git
   cd pytorchvideo
   pip install -e .
   ```
3. clone this repo:

   使用github
   ```
   git clone https://github.com/Whiffe/yolov5-slowfast-deepsort-PytorchVideo.git
   cd yolo_slowfast
   ```
   
   或者使用gitee
   
   ```
   git clone https://gitee.com/YFwinston/yolov5-slowfast-deepsort-PytorchVideo.git
   cd yolo_slowfast
   ```
   

2. create a new python environment (optional 可选):

   ```
   conda create -n {your_env_name} python=3.8.12
   conda activate {your_env_name}
   ```

3. install requiments:

   ```
   pip install -r requirements2.txt
   ```
   
4. download weights file(ckpt.t7) from [[yolov5_file]](https://share.weiyun.com/xCgma1LG) to this folder:

   ```
   ./deep_sort/deep_sort/deep/checkpoint/
   ```
   
   我是将ckpt.t7放在了：user-data/yolov5_file/
   
   所以执行：
   
   ```
   mkdir -p /home/yolo_slowfast/deep_sort/deep_sort/deep/checkpoint/
   cp /user-data/yolov5_file/ckpt.t7 /home/yolo_slowfast/deep_sort/deep_sort/deep/checkpoint/ckpt.t7
   ```
   

5. test on your video:

   ```
   python yolo_slowfast.py --input {path to your video}
   ```

   The first time execute this command may take some times to download the yolov5 code and it's weights file from torch.hub, keep your network connection.

## References

Thanks for these great works:

[1] [Ultralytics/Yolov5](https://github.com/ultralytics/yolov5)

[2] [ZQPei/deepsort](https://github.com/ZQPei/deep_sort_pytorch) 

[3] [FAIR/PytorchVideo](https://github.com/facebookresearch/pytorchvideo)

[4] AVA: A Video Dataset of Spatio-temporally Localized Atomic Visual Actions. [paper](https://arxiv.org/pdf/1705.08421.pdf)

[5] SlowFast Networks for Video Recognition. [paper](https://arxiv.org/pdf/1812.03982.pdf)

## Citation

If you find our work useful, please cite as follow:

```
{   yolo_slowfast,
    author = {Wu Fan},
    title = { A realtime action detection frame work based on PytorchVideo},
    year = {2021},
    url = {\url{https://github.com/wufan-tb/yolo_slowfast}}
}
```

### Stargazers over time

[![Stargazers over time](https://starchart.cc/wufan-tb/yolo_slowfast.svg)](https://starchart.cc/wufan-tb/yolo_slowfast)


