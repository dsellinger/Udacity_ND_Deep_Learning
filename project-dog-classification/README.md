[//]: # (Image References)

[image1]: ./images/sample_dog_output.png "Sample Output"
[image2]: ./images/vgg16_model.png "VGG-16 Model Layers"
[image3]: ./images/vgg16_model_draw.png "VGG16 Model Figure"


## Udacity Project - Dog Breed classification 

The project's goal was to build an app to identify the dog breed of a given dog image. Additionally also Human faces will be processed and the most resembling dog breeds will be predicted.

![Sample Output][image1]

The project was set up in a pipeline of processing steps:

## Detect Humans
Function to identify if the image represents a human. For this purpose OpenCV's implementation of Haar feature-based cascade classifiers (https://docs.opencv.org/trunk/d7/d8b/tutorial_py_face_detection.html) was used. 
Accuracy for humans: 98%
False positives/dogs: 17%

## Detect Dogs
Function to identifiy if the image represents a dog based on the pretrained VGG16 model.
Accuracy for dogs: 100%
False positives/humans: 1%

## CNN to Classify Dog Breeds from Scratch
Use a CNN build from sratch to predict dog breeds.
Used the following architecture:
	CNN_1: kernels 3, stride 2, padding 1
	MaxPooling
	CNN_2: kernels 3, stride 2, padding 1
	MaxPooling
	CNN_3: kernels 3, stride 1, padding 1
	MaxPooling
	FC_1 (dropout: 0.25)
	FC_2
accuaracy after 45 epochs: 19%

## CNN to Classify Dog Breeds from Scratch
Use a pretrained model to predict dog breeds.
Based on the VGG16 architecture - accuracy: 64%
Based on the resnet50 architecture - accuracy: 84% after 20 epochs
