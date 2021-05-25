# Getting and Cleaning Data : Peer Graded Assignment

This repository is my submission to the PGA of this course, it
contains instructions on how to run data analysis on Human 
Activity Recognition Using Smartphones Data Set.

# Dataset used and its Description
### [Human Activity Recognition Using Smartphones Data Set](https://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones)

# Descriptions of Files in this repository
### run_analysis.R 
This file basically contains the steps to achieve the final tidy data set file. It contains of code which does the following steps: 

1. Merges the training and the test sets to create one data set.
2. Extracts only the measurements on the mean and standard deviation for each measurement. 
3. Uses descriptive activity names to name the activities in the data set
4. Appropriately labels the data set with descriptive variable names. 
5. From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject.
 
### final_tidy_data.txt
This contains the final exported data set which was obtained after following all the above steps.

### CodeBook.md
This is a code book which contains the variables names and changes and the description of steps that were performed in run_analysis.R
