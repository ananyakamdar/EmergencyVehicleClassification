# Emergency Vehicle Classification
I recently participated in [Analytics Vidhya’s Computer Vision Hackathon]( https://datahack.analyticsvidhya.com/contest/janatahack-computer-vision-hackathon/) where the aim was to build an image classifier that can differentiate between emergency vehicles such as ambulances, police cars, fire trucks, etc. from non-emergency vehicles such as privately owned cars.

Being able to identify such vehicles is integral to building traffic light control systems that can monitor traffic and let emergency vehicles pass by quickly. In the future, self-driving car systems will also require such identifiers to ensure these vehicles reach their destination in time and are not obstructed by non-emergency ones.

## Dataset Description and Evaluation Metric
The data contains 2352 images of vehicles of which 1646 are for training and 706 are for testing. The images can be found [here]( https://drive.google.com/drive/folders/1tbEA55PxB35S4HVUimAuzTw8yIf5gSyv?usp=sharing).

The cv_train.csv file contains the names of images which are for training and their labels (0 for non-emergency vehicles and 1 for emergency vehicles). The cv_test.csv file contains the names of the images which are for testing.

The evaluation metric for this competition is **Accuracy**.

## Approach
We tried three Convolutional Neural Networks to build the image classifier. Using 5-fold cross validation, we run the models for 5 epochs during each fold. Predictions are made (and saved) for the testing images at the end of each fold. Once all the training is completed on all folds, the average of the predictions for all the folds is calculated. Finally, the predictions of all folds and the average predictions are submitted. 

**1. Neural network with 3 convolutional layers**: There is a trade-off between the complexity of the neural network and time taken for training. Thus a 3 convolutional layer network gives a decent accuracy which is approximately between 85-90% for the different folds.

**2. Pretrained keras model ResNet152V2 with 2 additional convolutional layers**: Pretrained models have the advantage of being trained on large datasets for a long time to extract as many features from the data as possible. Using this information and transferring it to our model helps us greatly by increasing the accuracy to approximately 95-99%. The validation accuracy using this model reaches 100%, but the score on submission is lower due to the model overfitting on the training data.

**3. Pretrained keras model InceptionResNetV2 with 2 additional convolutional layers**: This model gives an accuracy of around 96-98% on both, the training and the testing data, and is used for the final submission after some parameter tuning.

The Google Colab notebook with the codes can be found [here](https://colab.research.google.com/drive/1KaCfsqa_AA4YQ3rkc0zrPbSc7cZxXVzz?usp=sharing)

## Results
Our rank on the Public Leaderboard was **56** out of 10000+ participants, with a score of **0.96875**. On the Private Leaderboard our rank was 103 with a score of 0.9545.
