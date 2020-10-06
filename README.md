I recently participated in [Analytics Vidhya’s Computer Vision Hackathon]( https://datahack.analyticsvidhya.com/contest/janatahack-computer-vision-hackathon/) where the aim was to build an image classifier that can differentiate between emergency vehicles such as ambulances, police cars, fire trucks, etc. from non-emergency vehicles such as privately owned cars.

Being able to identify such vehicles is integral to building traffic light control systems that can monitor traffic and let emergency vehicles pass by quickly. In the future, self-driving car systems will also require such identifiers to ensure these vehicles reach their destination in time and are not obstructed by non-emergency ones.

##Dataset Description and Evaluation Metric
The data contains 2352 images of vehicles of which 1646 are for training and 706 are for testing. The images can be found [here]( https://drive.google.com/drive/folders/1tbEA55PxB35S4HVUimAuzTw8yIf5gSyv?usp=sharing).

The cv_train.csv file contains the names of images which are for training and their labels (0 for non-emergency vehicles and 1 for emergency vehicles). The cv_test.csv file contains the names of the images which are for testing.
