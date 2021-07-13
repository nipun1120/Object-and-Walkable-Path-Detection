# Object-and-Walkable-Path-Detection

Object detection and walkable path detection is the task of detecting and labeling all objects in an image or video and giving a suitable walking path based on the detection. It can be used to aid blind people and robots.

The obstacle detection has been implemented by detecting objects using SSD inception v2 which has been trained on the COCO dataset. A region of interest has been defined for the detection of the obstacles in our path. Once the location of the obstacle is detected on our video frame, the class and accuracy of the obstacle detected are displayed. Based on the detected locations of the obstacles, the necessary instructions are passed to the user. The instructions include  "Left",
 
"Right" or "Stop" For example, if the obstacle lies on the left side of the frame, the user is instructed to move "Right" and vice-versa.
The final results show that using an object detection API using SSD inception is a robust way to detect obstacles in a video or frame and will smoothly help charter a path around them helping the blind and robots.

Image classification and object detection:

Image classification in computer vision takes an image and predicts the object in an image, while object detection not only predicts the object but also finds their location in terms of bounding boxes. For example, when we build a swimming pool classifier, we take an input image and predict whether it contains a pool, while an object detection model would also tell us the location of the pool.
SSD

The SSD head is just one or more convolutional layers added to this backbone and the outputs are interpreted as the bounding boxes and classes of objects in the spatial location of the final layers activations. Next, let's go through the important concepts/parameters in SSD.
Grid Cell:

SSD divides the image using a grid and have each grid cell be responsible for detecting objects in that region of the image. Detection objects simply means predicting the class and location of an object within that region. If no object is present, we consider it as the background class and the location is ignored.
Anchor box:

SSD uses a matching phase while training, to match the appropriate anchor box with the bounding boxes of each ground truth object within an image. Essentially, the anchor box with the highest degree of overlap with an object is responsible for predicting that object’s class and its location. This property is used for training the network and for predicting the detected objects and their locations once the network has been trained.
Aspect ratio

Not all objects are square in shape. Some are longer and some are wider, by varying degrees. The SSD architecture allows pre-defined aspect ratios of the anchor boxes to account for this. The ratios parameter
 
can be used to specify the different aspect ratios of the anchor boxes associates with each grid cell at each zoom/scale level
Zoom level

It is not necessary for the anchor boxes to have the same size as the grid cell. We might be interested in finding smaller or larger objects within a grid cell. The zooms parameter is used to specify how much the anchor boxes need to be scaled up or down with respect to each grid cell. Just like what we have seen in the anchor box example, the size of the building is generally larger than the swimming pool.
TENSORFLOW OBJECT DETECTION API:

The TensorFlow object detection API is the framework for creating a deep learning network that solves object detection problems. There are already pretrained models in their framework which they refer to as Model Zoo. This includes a collection of pretrained models trained on the COCO dataset. These models can be used for inference if we are interested in categories only in this dataset.
COCO DATASET:

The Computer Vision Benchmark

The COCO dataset is labeled, providing data to train supervised computer vision models that are able to identify the common objects in the dataset. Of course, these models are still far from perfect, so the COCO dataset provides a benchmark for evaluating the periodic improvement of these models through computer vision research.

A Checkpoint for Transfer Learning

Another motivation for the COCO dataset is to provide a base dataset to train computer vision models. Once the model is trained on the COCO dataset, it can be fine-tuned to learn other tasks, with a custom dataset.
