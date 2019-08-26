![Darknet Logo](http://pjreddie.com/media/files/darknet-black-small.png)

# Lambda Notes

### Installation

```
# Install OpenCV
sudo apt-get install build-essential
sudo apt-get install cmake git libgtk2.0-dev pkg-config libavcodec-dev libavformat-dev libswscale-dev
sudo apt-get install python-dev python-numpy libtbb2 libtbb-dev libjpeg-dev libpng-dev libtiff-dev libdc1394-22-dev

cd
wget https://github.com/opencv/opencv/archive/3.4.7.zip
unzip 3.4.7.zip
cd opencv-3.4.7

mkdir build
cd build

cmake -D CMAKE_BUILD_TYPE=Release -D CMAKE_INSTALL_PREFIX=/usr/local ..
make -j8
sudo make install

sudo /bin/bash -c 'echo "/usr/local/lib" > /etc/ld.so.conf.d/opencv.conf'
sudo ldconfig

# Install Darknet

cd
git clone https://github.com/lambdal/darknet.git
cd darknet
make -j8

# Verify Installation

./darknet
./darknet imtest data/eagle.jpg


# Run Object Detection
wget https://pjreddie.com/media/files/yolov3.weights
./darknet detector demo cfg/coco.data cfg/yolov3.cfg yolov3.weights
```

### Performance

27FPS on 2080Ti



![Darknet Logo](http://pjreddie.com/media/files/darknet-black-small.png)

# Darknet #
Darknet is an open source neural network framework written in C and CUDA. It is fast, easy to install, and supports CPU and GPU computation.

For more information see the [Darknet project website](http://pjreddie.com/darknet).

For questions or issues please use the [Google Group](https://groups.google.com/forum/#!forum/darknet).
