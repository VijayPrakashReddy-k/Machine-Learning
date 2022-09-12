### Problem 1: Types of Attributes (14 points)

***Classify the following attributes as nominal, ordinal, interval, ratio.***

*(a) Rating of an Amazon product by a person on a scale of 1 to 5*

***`Ordinal Scale Data`*** - It's used to represent non-mathematical ideas such as frequency, satisfaction,happiness, a degree of pain, etc.

*(b) The Internet Speed*

***`Ratio Scale Data`*** - It can’t go Negative and there’s a Starting or Zero point and it's a measurement scale that not only produces the order of the variables, but also makes the difference between the known variables along with information about the value of the true zero.

*(c) Number of customers in a store*

***`Ratio Scale Data`*** - It can’t go Negative and there’s a Starting or Zero point and it's a measurement scale that not only produces the order of the variables, but also makes the difference between the known variables along with information about the value of the true zero.

*(d) UCF Student ID*

***`Nominal Scale Data`*** : It’s a Named Variable and used to label variables in different classifications and does not imply a 	quantitative value or order.

*(e) Distance*

***`Ratio Scale Data`*** - It can’t go Negative and there’s a Starting or Zero point and it's a measurement scale that not only produces the order of the variables, but also makes the difference between the known variables along with information about the value of the true zero.

*(f) Letter grade (A, B, C, D)*

***`Ordinal Scale Data`*** - It's used to represent non-mathematical ideas such as frequency, satisfaction,happiness, a degree of pain, etc.

*(g) The temperature at Orlando*

***`Interval Scale Data`*** — It’s a qualitative measure and it may go to Negative and there is no starting or Zero point.


### Problem 2: Exploring Data Preprocessing Techniques (26 points) 
 
***Read the solution post of the Kaggle Titanic Dataset:***

[![Kaggle Notebook](kaggle.png)](https://www.kaggle.com/code/preejababu/titanic-data-science-solutions). 

Run the code and reproduce the data preprocessing and classification modeling steps.  
 
`Q1 (Reproduce): Please read, understand, run the code and reproduce the model accuracies. Please briefly explain whether you can reproduce the classification accuracies of  'Support Vector Machines', 'KNN', 'Logistic Regression',  'Random Forest', 'Naive Bayes', 'Perceptron', 'Stochastic Gradient Decent', 'Linear SVC', 'Decision Tree'. (10 points)`
 
 1. Initially I register to Kaggle and click on copy and edit button to run the given kaggle notebook with kernel.`

 2. I ran all the cells and then able to reproduce the classification accuracies, for all the models with slight changes in the accuracies.`
 

<p align = 'center'>
            <img src = Images/ML_Results_given.png />
</p>

`Q2 (Improve): Is the data preprocessing process proposed in the Kaggle post the best preprocessing solution? If yes, please explain why. If not, can you leverage what you learned in the class and your previous experiences to improve data processing, to obtain better accuracies for all these classification models? Describe what is your improved data preprocessing, and what are your improved accuracies?  (16 points)`

***`Steps followed to Improve the Accuracy`***

**Step 1 - Showed Distributions for Features**

**Step 2 - Data Munging :** Working with missing values

           Replaced the missing values with 'C' for Embarked feature

**Step 3 - Outlier Imputation :** For Age and Fare, and created bins

          Replaced all missing Age with mean value
          Replaced with median age of gender
          Replaced with median age of Pclass
          Replaced with median age of title
          
**Step 4 - Feature Engineering :** For Age, FamilySize and added New Feature Ismother 

**Step 5 - Categorical Feature Encoding** : Created Encoding Values for Categorical Features and then Droped and Reorder Columns.

<p align = 'center'>
            <img src = Images/Model_Output_Results.png />
</p>

### Problem 3: Distance/Similarity Measures (10 points)

Given the four boxes shown in the following figure, answer the following questions.

- In the diagram, numbers indicate the lengths and widths and you can consider each box to be a vector of two real numbers, length and width. For example, the top left box would be (2,1), while the bottom right box would be (3,3).  Restrict your choices of similarity/distance measure to Euclidean distance and correlation.  Please explain your choice.

<p align = 'center'>
            <img src = Images/boxes.png />
</p>

The boxes can be measured by x and y vectors where,

          x= measurement towards horizontal axis and 
          y= measurement towards vertical axis.

          A1 (2,1), A2 (1,1), A3 (6,3), A4 (3,3)
          
#### Euclidean distance:
- `The Euclidean distance is a distance measure between two points or or vectors in a two- or multidimensional (Euclidean) space based on Pythagoras' theorem. The distance is calculated by taking the square root of the sum of the squared pair-wise distances of every dimension.`

<p align = 'center'>
            <img src = Images/distance_euclidean.gif/>
</p>

 #### Pearson correlation:
 - `The Pearson correlation coefficient is probably the most widely used measure for linear relationships between two normal distributed variables and thus often just called "correlation coefficient". Usually, the Pearson coefficient is obtained via a Least-Squares fit and a value of 1 represents a perfect positive relation-ship, -1 a perfect negative relationship, and 0 indicates the absence of a relationship between variables.`
 
<p align = 'center'>
            <img src = Images/pearson_rho.gif/>
</p>

<p align = 'center'>
            <img src = Images/pearson.webp/>
</p>

<p align = 'center'>
            <img src = Images/pearson_rho_2.gif/>
</p>


**1. Which proximity measure would you use to group the boxes based on their shapes (length-width ratio)?**

When we are dealing with shape we should go for Correlation. Here the variation of X and Y should be in direct proportion which means they should be correlated for the same type of shapes.

Hence, it will beThe length and width ratio of the boxes are

     A1=2:1
     
     A2=1:1
     
     A3=6:3 => 2:1
     
     A4=3:3 => 1:1

- `According to the length and width ratio (A1 and A3) and (A2 and A4) can be grouped together.`

**2. Which proximity measure would you use to group the boxes based on their size?**

`To measure the size of the boxes need to represent the boxes as vectors. Hence, we have to calculate Euclidean distance which is`

The distance between Boxes:

B1 & B2: sqrt{(2 − 1)^2 + (1 − 1)^2} = 1

B1 & B3: sqrt{(2 − 6)^2 + (1 − 3)^2} = 4.47

B1 & B4: sqrt{(2 − 3)^2 + (1 − 3)^2} = 2.23

B2 & B3: sqrt{(1 − 6)^2 + (1 − 3)^2} = 5.38

B2 & B4: sqrt{(3 − 1)^2 + (3 − 1)^2} = 2.82

B3 & B4: sqrt{(3 − 6)^2 + (3 − 3)^2} = 3

**We have to go for Euclidean distance when we are dealing with the sizes of the boxes. So the grouping will be**

     B1&B1; B2&B2; B3&B3; B4&B4 (Zero distance between Boxes within itself)

     B1&B2

     B1&B4

     B2&B4

     B3&B4

     B1&B3

     B2&B3
