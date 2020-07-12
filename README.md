# Getting-and-Cleaning-Data-Course-Project
##run_analysis.R <- Getting and Cleaning Data Course Project
        library(dplyr)

## Features and activity names
        actlabels <- read.table("C:/Users/mpastur/Desktop/test/UCI HAR Dataset/activity_labels.txt")
        features <- read.table("C:/Users/mpastur/Desktop/test/UCI HAR Dataset/features.txt")

## Test files
        xtest <- read.table("C:/Users/mpastur/Desktop/test/UCI HAR Dataset/test/X_test.txt")
        ytest <- read.table("C:/Users/mpastur/Desktop/test/UCI HAR Dataset/test/y_test.txt")
        stest <- read.table("C:/Users/mpastur/Desktop/test/UCI HAR Dataset/test/subject_test.txt")
        test <- bind_cols(ytest,stest,xtest)

##Train files
        xtrain <- read.table("C:/Users/mpastur/Desktop/test/UCI HAR Dataset/train/X_train.txt")
        ytrain <- read.table("C:/Users/mpastur/Desktop/test/UCI HAR Dataset/train/y_train.txt")
        strain <- read.table("C:/Users/mpastur/Desktop/test/UCI HAR Dataset/train/subject_train.txt")
        train <- bind_cols(ytrain,strain, xtrain)

##merge files
        merged <- bind_rows(test,train)

##activity name col
        actname <- merge(actlabels,merged, by.x = "V1", by.y="V1...1")
        mergedg <- select(actname, -V1)

##col names
        colnames(mergedg) <- c("activity", "subject" ,features[1:561,2])

##select mean and std 
        e4 <- dplyr::select(mergedg,contains(c("activity","subject","mean","std")))

##Average of each variable for each activity and subject
        colnames(merged) <- c("activity", "subject" ,features[1:561,2])
        meansd <- dplyr::select(merged,contains(c("activity","subject","mean","std")))
        e5 <- lapply(split(meansd,list(meansd$activity,meansd$subject)),colMeans)
