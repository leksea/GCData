# Getting and Cleaning Data Course Project Repository

Contents of GCData repository:
* README.md -- readme file.
* CodeBook.md -- description of datafields in `tidyDataset.txt`.
* run_analysis.R -- the R scrip that generates `tidyDataset.txt`.

Step-by-step description of data manupulations performed by `run_analysis.R`:

1. Script downloads (if it was not loaded before) the original dataset (https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip), saves it in *working directory/UCI HAR Dataset*.
2. Script loads the activity labels *'UCI HAR Dataset/activity_labels.txt'* and feature info *'UCI HAR Dataset/features.txt'*.
3. Script loads training *'UCI HAR Dataset/train/*.txt'* and test *'UCI HAR Dataset/test/*.txt'* datasets, keeping data columns that contain mean or standard deviation, creates two datasets: `train`, `test`.
4. Script loads the `activity` and `subject` data for each dataset (`train`, `test`), combines columns for each dataset.
5. Script merges the `train` and `test` datasets, adds labels.
6. Script converts the `activity` and `subject` columns into factors.
7. Script creates tidy dataset `allData` that consists of the average (mean) value of each variable for each (`subject`, `activity`) pair.
8. Script saves `allData.mean` as `tidyDataset.txt` file in working directory.
