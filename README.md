This is an object tracking by detection implemented with YOLOv4, DeepSort, and TensorFlow. YOLOv4 is used to perform object detections and Deep SORT (Simple Online and Realtime Tracking with a Deep Association Metric) used for object tracking.

### Requirements
### Module requirements
(TensorFlow 2 packages require a pip version >19.0.)
```bash
# TensorFlow CPU
pip install -r requirements.txt

# TensorFlow GPU
pip install -r requirements-gpu.txt
```
### Nvidia Driver for GPU (If you want to run the code in your local GPU)
You need CUDA Toolkit
https://developer.nvidia.com/cuda-10.1-download-archive-update2

## Downloading YOLOv4 Pre-trained Weights
Download pre-trained yolov4.weights file: https://drive.google.com/file/d/1ccUlgyncCGUO5ME6IujMjqrBmakUVb-Y/view?usp=sharing

Move youre dowloaded yolov4.weights to **yolo/weights** folder.

You can youse also yolov4-tiny.weights if you want a smaller model that is faster at running detections but less accurate. Download this file here: https://drive.google.com/file/d/1Qq7PLyeNhnn2Beog90SMaiLpgU-3TzoY/view?usp=sharing

## Running the Tracker with YOLOv4
First convert the weights just dowloaded into the corresponding TensorFlow model which will be saved to a checkpoints folder:
```bash
# Convert weights to tensorflow model
python conversion.py --model yolov4 

#Then run the tracker to begin tracking for your video
python tracker.py --video test.mp4 --output ./outputs/result.avi --model yolov4

# If you want to run the tracker for your webcam
python object_tracker.py --video 0 --output ./outputs/webcam.avi --model yolov4
```

You can review your output videos is the outputs folder.

Check the tracker.py file to see all parameters allowed.  

### References  

   Huge shoutout goes to hunglc007 and nwojke for creating the backbones of this repository:
  * [theAIGuysCode yolov4-deepsort](https://github.com/theAIGuysCode/yolov4-deepsort)
  * [Deep SORT Repository](https://github.com/nwojke/deep_sort)
