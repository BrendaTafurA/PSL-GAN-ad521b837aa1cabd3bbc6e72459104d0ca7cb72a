# PSL-KNN
Knn model to classify Peruvian Sign Language signs

The purpose of this dataset is to perform different experiments to obtain the accuracy of each one of them and see how it changes according to certain factors. For example:

Experiment 1: In official.py are the experiments with 10 frames and 480 features ( 10 frames * 24 landmarks * 2 (x, and y) ). 

Results 1:  
10 frames were used as base, all instances (including spelling ones but exluding NNN instances) were used and the metric accuracy was used.

                      10 frames
base (all dataset)      18% 
verbs                   31% 
adverbs                 27% 
nouns (all nouns)       8%
nouns (some nouns)      62%
adjectives              60%

Experiment 2: In new_analysis.py you can find the experiments.

Results 2:  
20 frames (920 features), 15 frames (690 features), 10 frames (460 features) were used as a base. Also, all instances were used (including spelling but exluding NNN instances) and the accuracy metric was used.

                   20 frames 15 frames 10 frames
base (all dataset)      8%      11%        10% 
verbs                   23%     22%        27% 

