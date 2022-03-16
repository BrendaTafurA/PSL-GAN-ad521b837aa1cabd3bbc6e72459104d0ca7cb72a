# PSL-KNN
Knn model to classify Peruvian Sign Language signs

The purpose of this dataset is to perform different experiments to obtain the accuracy of each one of them and see how it changes according to certain factors. 

For example:

1. Whether you are using the MediaPipe holistic model only or the holistic model plus the hand model
2. Whether frames are being filtered or completed. 
3. Is it analyzed with Principal Component Analysis (6 and 10 components) and without it.
4. The whole dataset and a single dataset with verbs is analyzed.

How to get datasets:

The original preprocessing code from the paper "PeruSIL: A Framework to Build a Continuous Peruvian Sign Language Interpretation Dataset" (https://github.com/gissemari/PeruvianSignLanguage/blob/master/1.Preprocessing/Keypoints/ConvertVideoToKeypoint.py) was refactored. The refactored version is authored by Stev Huamán (https://github.com/StevRamos/PSL-GAN/blob/ad521b837aa1cabd3bbc6e72459104d0ca7cb72a/create_dataset.py). It basically performs the same preprocessing but in a different format, in addition to applying some filters. 

The filters consist of that it is required that all videos have the same amount of frames (same frame length), all frames must have the same amount of keypoints and these must be the same keypoints. In addition, it is established that there must be an exact number of frames and instances. For this purpose, two scenarios were used: 

1. min_frames = 10 and min_instances = 10
2. min_frames = 15 and min_instances = 10

Thus, only the videos that meet these conditions are taken and all these data are stored in a dataframe.

For this work, Stev's version was used with some changes. These were: 

1. Finger landmarks were added, for this, now 75 landmarks are retrieved (32 pose model, 21 hand model and 21 left hand).  
2. An additional line was added to obtain the dataset with a different format:

A. One in which the "x" and "y" coordinate values are in the form of rows (the original: Stev's code).
B. One in which the "x" and "y" coordinates are in the form of columns. In addition, as part of the columns are the applied filters, which should be "True", since we only take the data that meet the specified filters (the aggregated version). Name's files end with "shaping".

Both of them were saved in "csv" format.








