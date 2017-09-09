# Semantic Segmentation
### Introduction
In this project, you'll label the pixels of a road in images using a Fully Convolutional Network (FCN).

### Architecture:
 The  design implementation here is very close to this paper on 
 [Fully Convolutional Networks for Semantic Segmentation](https://people.eecs.berkeley.edu/~jonlong/long_shelhamer_fcn.pdf).
 ![Layer working ](Screen%20Shot%202017-09-09%20at%202.26.31%20PM.png).
 
In this we are using a pre-trained VGG-16 network and replaced the final layer fully connected layer to  a 1x1 CNN.
 The depth setting was equal to the number of classes we have and in this case we are finding pixels which are roads with non roads .
 
Then performance of the network was inproved with the addition of skip  connection.
Here we do a element wise add  with  the vgg 3rd and 4th layer  to the 1x1 convolved layer 7 and layer 4  respectively.

#### Parameters used:
- Loss function: Cross entropy
- Optimizer: Adam optimizer
- learning rate: 0.0001
- key-prob:0.5
- epoach :50
- batch :10


###Ouput

Here is the output of the FCN to find the roads.
As you can see the  green highlighted  area are the pixels that are supposed to be road surface to the 
FCN.



![segmetation1](um_000014.png)
![segmetation1](um_000027.png)
![segmetation1](um_000037.png)
![segmetation1](um_000077.png)
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
 - Newest inference images from `runs` folder
 
 ## How to write a README
A well written README file can enhance your project and portfolio.  Develop your abilities to create professional README files by completing [this free course](https://www.udacity.com/course/writing-readmes--ud777).
