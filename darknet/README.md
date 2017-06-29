#Darknet#
Darknet is an open source neural network framework written in C and CUDA. It is fast, easy to install, and supports CPU and GPU computation.

For more information see the [Darknet project website](http://pjreddie.com/darknet).

For questions or issues please use the [Google Group](https://groups.google.com/forum/#!forum/darknet).

YOLOv2 project page: Convolutional Neural Networks http://pjreddie.com/darknet/yolo

# How to setup and run Yolo

### Step 1: Install dependencies

- [ ] GPU : run two scripts
      https://github.com/hanxvn/cv-utils/blob/master/setup_cuda_8_0_step_0.sh
      and
      https://github.com/hanxvn/cv-utils/blob/master/setup_cuda_8_0_step_1.sh
      
- [ ] OpenCV: run the script https://github.com/hanxvn/cv-utils/blob/master/open_cv_2_4_13_install.sh

### Step 2: Clone the repo

` git clone https://github.com/hanxvn/yolo.git`

### Step 3: Dataset

Use `darknet/script/.sh` to get any neccessary dataset.


### Step 4: Modify configuration file

1. Build darknet

Modify the following lines in `Makefile` according to your system (GPU vs non-GPU, OpenCV vs non-OpenCV etc)

`GPU=0
CUDNN=0
OPENCV=0
DEBUG=0`

then use `make` to build darknet.

2. Train a model

Modify `Makefile` as your configuration. Then `make train` or `make train-gpus`

3. Test a model

Modify `Makefile` as your configuration. Then `make test`

### Step 5: Training

`wget a pretrained model` as defined in `Makefile`, e.g., `wget https://www.dropbox.com/s/xen6a1yzf7qpbq4/darknet19_448.conv.23`. The pretrained model should be in `darknet` directory.

`make train` or `make train-gpus`

### Step 6: Testing

`make test` or `make test-camera`
