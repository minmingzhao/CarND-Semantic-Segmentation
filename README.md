# Semantic Segmentation
### Introduction
This is my 2nd project for Term 3 semantic segmentation using a Fully Convolutional Network (FCN).

### Approach
The encoder is VGG16 pretrained model. Decoder is fully convolutional network FCN8. Data is from KITTI road dataset. 

#### Archetecture
A pre-trained VGG-16 was followed by, instead of full connected layers, a 1x1 convolution with depth equal to number of classes (road/nonroad). Skip connections was used to improve performance. In this case, as the paper suggests, 1x1 convolution of layer 4 and 2x2 upsampled layers (output of layer 7). Same applied to 1x1 convolution of layer 3 and 2x2 conv2d transpose upsample of output of previous layer. Each convolution and transpose convolution layer include a kernel initializer and regularizer. 

#### Augmentation of image
Vertical image flipping was used as agumentation to improve the training dataset. 

#### Training parameter setting
keep_prob: 0.5
learning_rate: 0.00
epochs: 100
batch_size: 5

Training loss was reduced from initial 1.5 to 0.3 after 50 epochs, further reduced to 0.08 at 100 epochs. 

#### Sample image output

[um_000005.png]: ./runs/images/um_000005.png

[um_000019.png]: ./runs/images/um_000019.png

[um_000024.png]: ./runs/images/um_000024.png

[umm_000008.png]: ./runs/images/umm_000008.png

[umm_000014.png]: ./runs/images/umm_000014.png

[umm_000077.png]: ./runs/images/umm_000077.png


![alt text][um_000005.png]

![alt text][um_000019.png]

![alt text][um_000024.png]

![alt text][umm_000008.png]

![alt text][umm_000014.png]

![alt text][umm_000077.png]

### Setup
##### Frameworks and Packages
Make sure you have the following is installed:
 - [Python 3](https://www.python.org/)
 - [TensorFlow](https://www.tensorflow.org/)
 - [NumPy](http://www.numpy.org/)
 - [SciPy](https://www.scipy.org/)
##### Dataset
Download the [Kitti Road dataset](http://www.cvlibs.net/datasets/kitti/eval_road.php) from [here](http://www.cvlibs.net/download.php?file=data_road.zip).  Extract the dataset in the `data` folder.  This will create the folder `data_road` with all the training a test images.

### Start
##### Implement
Implement the code in the `main.py` module indicated by the "TODO" comments.
The comments indicated with "OPTIONAL" tag are not required to complete.
##### Run
Run the following command to run the project:
```
python main.py
```
**Note** If running this in Jupyter Notebook system messages, such as those regarding test status, may appear in the terminal rather than the notebook.

### Submission
1. Ensure you've passed all the unit tests.
2. Ensure you pass all points on [the rubric](https://review.udacity.com/#!/rubrics/989/view).
3. Submit the following in a zip file.
 - `helper.py`
 - `main.py`
 - `project_tests.py`
 - Newest inference images from `runs` folder  (**all images from the most recent run**)
 
 ## How to write a README
A well written README file can enhance your project and portfolio.  Develop your abilities to create professional README files by completing [this free course](https://www.udacity.com/course/writing-readmes--ud777).
