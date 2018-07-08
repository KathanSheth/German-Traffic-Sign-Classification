# German Traffic Dataset Study Project

This is my second project (after Dogs_vs_Cats) on Image classification using CNN and Keras. Previously, I have implemented same project using HOG features and Linear SVM. In this implementation, I have tried simple MLP and different CNN architecture.

Original Dataset can be found here:

http://benchmark.ini.rub.de/?section=gtsrb&subsection=dataset

Overview of Dataset:

43 Classes
~50K total traffic sign images

The original dataset contains following properties:

	-	The images contain one traffic sign each
	-	Images contain a border of 10 % around the actual traffic sign (at least 5 pixels) to allow for edge-based approaches
	-	Images are stored in PPM format (Portable Pixmap, P6)
	-	Image sizes vary between 15x15 to 250x250 pixels
	-	Images are not necessarily squared
	-	The actual traffic sign is not necessarily centered within the image.This is true for images that were close to the image border in the full camera image
	-	The bounding box of the traffic sign is part of the annotatinos (see below)

Some preprocessing is required (Like center the image, remove borders, convert all images to same size etc.) 

**NOTE 1 : I have not done this preprocessing. Rather I have used already preprocesses data which is stored in `.pickle` format. We can easily find it online.**


Again, same as my previous project (Dogs_vs_Cats), I have divided this project in four different notebooks.

Brief explanation of each:

**a)	1_German_Traffic_MLP.ipynb**

I have implemented a simple NN with two hidden layers each with 128 neurons. I have not performed any regularization or data augmentation here.

**b)	2_1_German_Traffic_LeNet_20_epochs.ipynb**

I have implemented a CNN architecture (Based on LeNet) and trained for 20 epochs.

**c)	2_2_German_Traffic_LeNet_12_epochs.ipynb**

This is same as above. The only difference in this notebook is the number of epochs (12 instead of 20)

**d)	3_1_German_Traffic_VggNet_Adam_lr_0009.ipynb**

Implemented a CNN architecture (Based on VGGNet) and trained with Adam optimizer.

**e)	3_2_German_Traffic_VggNet_Adam_lr_001.ipynb**

Same as above. Learning rate 0.001 instead of 0.0009

**f)	4_German_Traffic_VggNet_ImageDataGenerator.ipynb**

In this notebook, I have implemented same VGGNet architecture but rather than using manual data augmentation I have used Keras' ImageDataGenerator class to generate augmented data in real time. Also, I have used SGD optimizer here.

** Summary **

| File - Name                                       | Test Loss                 | Test Accuracy        | Saved Model                         |
|:--------------------------------------------------|:--------------------------|:---------------------|:------------------------------------|
| 1_German_Traffic_MLP.ipynb                        | 1.2018                    | 80.9817%             | Not Saved                           |
| 2_1_German_Traffic_LeNet_20_epochs.ipynb          | 0.3937                    | 93.6817%             | Not Saved                           |
| 2_2_German_Traffic_LeNet_12_epochs.ipynb          | 0.3288                    | 94.2913%             | Not Saved                           |
| 3_1_German_Traffic_VggNet_Adam_lr_0009.ipynb      | 0.1293                    | 97.4346%             | German_Traffic_VGGNET_Trial1.h5     |
| 3_2_German_Traffic_VggNet_Adam_lr_001.ipynb       | 0.1753                    | 97.3792%             | German_Traffic_VGGNET_Trial2.h5|  
| 4_German_Traffic_VggNet_ImageDataGenerator.ipynb  |                     |  | 


Image Reference:
https://www.researchgate.net
