Introduction
-------------------------------
The script run_analysis.R walks through step by step the 5 steps necessary to complete the course project. I walk through these below:

1) Data is merged using the *rbind()* function. This is done by matching data field names, lengths and measures. 
2) Next, fields are restricted to those with similar mean and standard deviation measures. After extracting these columns, they are given the correct names as indicated by features.txt.
3) The activity names and IDs from *activity_labels.txt* are added.
4) Incorrect or unclear field names are addressed. 
5) Generate a new dataset with all the average measures for each subject and activity type (30 subjects * 6 activities = 180 rows). The output file is called *averages_data.txt*, and uploaded to this repository.

The final cleaned dataset contains the following variables
-----------------------------------------------------------
1) **x_train**, **y_train**, **x_test**, **y_test**, **subject_train** and **subject_test** contain the raw downloaded data.
2) **x_data**, **y_data** and **subject_data** combine the previous datasets for additional analysis.
3) *Features* contains the correct names for the **x_data** dataset, which are applied to the column names stored in mean_and_std_features, a numeric vector used to extract the desired data.
4) all_data combined x_data, y_data and subject_data in one dataset.
5) averages_data contains the relevant averages which will be later stored in a .txt file. *ddply()* from the plyr package is used to apply *colMeans()*.