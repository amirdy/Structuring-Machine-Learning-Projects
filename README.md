# Structuring Machine Learning Projects
Based on the Structuring Machine Learning Projects course Published on Coursera [[click]](https://www.coursera.org/learn/machine-learning-projects/home/welcome)

## 1- Dataset spliting:

#### Assumption:

Validation set = Developement set = Dev set
#### Number of samples: 100, 1000, 10000
* Train set : 60 %
* Dev set : 20 %
* Test set: 20 %

#### Number of samples: 1000000
* Train set : 98 %
* Dev set : 1 %
* Test set: 1 %

#### Important Notices:
- Dev set and Test set should have the same distribution.
- Size of test set [Andrew NG]:
  > Set your test set to be big enough to give high confidence in the overall performance of your system.
- Choosing dev set [Andrew NG]:
  > Choose a dev set and test set to reflect data you expect to get in the future and consider important to do well on.

## 2- Defining single number evaluation metric:
* Like <ins>Accuracy</ins> or <ins>Recall</ins> or combination of them (<ins>F1 score</ins>) and etc.
* If it can not be just 1 metric :
  * For exmaple: ***Acuuracy*** and ***run*** time.
    * In this situation our main metric (***optimization metric***) is ***Accuracy*** and ***run time*** is ***Satisficing metric***. It means that we only care about the run time to be less than 1 second but how much? not important!
* This single number evaluation metric, should be at least equal to human level performance (by training)
* human level performance and single number evaluation metric have the same type (for example both are accuracy)
* How we find the value of human level performance (like accuracy )? 
  * By asking people to lable some bunch of images and calculate the accuracy
  
### Trick:
For cat dectector if you want specific breed to be recognized correctly, we can change the loss as below:

<img src="https://latex.codecogs.com/svg.latex?\dpi{100}\frac{1}{M}\sum_{i=1}^Mloss(y_i,\widehat{y}_i)\Rightarrow%20\frac{1}{\sum%20W_i}\sum_{i=1}^M%20W_i\cdot%20loss(y_i,\widehat{y}_i)\small{,\%20\%20\%20\%20\%20W_i=\begin{cases}10%20&%20X_i%20=%20specific\%20cat\\1%20&%20X_i\neq%20specific\%20cat%20\end{cases}}" /> 

  The error(evaluation metric) now will be :
  
<img src="https://latex.codecogs.com/svg.latex?\dpi{100}error%20=%20\frac{1}{\sum%20W_i}%20\sum_{i=1}^M%20W_i%20\cdot%201\{y_i%20\neq%20\widehat{y}_i%20\}" /> 


### Some definitions:
Bayes optimal error : Best possible error

Human level error can be a proxy for bayes optimal error (for a task that humans can do quite well like computer vision).
<img src="https://latex.codecogs.com/svg.latex?\dpi{100}\text{Human%20level%20error}\leq\text{%20%20bayes%20optimal%20error}" /> 

<img src="https://latex.codecogs.com/svg.latex?\dpi{100}\text{Avoidable%20bias}=\text{Bayes%20error}-\text{Training%20error}" /> 

<img src="https://latex.codecogs.com/svg.latex?\dpi{100}\text{Varaince}=\text{Training%20error}-\text{dev%20error}" /> 

    
Imporve fitting training set on cost function (reduce avoidable bias):
- Training bigger model
- Train longer/better optimization algorithms (such as momentum, Rmsprob, Adam, ...)
- Changing NN architecture/hyperparameters (such as activation functions,number of layers, trying CNN/RNN, ...)

Imporve fitting dev set on cost function (reduce variance):
- Get more data
- Using regularization (such as L2, dropout, data augmentation, ...)
- Changing NN architecture/hyperparameters (such as activation functions,number of layers, trying CNN/RNN, ...)

Imporve fitting test set on cost function :
- Using bigger dev set


