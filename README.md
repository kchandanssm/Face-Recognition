To create a complete project on Face Recognition, we must work on 3 very distinct phases:

- Face Detection and Data Gathering 

- Train the Recognizer 

- Face Recognition


Face Detection:-

The most basic task on Face Recognition is of course, "Face Detecting". Before anything, you must "capture" a face (Phase 1) in order to recognize it, when compared with a new face captured on future (Phase 3). 

The most common way to detect a face (or any objects), is using the "Haar Cascade classifier".
Here we will work with face detection. Initially, the algorithm needs a lot of positive images (images of faces) and negative images (images without faces) to train the classifier. Then we need to extract features from it. The good news is that OpenCV comes with a trainer as well as a detector. If you want to train your own classifier for any object like car, planes etc. you can use OpenCV to create one. Its full details are given here: Cascade Classifier Training.

Run face_detection.py.


Data Gathering:-

First, create a directory where you develop your project, for example, FacialRecognitionProject:

"mkdir FacialRecognitionProject"

In this directory, besides the 3 python scripts that we will create for our project, we must have saved on it the Facial Classifier.

Next, create a subdirectory where we will store our facial samples and name it "dataset":
"mkdir dataset"

Run face_dataset.py

The code is very similar to the code that we saw for face detection. What we added, was an "input command" to capture a user id, that should be an integer number (1, 2, 3, etc)

eg:- face_id = input('\n enter user id end press  ==>  ')


On my code, I am capturing 500 samples from each id. You can change it on the last "elif". The number of samples is used to break the loop where the face samples are captured.


Trainer:-

On this second phase, we must take all user data from our dataset and "trainer" the OpenCV Recognizer. This is done directly by a specific OpenCV function. The result will be a .yml file that will be saved on a "trainer/" directory.

"mkdir trainer"

Confirm if you have the PIL library installed on your Rpi. If not, run the below command in Terminal:
"pip install pillow"


We will use as a recognizer, the LBPH (LOCAL BINARY PATTERNS HISTOGRAMS) Face Recognizer, included on OpenCV package. We do this in the following line:

Run train.py

We are including here a new array, so we will display "names", instead of numbered ids:


Recognizer:-
Now, we reached the final phase of our project. Here, we will capture a fresh face on our camera and if this person had his face captured and trained before, our recognizer will make a "prediction" returning its id and an index, shown how confident the recognizer is with this match.

We are including here a new array, so we will display "names", instead of numbered ids:
names = ['None', 'Marcelo', 'Paula', 'Ilza', 'Z', 'W']

Run face_recognition.py





# Face-Recognition
