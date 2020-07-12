---
title: "Codebook"
author: "Mateopr"
date: "7/12/2020"
output: html_document
---
This is the codebook of the course project that describes the variables, data and
the transformations done.

## Aim of the project

The data represens the data collected from the accelerometers from the Samsung Galaxy S smartphone.

The data was gather from 30 "subjects" doing 6 "activities" such as walking, laying...

The data collected is from the accelerometer and gyroscope of the phones


## Variables

        Activity: describes the activity that the subject was doing:
                1 WALKING
                2 WALKING_UPSTAIRS
                3 WALKING_DOWNSTAIRS
                4 SITTING
                5 STANDING
                6 LAYING
        
        Subject: the subjects are code from 1-30
        
        Features: The features are collected for different direction X,Y,Z and the files shows the mean and standar deviation (sd) of each one
                tBodyAcc-XYZ
                tGravityAcc-XYZ
                tBodyAccJerk-XYZ
                tBodyGyro-XYZ
                tBodyGyroJerk-XYZ
                tBodyAccMag
                tGravityAccMag
                tBodyAccJerkMag
                tBodyGyroMag
                tBodyGyroJerkMag
                fBodyAcc-XYZ
                fBodyAccJerk-XYZ
                fBodyGyro-XYZ
                fBodyAccMag
                fBodyAccJerkMag
                fBodyGyroMag
                fBodyGyroJerkMag

## Output

The output shows the average of each variable for each activity and subject.
So the output 6.30 shows the result of the subject#30 while "LAYING"

