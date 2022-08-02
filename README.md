# Detecting-and-recognizing-hand-sign-language
- One in every six people in the world has a hearing problem, and the number is rapidly increasing. According to Ms. Suchitra Prasansuk, President of the World Association of Audiologists, World Health Organization (WHO) statistics show that there were approximately 250 million people worldwide with deafness and hearing loss in 2010, and this number increased to approximately 360 million people in 2015. Our country currently has 1 to 2.5 million speech and hearing impaired people, roughly the population of a province. This demonstrates an increase in the number of people suffering from hearing loss. The ability to communicate verbally in the deaf community is severely limited due to impaired hearing. To replace the ability to communicate verbally, sign language, which uses the representation of hands and body, was created.
- Artificial intelligence (AI) is becoming increasingly popular and is affecting many aspects of daily life. Computer vision (CV) is a branch of artificial intelligence that includes digital image acquisition, processing, analysis, and recognition. Deep Learning Networks is a discipline that examines algorithms and computer programs so that computers may learn and make predictions in the same manner that humans do. It is used in a variety of applications, including science, engineering, and other fields of life, as well as object detection and classification. A good example is CNN (Convolutional Neural Network) learning to distinguish patterns from images by successively stacking layers on top of each other. CNN is now regarded as a model in many applications. Full image classifier and leverages technologies in the field of computer vision to leverage machine learning.
- More and more algorithms and models have been introduced for the recognition problem, including the YOLOv5 model, which is applied specifically to hand-sign recognition.
## I. OVERVIEW
* YOLO (You Only Look Once) that is a CNN network model used to detect and identify objects. Additionally, the convolution of layers will extract features in an image, and give the coordinates and order of labels assigned to each frame.
Furthermore, YOLO is considered to be the fastest algorithm in object recognition models but may not be the best.
* The main purpose of YOLO is to predict labels for objects in the classification and determine the coordinates of the object. Therefore, YOLO can detect many objects with different labels in the fastest time.
YOLO has released 5 versions so far as v1, v2, v3, v4 and v5. Each stage of YOLO has upgraded classification, optimized real-time label recognition and extended prediction limits for frames.
## II. YOLOv5 ARCHITECTURE
Architecturally, YOLOv5 consists of four main parts: input, backbone, neck, and output.
* To begin, YOLOv5 added a cross-stage partial network (CSPNet) into Darknet, resulting in CSPDarknet as the network's backbone. CSPNet solves the problem of repeated gradient information in large-scale backbones by integrating gradient changes into the feature map, reducing model parameters and floating-point operations per second (FLOPS), ensuring inference speed and accuracy while also reducing model size.
* In the hand symbol detection task, detection speed and accuracy are critical, and compact model size influences inference efficiency on resource-constrained edge devices.
* Second, to improve information flow, the YOLOv5 used a path aggregation network (PANet) as its neck. PANet uses a new feature pyramid network (FPN) structure with an improved bottom-up path, which improves low-level feature propagation. Simultaneously, adaptive feature pooling, which connects the feature grid and all feature levels, is used to ensure that useful information in each feature level propagates directly to the next subnetwork. PANet improves the utilization of accurate localization signals in lower layers, which obviously improves the object's location accuracy.
* Third, the YOLO layer, the head of Yolov5, generates different sizes of feature maps to achieve multi-scale prediction, allowing the model to handle small, medium, and large objects.
* ![alt text](https://www.researchgate.net/figure/The-network-architecture-of-Yolov5-It-consists-of-three-parts-1-Backbone-CSPDarknet_fig1_349299852)
* It consists of three parts: (1) Backbone: CSPDarknet, (2) Neck: PANet, and (3) Head: YOLO Layer. The data is first supplied into CSPDarknet, which extracts features, and then into PANet, which fuses them. Finally, YOLO Layer outputs detection results (class, score, location, size). 
YOLOv5 include 4 different types: YOLOv5-small, YOLOv5-medium, YOLOv5-large, YOLOv5-extraLarge. In this project, we use YOLOv5-small to train.
## III. HAND SYMBOL DETECTION
* We will use a camera and OpenCV in real-time to detect the hand symbol. It is commonly assumed that videos are composed of still images known as frames. Hand symbol detection was performed in every frame of a video. To detect hand symbols, we'll utilize the YOLOv5 pre-trained model.
* It is a real-time object detection algorithm. Because it has been trained to move quickly. Furthermore, it returns the relative accuracy. It is also intended to distinguish objects in a video or image.
* To begin, the detection of hand symbols involves the detection of a large number of images. In this section, we will label the frames in each image. Then, pass them to the model, which will train and return results.
* The hand symbol variable, which contains the height and width of the rectangle as well as the top-left corner coordinates enclosing the hand, can be used to generate a hand frame.
* The method for preprocessing is the same as the method for training the model described in the second section. The following step is to draw a rectangle on top of the face and label it based on the predictions.
* Though YOLOv5 and its variants are not as accurate. YOLOv5 performs admirably when confronted with standard-sized objects, but it is incapable of detecting small objects. When dealing with objects that appear to have rapidly changing properties, accuracy suffers significantly.
## IV. DATA SET
>We used images from our video to ensure that our learners could handle a variety of hand symbols. We will use a dataset of 4,1950 images cropped from video of hand symbols (including 0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, A, B, C, D, E, F, G, H, and I LOVE U) to prepare for the labeling and training process. A label will be attached to each image.
