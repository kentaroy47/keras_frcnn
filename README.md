# Keras Faster-RCNN

 this is a very userful implementation of faster-rcnn based on tensorflow and keras, the model is very clear and just saved in .h5 file, out of box to use, and easy to train on other data set with full support. if you have any question, feel free to ask me via wechat: jintianiloveu

## Requirements
Basically, this code supports both python2.7 and python3.5, the following package should installed:
* tensorflow
* keras
* scipy
* cv2

## Training Kitti
(added by kentaro47)
* Download the KITTI training example from [here](http://www.cvlibs.net/download.php?file=data_object_image_2.zip) and [here](http://www.cvlibs.net/download.php?file=data_object_label_2.zip)

* create format for training
execute
'python generate_simple_kitti_anno_file.py /path/to/unzipped/image_2/ /path/to/unzipped/label_2/'
to get kitti_simple_label.txt. use the training folder to generate .txt file for training, and use the testing folder for test purposes.

* training with dataset
execute 
'python train_frcnn_kitti.py'

* evaluating with dataset
create test data by 
'python generate_simple_kitti_anno_file.py /path/to/unzipped/testing/image_2/ /path/to/unzipped/testing/label_2/'

execute 
'python test_frcnn_kitti.py'


## Train New Dataset

to train a new dataset is also very simple and straight forward. Simply convert your detection label file whatever format into this format:

```
/path/training/image_2/000000.png,712.40,143.00,810.73,307.92,Pedestrian
/path/training/image_2/000001.png,599.41,156.40,629.75,189.25,Truck
```
Which is `/path/to/img.png,x1,y1,x2,y2,class_name`, with this simple file, we don't need class map file, our training program will statistic this automatically.

## For Predict

If you want see how good your trained model is, simply run:
```
python test_frcnn_kitti.py
```
you can also using `-p` to specific single image to predict, or send a path contains many images, our program will automatically recognise that.

**That's all, help you enjoy!**
