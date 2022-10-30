# Importing pedestrian trajectories from video stream to PTV Vissim





<div align="center">
<p>
<img src="trackers/strong_sort/results/output_th025.gif" width="400"/> 
</p>
<br>
<div>
<a href="https://colab.research.google.com/drive/18nIqkBr68TkK8dHdarxTco6svHUJGggY?usp=sharing"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"></a>
</div>

</div>

## Before you run the tracker

1. Clone the repository recursively:

`git clone --recurse-submodules https://github.com/mikel-brostrom/Yolov5_StrongSORT_OSNet.git`

If you already cloned and forgot to use `--recurse-submodules` you can run `git submodule update --init`

2. Make sure that you fulfill all the requirements: Python 3.8 or later with all [requirements.txt](https://github.com/mikel-brostrom/Yolov5_DeepSort_Pytorch/blob/master/requirements.txt) dependencies installed, including torch>=1.7. To install, run:

`pip install -r requirements.txt`


## Tracking methods

```bash
$ python track.py --tracking-method strongsort
                                    ocsort
                                    bytetrack
```

## Tracking sources

Tracking can be run on most video formats

```bash
$ python track.py --source 0  # webcam
                           img.jpg  # image
                           vid.mp4  # video
                           path/  # directory
                           path/*.jpg  # glob
                           'https://youtu.be/Zgi9g1ksQHc'  # YouTube
                           'rtsp://example.com/media.mp4'  # RTSP, RTMP, HTTP stream
```



```bash


$ python track.py --source 0 --yolo-weights yolov5n.pt --img 640
                                            yolov5s.tflite
                                            yolov5m.pt
                                            yolov5l.onnx 
                                            yolov5x.pt --img 1280
                                            ...
```

### StrongSORT

```bash


$ python track.py --source 0 --strong-sort-weights osnet_x0_25_market1501.pt
                                                   mobilenetv2_x1_4_msmt17.engine
                                                   resnet50_msmt17.onnx
                                                   osnet_x1_0_msmt17.pt
                                                   ...
```


```bash
python track.py --source 0 --yolo-weights yolov5/weights/crowdhuman_yolov5m.pt --classes 0  # tracks persons, only
```

```bash
python track.py --source 0 --yolo-weights yolov5s.pt --classes 16 17  # tracks cats and dogs, only
```

```bash
python track.py --source ... --save-txt
```

