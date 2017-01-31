
##Identifiers
    - subject - The ID of the test subject
    - activity - The type of activity performed when the corresponding measurements were taken

##Data transformation

The raw data sets are processed with run_analisys.R script to create a tidy data set.
Merge training and test sets

- Test and training data (X_train.txt, X_test.txt), subject ids (subject_train.txt, subject_test.txt) and activity ids (y_train.txt, y_test.txt) are merged to obtain a single data set. Variables are labelled with the names assigned by original collectors (features.txt).
Extract mean and standard deviation variables

- From the merged data set is extracted and intermediate data set with only the values of estimated mean (variables with labels that contain "mean") and standard deviation (variables with labels that contain "std").
Use descriptive activity names

- A new column is added to intermediate data set with the activity description. Activity id column is used to look up descriptions in activity_labels.txt.
Label variables appropriately

- Labels given from the original collectors were changed: to obtain valid R names without parentheses, dashes and commas to obtain more descriptive labels
Create a tidy data set

- From the intermediate data set is created a final tidy data set where numeric variables are averaged for each activity and each subject.

- The tidy data set contains 10299 observations with 81 variables divided in:

    -- an activity label (Activity): WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING
    -- an identifier of the subject who carried out the experiment (Subject): 1, 3, 5, 6, 7, 8, 11, 14, 15, 16, 17, 19, 21, 22, 23, 25, 26, 27, 28, 29, 30
    -- a 79-feature vector with time and frequency domain signal variables (numeric)


For variables derived from mean and standard deviation estimation, the previous labels are augmented with the terms "Mean" or "StandardDeviation".

The data set is written to the file project_output.txt.

##Activity Labels

   -- WALKING (value 1): subject was walking during the test
   -- WALKING_UPSTAIRS (value 2): subject was walking up a staircase during the test
   -- WALKING_DOWNSTAIRS (value 3): subject was walking down a staircase during the test
   -- SITTING (value 4): subject was sitting during the test
   -- STANDING (value 5): subject was standing during the test
   -- LAYING (value 6): subject was laying down during the test

