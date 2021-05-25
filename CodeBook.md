## The following steps were performed in the **run_analysis.R** file in order to obtain the **final_tidy_data.txt** file.

### Downloading and Unzipping Data
The data was downloaded in a ZIP file format and then unzipped to obtain the
UCI HAR Dataset Folder which contains the required data sets.

### Assigning each data file to appropriate table variables
Each of the data files in the train folder and test folder is assigned to 
appropriate tables with names such as x_train,y_test,etc. We also store 
the features and activity labels data files into tables.

### Merging the train and test datasets to one dataset

We basically row bind x_train and x_test to obtain merged_x, y_train and y_test
to obtain the merged_y and subject_train and subject_test to obtain merged_subject.
In the end we finally column bind merged_x,merged_y and merged_subject to obtain
final_data.
The dimensions are as follows

1. merged_x : 10299,561
2. merged_y : 10299,1
3. merged_subject : 10299,1
4. final_data : 10299,563

### Extracting only the measurements on mean and standard deviations for each measurement

We create req_data from final_data by selecting only the code and subject columns
and also use pattern matching to select columns which contain either mean or std.
The dimensions of resulting req_data is 10299,88.

### Using descriptive activity names to name the activities in the data set

We use the activities data set to substitute the activity names in place of activity
codes in the req_data table.

### Appropiately labelling the data sets with descriptive variable names

We make the following changes to the variable names in this step with help of gsub :

1. Change the name of the second column from "code"" to "Activity".
2. "Acc" in column names gets changed to "Accelerometer".
3. "Gyro" in column names gets changed to "Gyroscope".
4. "Mag" in column names gets changed to "Magnitude".
5. All substrings that start with f and t get changed to Frequency and Time respectively.
6. "tBody" in column names is changed to "TimeBody".
7. In some column names "BodyBody" is used, we change it to a single "Body".

### From the above data creating a second, independent tidy data set with the average of each variable for each activity and each subject

Here we use dplyr to first group the data by subject and Activity names and then
use the summarize function to get the mean of all the column variables.
In the end we simply write this tidy data set into to the **final_tidy_data.txt**
file with row.name= FALSE.
