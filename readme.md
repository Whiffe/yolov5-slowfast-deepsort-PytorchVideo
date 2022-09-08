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
   
   ```
   apt update
   apt install libgl1-mesa-glx

   ```
   
3. clone this repo:

   使用github
   ```
   cd /home
   git clone https://github.com/Whiffe/yolov5-slowfast-deepsort-PytorchVideo.git
   ```
   
   或者使用gitee
   
   ```
   cd /home
   git clone https://gitee.com/YFwinston/yolov5-slowfast-deepsort-PytorchVideo.git
   ```
   

2. create a new python environment (optional 可选):

   ```
   conda create -n {your_env_name} python=3.8.12
   conda activate {your_env_name}
   ```

3. install requiments:

   ```
   cd /home/yolov5-slowfast-deepsort-PytorchVideo
   pip install -r requirements2.txt
   ```
   
4. download weights file(ckpt.t7) from [[yolov5_file]](https://share.weiyun.com/xCgma1LG) to this folder:

   ```
   ./deep_sort/deep_sort/deep/checkpoint/
   ```
   
   我是将ckpt.t7放在了：/user-data/yolov5_file/
   
   所以执行：
   
   ```
   mkdir -p /home/yolov5-slowfast-deepsort-PytorchVideo/deep_sort/deep_sort/deep/checkpoint/
   cp /user-data/yolov5_file/ckpt.t7 /home/yolov5-slowfast-deepsort-PytorchVideo/deep_sort/deep_sort/deep/checkpoint/ckpt.t7
   ```
5. download file(SLOWFAST_8x8_R50_DETECTION.pyth) from [[slowfast_file]](https://share.weiyun.com/EUi4NvnM) to this folder:
   
   我是将SLOWFAST_8x8_R50_DETECTION.pyth放在了：/user-data/slowfast_file/
   
   所以执行：
   ```
   mkdir -p /root/.cache/torch/hub/checkpoints/ 
   cp /user-data/slowfast_file/SLOWFAST_8x8_R50_DETECTION.pyth /root/.cache/torch/hub/checkpoints/SLOWFAST_8x8_R50_DETECTION.pyth
   ```

6. download file(yolov5l6.pt) from [[yolov5_file]](https://share.weiyun.com/xCgma1LG) to this folder:

   我是将yolov5l6.pt放在了：/user-data/yolov5_file/
   
   所以执行：
   ```
   cp /user-data/yolov5_file/yolov5l6.pt /home/yolov5-slowfast-deepsort-PytorchVideo/yolov5l6.pt
   ```
7. download file(master.zip) from [[yolov5_file]](https://share.weiyun.com/xCgma1LG) to this folder:

   我是将yolov5-master.zip放在了：/user-data/yolov5_file/
   
   所以执行：
   ```
   cp /user-data/yolov5_file/yolov5-master.zip /root/.cache/torch/hub/master.zip
   ```
   

8. test on your video:

   
   ```
   python yolo_slowfast.py --input {path to your video}
   ```
   
   我将1.mp4存放在了/home/yolov5-slowfast-deepsort-PytorchVideo/demo/中
   
   所以执行：
   
   
   ```
   cd /home/yolov5-slowfast-deepsort-PytorchVideo
   mkdir demo
   ```
   
   ```
   cd /home/yolov5-slowfast-deepsort-PytorchVideo
   python yolo_slowfast.py --input ./demo/1.mp4
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


## Stargazers over time

[![Stargazers over time](https://starchart.cc/Whiffe/yolov5-slowfast-deepsort-PytorchVideo.svg)](https://starchart.cc/Whiffe/yolov5-slowfast-deepsort-PytorchVideo)



