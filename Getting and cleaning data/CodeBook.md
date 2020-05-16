Codebook
This codebook describes the variables of the dataset "onlyaverageperactivitypersubject". It will also give a short description of the input files and the transformations being done on these input files. For more indepth detail about the transformations please check the Readme or view the run_analysis.R file.

About the dataset used as input
The input files for this dataset is the Human Activity Recognition Using Smartphones Dataset, version 1.0. The input dataset is based on experiments which have been carried out with a group of 30 volunteers within an age bracket of 19-48 years. Each person performed six activities:

WALKING
WALKING_UPSTAIRS
WALKING_DOWNSTAIRS
SITTING
STANDING
LAYING wearing a smartphone (Samsung Galaxy S II) on the waist. Using its embedded accelerometer and gyroscope, they captured 3-axial linear acceleration and 3-axial angular velocity at a constant rate of 50Hz. The experiments have been video-recorded to label the data manually. The obtained dataset has been randomly partitioned into two sets, where 70% of the volunteers was selected for generating the training data and 30% the test data. If you want to use this dataset in a publication, see the license which article should be referenced. The license is at the bottom of the Readme.
About the output dataset
The output dataset is a tidy dataset which contains only calculated Mean and Standard devation values of the measured variables grouped by an activitiy per subject (participant). This output dataset can be used for later analysis.

Background on the input Variables
The features selected for this database come from the accelerometer and gyroscope 3-axial raw signals tAcc-XYZ and tGyro-XYZ. These time domain signals (prefix 't' to denote time) were captured at a constant rate of 50 Hz. Then they were filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise. Similarly, the acceleration signal was then separated into body and gravity acceleration signals (tBodyAcc-XYZ and tGravityAcc-XYZ) using another low pass Butterworth filter with a corner frequency of 0.3 Hz.

Subsequently, the body linear acceleration and angular velocity were derived in time to obtain Jerk signals (tBodyAccJerk-XYZ and tBodyGyroJerk-XYZ). Also the magnitude of these three-dimensional signals were calculated using the Euclidean norm (tBodyAccMag, tGravityAccMag, tBodyAccJerkMag, tBodyGyroMag, tBodyGyroJerkMag).

Finally a Fast Fourier Transform (FFT) was applied to some of these signals producing fBodyAcc-XYZ, fBodyAccJerk-XYZ, fBodyGyro-XYZ, fBodyAccJerkMag, fBodyGyroMag, fBodyGyroJerkMag. (Note the 'f' to indicate frequency domain signals).

These signals were used to estimate variables of the feature vector for each pattern:
'-XYZ' is used to denote 3-axial signals in the X, Y and Z directions.

Dataset variables explained
This dataset will only give the average of both the mean and standard deviation values. For the complete set or other values please use the input dataset.

The average of the mean values are those variables which have ..mean() at the end The average of the standard deviation values are those variables which have ..std() at the end

In the brackets you can have X, Y or Z. This is used to denote the 3-axial signals in the X, Y or Z direction.

The first letter can be either t which give you the values based on time domain signals or f which gives you the values based on frequency domain signals

t = time domain signals f = frequency domain signals

BodyAcc = Body Acceleration GravityAcc = Gravity Acceleration

Jerk = linear acceleration and angular velocity were derived in time to obtain Jerk signals Mag = Magnitude of these three-dimensional signals were calculated using the Euclidean norm Gyro = Gyro

Variables
Index	Variable names	Variable Description
"1"	"Activity"	"Walking, Walking Upstairs, Walking Downstairs, Sitting, Standing, Laying"
"2"	"Subject"	"All the subjects have been given a number so 1 to 30"
"3"	"tBodyAcc-mean()-X"	"The average of the mean of the time domain signals of the Body Linear Acceleration in the X direction"
"4"	"tBodyAcc-mean()-Y"	"The average of the mean of the time domain signals of the Body Linear Acceleration in the Y direction"
"5"	"tBodyAcc-mean()-Z"	"The average of the mean of the time domain signals of the Body Linear Acceleration in the Z direction"
"6"	"tBodyAcc-std()-X"	"The average of the standard deviation of the time domain signals of the Body Linear Acceleration in the X direction"
"7"	"tBodyAcc-std()-Y"	"The average of the standard deviation of the time domain signals of the Body Linear Acceleration in the Y direction"
"8"	"tBodyAcc-std()-Z"	"The average of the standard deviation of the time domain signals of the Body Linear Acceleration in the Z direction"
"9"	tGravityAcc-mean()-X	See above how to understand this variable
"10"	tGravityAcc-mean()-Y	See above how to understand this variable
"11"	tGravityAcc-mean()-Z	See above how to understand this variable
"12"	tGravityAcc-std()-X	See above how to understand this variable
"13"	tGravityAcc-std()-Y	See above how to understand this variable
"14"	tGravityAcc-std()-Z	See above how to understand this variable
"15"	tBodyAccJerk-mean()-X	See above how to understand this variable
"16"	tBodyAccJerk-mean()-Y	See above how to understand this variable
"17"	tBodyAccJerk-mean()-Z	See above how to understand this variable
"18"	tBodyAccJerk-std()-X	See above how to understand this variable
"19"	tBodyAccJerk-std()-Y	See above how to understand this variable
"20"	tBodyAccJerk-std()-Z	See above how to understand this variable
"21"	tBodyGyro-mean()-X	See above how to understand this variable
"22"	tBodyGyro-mean()-Y	See above how to understand this variable
"23"	tBodyGyro-mean()-Z	See above how to understand this variable
"24"	tBodyGyro-std()-X	See above how to understand this variable
"25"	tBodyGyro-std()-Y	See above how to understand this variable
"26"	tBodyGyro-std()-Z	See above how to understand this variable
"27"	tBodyGyroJerk-mean()-X	See above how to understand this variable
"28"	tBodyGyroJerk-mean()-Y	See above how to understand this variable
"29"	tBodyGyroJerk-mean()-Z	See above how to understand this variable
"30"	tBodyGyroJerk-std()-X	See above how to understand this variable
"31"	tBodyGyroJerk-std()-Y	See above how to understand this variable
"32"	tBodyGyroJerk-std()-Z	See above how to understand this variable
"33"	tBodyAccMag-mean()	See above how to understand this variable
"34"	tBodyAccMag-std()	See above how to understand this variable
"35"	tGravityAccMag-mean()	See above how to understand this variable
"36"	tGravityAccMag-std()	See above how to understand this variable
"37"	tBodyAccJerkMag-mean()	See above how to understand this variable
"38"	tBodyAccJerkMag-std()	See above how to understand this variable
"39"	tBodyGyroMag-mean()	See above how to understand this variable
"40"	tBodyGyroMag-std()	See above how to understand this variable
"41"	tBodyGyroJerkMag-mean()	See above how to understand this variable
"42"	tBodyGyroJerkMag-std()	See above how to understand this variable
"43"	fBodyAcc-mean()-X	See above how to understand this variable
"44"	fBodyAcc-mean()-Y	See above how to understand this variable
"45"	fBodyAcc-mean()-Z	See above how to understand this variable
"46"	fBodyAcc-std()-X	See above how to understand this variable
"47"	fBodyAcc-std()-Y	See above how to understand this variable
"48"	fBodyAcc-std()-Z	See above how to understand this variable
"49"	fBodyAccJerk-mean()-X	See above how to understand this variable
"50"	fBodyAccJerk-mean()-Y	See above how to understand this variable
"51"	fBodyAccJerk-mean()-Z	See above how to understand this variable
"52"	fBodyAccJerk-std()-X	See above how to understand this variable
"53"	fBodyAccJerk-std()-Y	See above how to understand this variable
"54"	fBodyAccJerk-std()-Z	See above how to understand this variable
"55"	fBodyGyro-mean()-X	See above how to understand this variable
"56"	fBodyGyro-mean()-Y	See above how to understand this variable
"57"	fBodyGyro-mean()-Z	See above how to understand this variable
"58"	fBodyGyro-std()-X	See above how to understand this variable
"59"	fBodyGyro-std()-Y	See above how to understand this variable
"60"	fBodyGyro-std()-Z	See above how to understand this variable
"61"	fBodyAccMag-mean()	See above how to understand this variable
"62"	fBodyAccMag-std()	See above how to understand this variable
"63"	fBodyBodyAccJerkMag-mean()	See above how to understand this variable
"64"	fBodyBodyAccJerkMag-std()	See above how to understand this variable
"65"	fBodyBodyGyroMag-mean()	See above how to understand this variable
"66"	fBodyBodyGyroMag-std()	See above how to understand this variable
"67"	fBodyBodyGyroJerkMag-mean()	See above how to understand this variable
"68"	fBodyBodyGyroJerkMag-std()	See above how to understand this variable
"69"	angle(tBodyAccMean,gravity)	See above how to understand this variable
"70"	angle(tBodyAccJerkMean),gravityMean)	See above how to understand this variable
"71"	angle(tBodyGyroMean,gravityMean)	See above how to understand this variable
"72"	angle(tBodyGyroJerkMean,gravityMean)	See above how to understand this variable
"73"	angle(X,gravityMean)	See above how to understand this variable
"74"	angle(Y,gravityMean)	See above how to understand this variable
"75"	angle(Z,gravityMean)	See above how to understand this variable
