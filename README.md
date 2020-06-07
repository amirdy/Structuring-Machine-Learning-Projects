# Structuring Machine Learning Projects
Based on the Structuring Machine Learning Projects course Published on Coursera

## 1- Dataset spliting:

#### Number of samples: 100, 1000, 10000
* Train set : 60 %
* Validation set (Developement set) : 20 %
* Test set: 20 %

#### Number of samples: 1000000
* Train set : 98 %
* Validation set (Developement set) : 1 %
* Test set: 1 %

#### Important Notices:
- Validation set and Test set should have thesame distribution
- Andrew NG:
  > Choose a dev set and test set to reflect data you expect to get in the future and consider important to do well on 

## 2- Defining single number evaluation metric:
* Like ***Accuracy*** or ***Recall*** or combination of them (***F1 score***) and etc.
* If it can not be just 1 metric :
  * For exmaple: ***Acuuracy*** and ***run*** time.
    * In this situation our main metric (***optimization metric***) is ***Accuracy*** and ***run time*** is ***Satisficing metric***. It means that we only care about the run time to be less than 1 second but how much? not important!
* This single number evaluation metric, should be at least equal to human level performance (by training)
* human level performance and single number evaluation metric have the same type (for example both are accuracy)
* How we find the value of human level performance (like accuracy )? 
  * By asking people to lable some bunch of images and calculate the accuracy

