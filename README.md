# Behavior-of-Linear-Model-Machine-Learning-Study
### Experimenting on a linear model to study behavior on  different data set

# 1. Experiment 1 : Imbalanced Dataset 



 1.1.1  As a part of this experiment we will observe how linear models work in case of data imbalanced, we will observe how hyper plane is changes according to change in  learning rate for both svm and logistic regression.
    
1.1.2    we have created 4 random datasets which are linearly separable and having class imbalance

1.1.3 In the  dataset the ratio between positive and negative is 100 : 2, 100 : 20, 100 : 40, 100 : 80.




## 1.1 Linear SVM Observation


![SVM : 100:2, 100:20 ](https://i.imgur.com/nLJYwdF.png)

![SVM : 100:40, 100:80 ](https://i.imgur.com/KZngsMS.png)

1.1.1
<pre>

For C = 0.001
for Dataset 1 (100:2) model is under-fitted
for Dataset 2 (100:20) model is under-fitted than dataset 1
for Dataset 3 (100:40) model is more under-fitted than dataset 2
for Dataset 4 (100:80) model is by far most under-fitted
</pre>

1.1.2
<pre>
For C = 1
for Dataset 1 (100:2) model is under-fitted
for Dataset 2 (100:20) model is under-fitted than dataset 1
for Dataset 3 (100:40) model is more under-fitted than dataset 2
for Dataset 4 (100:80) model is highly under-fitted
</pre>
1.1.3
<pre>
For C = 100
for Dataset 1 (100:2) model is slightly under-fitted, but better than previous c =0.01 and c=1
for Dataset 2 (100:20) model is fitted well
for Dataset 3 (100:40) model is very slightly over-fitted
for Dataset 4 (100:80) model is fitted well
</pre>

## 1.2 Logistic Regression


![Logistic : 100:2, 100:20 ](https://i.imgur.com/m0neOTh.png)

![Logistic : 100:40, 100:80 ](https://i.imgur.com/vCv4TyV.png)

1.2.1

<pre>

for C = 0.001
All the dataset we could not able to find decision boundry it is highlt underfited
</pre>

1.2.2
<pre>

for C = 1
for Dataset 1 (100:2) and Dataset 2 (100:20) model is highly under-fitted, most probable reason is class imbalance
for Dataset 3 (100:40) model is slightly under-fitted¶
for Dataset 4 (100:80) model is fitted well
</pre>
1.2.3
<pre>

for C = 100
for Dataset 1 (100:2) model is slightly under-fitted, most probable reason is class imbalance, this model is better than model for C =0.001 and C = 1
for Dataset 2 (100:20) model is over-fitted
for Dataset 3 (100:40) model is overt-fitted but less than dataset 2
for Dataset 4 (100:80) model is fitted well
</pre>


# 2. Experiment 2 : Linear Model effect on High Variance Data.

*  In this experiment we will observe how linear models work in case of data having feautres with different variance

## 2.1 Experiment 2 <br/>
<pre>
*  We will apply Logistic regression(SGDClassifier with logloss) on 'data' and check the feature importance 
*  we will apply SVM(SGDClassifier with hinge) on 'data' and check the feature importance
</pre>
### 2.1.1 Experiment 1 Result 
<pre background-color="orange">
    *   Logistic regression fits quiet well and accuracy is also good
    *   SVM linear failed to converge with more than 100000 iteration with hinge loss <br/>
 Highly variance nature of data is affecting the classifier behavior
</pre>
## 2.2 Experiment 2 <br/>
<pre>
*  we will apply Logistic regression( SGDClassifier with log-loss ) on 'data' after standardization
*  we will apply SVM(SGDClassifier with hinge loss) on 'data' after standardization
</pre>
### 2.2.1 Experiment 2 Result
<pre>
    *    Logistic regression fits quiet well and accuracy is also good with standardized feature
    *    SVM linear  converge with in  500 max iteration with hinge loss <br/>
    *    After Standardization SVM Linear converged super fast and accuracy is also increased to 0.92

</pre>


# 3. Experiment 3 : Linear Model performance on presence of outliers
*   As a part of this experiment we will be working the regression problem and how regularization helps to get rid of outliers, and we will see how the hyperplane is changing in presence of outliers.


    for each regularizer: 
        for each outlier:
            add the outlier to the data
            fit the linear regression to the updated data
            get the hyper plane
            plot the hyperplane along with the data points



![Linear Regression : alpha : 0.0001 ](https://i.imgur.com/O0Jzbds.png)


![Linear Regression : alpha : 1 ](https://i.imgur.com/FoGiMRv.png)


![Linear Regression : alpha : 100 ](https://i.imgur.com/LuHVjI2.png)



## Observation
* As we increase Alpha value hyper plane is not moving significantly, 
increasing alpha value has little impace on position of hyper plane.

