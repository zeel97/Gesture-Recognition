# Gesture Recognition System

### Business Objective
Product development project for a television manufacturer looking to add a new feature to their TV sets: Gesture recogonition. 
The goal of the project is to train a model to recogonise 5 main hand gestures for pause, volume increase/decrease and forward and rewind by 10 seconds. 

### Dataset
A dataset of a few hundred categorised videos is used, which are about 2-3 seconds long. Each video is broken down into a sequence of 30 static frames. 
The dimensions of the videos vary between 360x360 and 120x160, basis the webcam used for recording. 

The .csv contains the name of the sub-folder containing the frames, name of the gesture and numeric label for the same

### Models Developed
Different variation of models were chosen and tested on the training and test accuracy. 
1. Conv3D
2. CNN + RNN
3. ResNet + RNN
4. Conv3D with GrayScale Image instead of RGB

### Hyperparameter Tuning
Test each variation with different hyperparamters to observe the variations and image of each on the train and test accuracy. The hyperparameters chosen were:
1. Changing batch size - from 10, 30, 50, 100, to 120 – Optimal Batch size was found to be 30 and 50
2. Changing No of Epochs - Optimal was 10, 15, 25
3. Resizing the images - Increased to 120 x 120, reduced to 60 x 60, optimal was 100 x 100
4. Image cropping – Did not yield much result
5. No of Images to be fed in system - Tried 30, 20, Optimal was 10 images
6. No of Channels - Tried with Grayscale to check if this is optimized, found training was limited
7. Batch Normalization - Did not yield much result, model accuracy kept on fluctuating with each epoch, No stability
8. L2 Normalization - Did not yield much result, in some cases information loss was observed
9. Learning Rate -With high in learning rate, the model was more unstable, bouncing around the local/global minima, by reducing learning rate, model seem to be more stable.

### Evaluation
The model with the best results was a Conv3D with 3 Hidden Layers, 1 Dense Layer and 1 Output Layer. 
Achieved training accuracy of 93% and validation accuracy of 73%. The model achieved minimum trainable parameters of 2,280,869, which invariably reduced the training time as compared to the other models tested.

Note: This was a group based project

