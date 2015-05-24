# DataScienceSpecialization-08-PracticalMachineLearning
CourseProject:Writeup

Background
Using devices such as Jawbone Up, Nike FuelBand, and Fitbit it is now possible to collect a large amount of data about personal activity relatively inexpensively. These type of devices are part of the quantified self movement – a group of enthusiasts who take measurements about themselves regularly to improve their health, to find patterns in their behavior, or because they are tech geeks. One thing that people regularly do is quantify how much of a particular activity they do, but they rarely quantify how well they do it. In this project, your goal will be to use data from accelerometers on the belt, forearm, arm, and dumbell of 6 participants. They were asked to perform barbell lifts correctly and incorrectly in 5 different ways. More information is available from the website here: http://groupware.les.inf.puc-rio.br/har (see the section on the Weight Lifting Exercise Dataset). 

Data 
The training data for this project are available here: 
https://d396qusza40orc.cloudfront.net/predmachlearn/pml-training.csv

The test data are available here: 
https://d396qusza40orc.cloudfront.net/predmachlearn/pml-testing.csv

The data for this project come from this source: http://groupware.les.inf.puc-rio.br/har. If you use the document you create for this class for any purpose please cite them as they have been very generous in allowing their data to be used for this kind of assignment. 

Building Model
The following parameters was selected in order to create prediction model.

roll_dumbbell		pitch_dumbbell	yaw_dumbbell
gyros_dumbbell_x	gyros_dumbbell_y	gyros_dumbbell_z	
accel_dumbbell_x	accel_dumbbell_y	accel_dumbbell_z	
magnet_dumbbell_x	magnet_dumbbell_y	magnet_dumbbell_z	


roll_forearm		pitch_forearm		yaw_forearm
gyros_forearm_x	gyros_forearm_y	gyros_forearm_z	
accel_forearm_x	accel_forearm_y	accel_forearm_z	
magnet_forearm_x	magnet_forearm_y	magnet_forearm_z

roll_arm		pitch_arm		yaw_arm
gyros_arm_x		gyros_arm_y		gyros_arm_z	
accel_arm_x		accel_arm_y		accel_arm_z	
magnet_arm_x	magnet_arm_y	magnet_arm_z

Reason: In my model dumbbell arm and forearm are the most important variables for prediction model

Algorithm: I use random forests for prediction algorithm because it's most accurate even some times it face over fitting problem.

Result: After training and test via cross validation the table result was shown below.
table(pred,testing$classe)
pred  A  B  C  D  E
   A 24  1  0  3  3
   B  0 13  0  2  2
   C  5  3 20  0  3
   D  2  2  1 14  0
   E  1  4  0  1 15
This result is much better than select less variables for example my previous model which using only dumbbell variables
table(pred,testing$classe)
pred  A  B  C  D  E
   A 25  4  3  1  2
   B  0  9  0  4  4
   C  1  2 13  1  4
   D  3  1  4 13  3
   E  3  7  1  1 10
