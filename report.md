#MLG 
##LAB 01: Introduction to jupyter notebooks

####By Ali Miladi & Dany Tchente

##Q1. Regarding the wine database, by looking at the boxplots generated during the Exploratory analysis of data (section 6) , which features seems the most discriminative ?why ?

![MacDown Screenshot](/Users/mac/Desktop/semestre_2/MLG/lab01/Screen\ Shot\ 2018-03-03\ at\ 18.59.47.png)

The features is "flavanoids" because the inter-quartile of each class don't overlap. 

##Q2. Can you estimate the performance of a single-rule classification method like the one presented in section 7 ? 

Class 1 = 59 - 6(fn_2) = 53 (tp)

Class 2 = 71 - 14(fn_3) - 17(fn_1) = 40 (tp)

Class 3 = 48 - 1 (fn_2) = 47 (tp)

***performance class 1*** = 53 / 59 = 0.9 = 90%

***performance class 2*** = 40 / 71 = 0.56 = 56%

***performance class 3*** = 47 / 48 = 0.98 = 98%

##Q3. Define a rule that uses the most discriminative feature to classify the wine observations.

```
pred = []

for row in df['flavanoids']:
    if row > 2.5:
        pred.append(1);
    elif row > 1.5 and row < 2.5 :
        pred.append(2);    
    else:
        pred.append(3)

# A new column is added to the dataframe
df['prediction'] = pred
```

##Q4. Compute the confusion matrix of the resulting rule-based system defined in Q3.

![MacDown Screenshot](/Users/mac/Desktop/semestre_2/MLG/lab01/Screen\ Shot\ 2018-03-03\ at\ 19.02.47.png)

##Q5. Compute the precision, the recall and the F1-score of the classification system defined in Q3 for only one class using the values of the confusion matrix ?

![MacDown Screenshot](/Users/mac/Desktop/semestre_2/MLG/lab01/Screen\ Shot\ 2018-03-03\ at\ 19.02.54.png)

We decided to choose the first class : 

***precision*** = tp/(tp + fp) = 53/(53 + 17) = 0.76 

***recall*** = tp/(tp + fn) = 53/(53 + 6) = 0.90

***f1-score*** = 2 x precision x recall / ( precision + recall) = 2 x 0.76 x 0.90/ (0.76 + 0.90) = 0.82  

