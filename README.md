# Human Activity Recognition

## Description
These days Smartphones have become an integral part of our life. We cannot assume our life without a mobile phone. Since, the advent of Smartphones, a revolution has been created in the mobile communication industry. Smartphones are not just restricted for calling these days. Infact, they are more often used for entertainment purpose.<br><br>
Smartphone manufacturing companies load Smartphones with various sensors to enhance the user experinece. Two of the such sensors are <b>Accelerometer</b> and <b>Gyroscope</b>. <b>Accelerometer</b> measures acceleration while <b>Gyroscope</b> measures angular velocity.<br><br>
Here, we will try to use the data provided by accelerometer and gyroscope of Smartphone to classify the activity which a Smartphone user is performing.

## Why this is Useful?
These days, in addition to Smartphones, we are also using Smart-Watches like Fitbit or Apple-Watch, which help us to track our health. They monitor our each activity throughout the day check how many calories we have burnt. How many hours have we slept. However, in addition to Accelerometer and Gyroscope, they also use Heart-Rate data to monitor our activity. Since, we only have Smartphone data so just by using  Accelerometer and Gyroscope data we will monitor the activity of a person. This software can then be converted into an App which can be downloaded in Smartphone. Hence, a person who has Smartphone can monitor his/her health using this App

## Quick Overview of Dataset
Accelerometer and Gyroscope readings are taken from 30 volunteers(referred as subjects) while performing the following 6 Activities.<br><br>
<b>These activites are encoded as follows:<br>
WALKING-- 1<br>
WALKING_UPSTAIRS-- 2<br>
WALKING_DOWNSTAIRS-- 3<br>
SITTING-- 4<br>
STANDING-- 5<br>
LYING-- 6<br>
</b>
* Readings are divided into a window of 2.56 seconds with 50% overlapping.
* Accelerometer readings are divided into gravity acceleration and body acceleration readings, which has x, y and z components each.
* Gyroscope readings are the measure of angular velocities which has x, y and z components.
* Jerk signals are calculated for Body-Acceleration readings.
* Fourier Transforms are made on the above time readings to obtain frequency readings.
* Now, on all the base signal readings., mean, max, mad, sma, arcoefficient, energy-bands, entropy etc., are calculated for each window.
* Extra features are calculated by taking the average of signals in a single window sample. These are used on the angle() variable.
* Finally, we got feature vector of 561 features and these features are given in the dataset.
* Each window of readings is a data-point of 561 features.

## Y-Encoded Labels
WALKING-- 0<br>
WALKING_UPSTAIRS-- 1<br>
WALKING_DOWNSTAIRS-- 2<br>
SITTING-- 3<br>
STANDING-- 4<br>
LYING-- 5

## Problem Addresed
Work-flow is as follows:<br>
1. Domain experts from the field of Signal Processing collects the data from Accelerometer and Gyroscope of Smartphone.
2. They break up the data in the time window of 2.56 seconds with 50% overlapping i.e., 128 reading
3. They engineered 561 features from each time window of 2.56 seconds.<br>

<b>By using either human engineered 561 feature data or raw features of 128 reading, our goal is to predict one of the six activities that a Smartphone user is performing at that 2.56 Seconds time window</b>.

## ML Problem Formulation
All of the Accelerometer and Gyroscope are tri-axial, means that they measure acceleration and angular-velocity respectively in all the three axis namely X-axis, Y-axis and Z-axis. So, we have in total six time-series data. Given this six time-series data, we want to predict six activities namely <b>Walking</b> or <b>Walking-Upstairs</b> or <b>Walking-Downstairs</b> or <b>Lying-Down</b> or <b>Standing-Up</b> or <b>Sitting-Down</b>.<br><br>
<b>At the outset, this is a multi-class classification problem.</b>

## Performance Metric
We will use Accuracy as one of the metric.

## Data
All the data is present in 'UCI_HAR_dataset/' folder in present working directory.<br>
Feature names are present in 'UCI_HAR_dataset/features.txt'<br><br>
<b>Train Data</b><br>
'UCI_HAR_dataset/train/X_train.txt'<br>
'UCI_HAR_dataset/train/subject_train.txt'<br>
'UCI_HAR_dataset/train/y_train.txt'<br>
<b>Test Data</b><br>
'UCI_HAR_dataset/test/X_test.txt'<br>
'UCI_HAR_dataset/test/subject_test.txt'<br>
'UCI_HAR_dataset/test/y_test.txt'<br>

## Data-Points Distribution
* 30 test-subjects data is randomly split to 70%(21) train and 30%(7) test data.
* Each data-point corresponds one of the 6 Activities.
## Data Source
https://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones
