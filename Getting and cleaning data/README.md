GettingandCleaningData
This Readme file will explain the steps which are being performed if you run the run_analysis script.

Some background information
The input files of this script is the Human Activity Recognition Using Smartphones Dataset, version 1.0. The input dataset is based on experiments which have been carried out with a group of 30 volunteers within an age bracket of 19-48 years. Each person performed six activities (WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING) wearing a smartphone (Samsung Galaxy S II) on the waist. Using its embedded accelerometer and gyroscope, we captured 3-axial linear acceleration and 3-axial angular velocity at a constant rate of 50Hz. The experiments have been video-recorded to label the data manually. The obtained dataset has been randomly partitioned into two sets, where 70% of the volunteers was selected for generating the training data and 30% the test data. If you want to use this dataset in a publication, see the license which article should be referenced. The license is in the extracted files.

Output after running the run_analysis script
The output dataset is a tidy dataset which contains the calculated Mean and Standard devation values of the measured variables by the activities and volunteers. That's why the tidy dataset is a wide dataset. This output dataset can be used for later analysis.

Explanation of the script
The run_analysis script first step is to download and unzip the data.

url = "https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip"  

download.file(url, "FUCIHARDataset.zip") 

unzip("FUCIHARDataset.zip", exdir = "HARdata")  
Next step is importing the following text files into R.

subject_train
subject_test
y_test
X_test
y_train
X_train
features
activity_labels
Joining the test and train data is the next step.These files can be recognised by the _test or _train addition. To join these two datasets, the rbind function is used.

subject_total <-  rbind(subject_train, subject_test) ## All subjects using rbind
X_total <- rbind(X_train, X_test) ## All x measurements using rbind
Y_total <- rbind(y_train, y_test) ## All y measurements, using rbind
Next step for the script is providing the variables in the X and Y datasets with descriptive names.

For the X_total dataset the descriptive variable names can be found in the features file. To use the description in the features file as columnheader, the following script is executed.

colnames(X_total) <- features$V2
For the Y measurements the desciptive variable names can be found in the activity_labels file. The script ties them together.

For the tidy dataset we are only interested in the measurements on the mean and standard deviation for each measurement.

These measumrents are described in the features file so the script takes all measurements which have mean(), std() or Mean.

For example, the code below gets all the features which contain mean()

featuresmean <- grep("mean()", features$V2, fixed = TRUE) 
This gives you 33 variables containing the word mean(). Also for std() we get 33 variables.

The script also includeds the features which contain Mean because these are also mean values and so should be part of the new dataset. This will add 7 more variables starting with angle like angle(X,gravityMean) and containing the word Mean.

The total the number of variables is (33 + 33 + 7 = 73 variables (not yet included are the activity and subject)

The Inertial Signals data doesn't contain any mean or standard deviation data so this data is not included in the tidy dataset.

All the needed features (these 73 variables) are put in the Vector called Allneededfeatures.

The following script creates a dataset with only the needed variables. See the code below

X_total_needed <- X_total[, Allneededfeatures]
At this point the other two important variables which are subject aare added to the dataset.

First thing the script adds the activities as a column to the dataset. The code below adds the column activities to the dataset

Newdataset1 <- mutate(X_total_needed, activities = Y_total_df)
In the same way the script adds the subjects as a column to the dataset.

Now we can group this last dataset by activity and subject and get the average of each variable for each activity and each subject.
That is done by the code below

Newdataset5 <-
  Newdataset3 %>%
     group_by(activities, subject)%>%
       summarise_all(.,funs(mean(., na.rm = TRUE)))  
Last step is write this newly created dataset to a file.

write.table(Newdataset5, "onlyaverageperactivitypersubject.txt", row.names = FALSE)
This final dataset contains 180 rows (not counting the header) -> 6 activities for the 30 participants and consist of 75 variables -> (33 mean + 33 std + 7 Mean + 1 for activity and 1 for Subjects). So it fulfills the tidy dataset criteria:

Each variable forms a column. (Check)
Each observation forms a row. (Check)
Each type of observational unit forms a table. (Check)
(See Tidy Data by Hadley Wickham in Journal of Statistical Software)
Last step of the script is removing all the data and objects from your environment. What remains on your computer are the input files and the output file.

To run the run_analysis.R script, load this script into R or RStudio, select everything and click on run. The script will perform all the steps described above.
