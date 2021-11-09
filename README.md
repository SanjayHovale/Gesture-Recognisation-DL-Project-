# Gesture-Recognisation-DL-Project-

Imagine you are working as a data scientist at a home electronics company which manufactures state of the art smart televisions. You want to develop a cool feature in the smart-TV that can recognise five different gestures performed by the user which will help users control the TV without using a remote.

The gestures are continuously monitored by the webcam mounted on the TV. Each gesture corresponds to a specific command:

Thumbs up:  Increase the volume
Thumbs down: Decrease the volume
Left swipe: 'Jump' backwards 10 seconds
Right swipe: 'Jump' forward 10 seconds  
Stop: Pause the movie

Each video is a sequence of 30 frames (or images)

The training data consists of a few hundred videos categorised into one of the five classes. Each video (typically 2-3 seconds long) is divided into a sequence of 30 frames(images). These videos have been recorded by various people performing one of the five gestures in front of a webcam - similar to what the smart TV will use. 
The data is in a zip file. The zip file contains a 'train' and a 'val' folder with two CSV files for the two folders. These folders are in turn divided into subfolders where each subfolder represents a video of a particular gesture. Each subfolder, i.e. a video, contains 30 frames (or images). Note that all images in a particular video subfolder have the same dimensions but different videos may have different dimensions. Specifically, videos have two types of dimensions - either 360x360 or 120x160 (depending on the webcam used to record the videos). Hence, you will need to do some pre-processing to standardise the videos. 

 

Each row of the CSV file represents one video and contains three main pieces of information - the name of the subfolder containing the 30 images of the video, the name of the gesture and the numeric label (between 0-4) of the video.

 

Your task is to train a model on the 'train' folder which performs well on the 'val' folder as well (as usually done in ML projects). We have withheld the test folder for evaluation purposes - your final model's performance will be tested on the 'test' set.

 

To get started with the model building process, you first need to get the data on your storage. 

In order to get the data on the storage, perform the following steps in order

Open the terminal
 g0 down https://drive.google.com/uc?id=1ehyrYBQ5rbQQe6yL4XbLWe3FMvuVUGiL

 unzip Project_data.zip
 
 Now that you have got the data on the storage, let's look at the different choices of architectures you can use.
 Two Architectures: 3D Convs and CNN-RNN Stack
a.	LSTM based
b.	GRU based

# Results:
Multiple Experiments were performed on the given train and validation dataset. The following table includes the details of all the 19Experiments performed:

(Final Model)

Model18	Conv2D+(GRU)

Training Accuracy: 84.46%
Validation Accuracy: 73%

(Total params: 1,000,293)		

Model18: 3 Conv2D (16,32,64,128) pairs of layers, kernel size=(3,3), Batch Normalization(BN), Maxpooling2D, and include Dropouts at Fully Connected (FC) layer group (with GRU)

Decision: Best Stable Model: Model 18

Observations: Out of all the Conv3D and Conv2D+RNN models, Model 18 seems to be the best and stable model for the following reasons:
(1) High training and validation accuracies. Validation loss seems to be lesser than other model.
(2) Losses substantially decrease over epochs resulting in better and stable model.
(3) Efficient simple neural network with a smaller number of parameters


