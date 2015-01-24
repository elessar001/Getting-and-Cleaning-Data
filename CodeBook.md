## Description

This file describes the transformations that were performed to clean up the merge, clean, and create a new data set with the required attributes from the original data.

## Source Data

A full description of the data used in this project can be found at The UCI Machine Learning Repository:

http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones 

The data was downloaded from the source fiven below:

https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip 

The data was manually downloaded into the working directory.

## Raw Data Set Information

The experiments were carried out with a group of 30 volunteers within an age bracket of 19-48 years. Each person performed six activities (walking, walking upstairs, walking downstairs, sitting, standing, and laying) wearing a smartphone (Samsung Galaxy S II) on the waist. Using its embedded accelerometer and gyroscope, 3-axial linear acceleration and 3-axial angular velocity were captured at a constant rate of 50Hz. The experiments have been video-recorded to label the data manually. The obtained dataset was been randomly partitioned into two sets, where 70% of the volunteers were selected for generating the training data and 30% for the test data.

The sensor signals (accelerometer and gyroscope) were pre-processed by applying noise filters and then sampled in fixed-width sliding windows of 2.56 sec and 50% overlap (128 readings/window). The sensor acceleration signal, which has gravitational and body motion components, was separated using a Butterworth low-pass filter into body acceleration and gravity. The gravitational force is assumed to have only low frequency components, therefore a filter with 0.3 Hz cutoff frequency was used. From each window, a vector of features was obtained by calculating variables from the time and frequency domain.

For each record in the dataset the following variables are provided:

+ Triaxial acceleration from the accelerometer (total acceleration) and the estimated body acceleration.
+ Triaxial Angular velocity from the gyroscope.
+ A 561-feature vector with time and frequency domain variables.
+ Its activity label.
+ An identifier of the subject who carried out the experiment.

## Data Transformations

### Merging Test and Training Data Sets

First column names and activity labels were applied to training and test data respectively. Then the training and test data were merged to form a new data set

### Extracting only the measurements on the mean and standard deviation for each measurement.

A logical vector was created that contained TRUE values for columns with ID, and columns with "Mean" and "StdDev" in column labels. The logical vector was used to subset the merged data set to retain the required columns.

### Using descriptive activity names to name the activities in the data set

The activity type was combined with the merged data subset to use decriptive activity names for the variables in the data set.

### Appropriately label the data set with descriptive activity names.

Using gsub function for pattern replacement to clean up the data labels.

### Create a second, independent tidy data set with the average of each variable for each activity and each subject.

Per the project instructions, we need to produce only a data set with the average of each veriable for each activity and subject
