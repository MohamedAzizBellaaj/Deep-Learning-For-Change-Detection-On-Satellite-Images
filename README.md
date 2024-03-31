# Deep Learning For Change Detection On Satellite Images

This is a continuation on the code written by Elyes Ouerghi.

This software aims at providing an evaluation for the change detection problem as described by the article :  "Multitask learning for large-scale semantic change detection" by Daudt et al. The code in mainly adapted from the original author's repository at "<https://github.com/rcdaudt/fully_convolutional_change_detection>".

The algorithm can be executed by running the function compute_map in main.py. It takes as input two color images in PNG format. Both images should be satellites images of the same area, and co-registered. It works best on images from the Sentinel-2 satellite. If both images do not have the same size, the images will be automatically cropped. The demo expects values stored on 8 bits. If the input images do not match this requirement, the images will be converted to 8 bit.
The output image is a change map. For each pixel in the input images, the value of the change map is 1 if a change is detected and 0 otherwise.

The network weights are in the file "fresunet3_final.pth.tar" and the network architecture is in the file "fresunet.py".

Here is the filepath structure of the dataset needed to run notebook correctly:

````
Onera
├── Images
│   ├── abudhabi
│   │   ├── imgs_1
│   │   ├── imgs_1_rect
│   │   ├── imgs_2
│   │   ├── imgs_2_rect
│   │   └── pair
│   ├── aguasclaras
│   │   ...
│   └── ...
├── Test
└── Train
