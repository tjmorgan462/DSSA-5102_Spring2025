# Data Gathering & Warehousing 
## DSSA-5102 - Spring 2025
_Data Science and Strategic Analytics Graduate Program_ - [Stockton University](https://www.stockton.edu/)

### Languages & Environment:
- Python, SQL, Anaconda Navigator, Jupyter Notebook, Github, Spyder

### Assignments:
- Assignment #1 - Locating a Dataset
    - Importing data and initial dataset exploration (Master dataset not available on repository). 
- Assignment #2 - Cleaning our Dataset
    - Preparing our dataset for our future class database (Master dataset not available on repository).
- Assignment #3 - Metadata
    - Creating a metadata file with all necessary components
- Assignment #4 - Only Murders in the...Database?
    - An introduction to basic SQL commands and queries.
- Assignment #5 - Only Murders in the...Database? Cont.
    - Practice using basic SQL commands and queries.
- Assignment #6 - Creating a Database from scratch in Python
    - Locally, and with MySQL Workbench.
- Assignment #7 - Populating our Database
    - Develop a database schema in MySQL Workbench with our populated database.
- Assignment #8 - JOINs
    - Practice using JOINs on our database to answer questions.
- Assignment #9 - Miscellaneous SQL
- Assignment #10 - Pulling it all Together!



<b>Dataset name: </b> Indicators of Anxiety or Depression Based on Reported Frequency of Symptoms <br>
<b>Company/Government Organization: </b> National Center for Health Statistics <br>
<b>Download link: </b> https://data.cdc.gov/NCHS/Indicators-of-Anxiety-or-Depression-Based-on-Repor/8pt5-q6wp/about_data <br>
<b>Date of Access: </b> 2/13/25

-  Data Source: ​ The data is from the National Center for Health Statistics and published by the Centers for Disease Control and Prevention. The data was first collected 4/23/20 and last updated 9/16/24, as of the date of access 2/13/25. The data is a csv file. <br><br> National Center for Health Statistics. <i>Indicators of Anxiety or Depression Based on Reported Frequency of Symptoms During Last 7 Days.</i> Data accessed 2/13/25. Available from: https://data.cdc.gov/d/8pt5-q6wp.

-  Collection Method: ​ The data was collected using an online questionnaire sent by both email and text message. The questions included: <br><br>"Over the last 7 days, how often have you been bothered by … having little interest or pleasure in doing things? Would you say not at all, several days, more than half the days, or nearly every day? Select only one answer." <br>"Over the last 7 days, how often have you been bothered by … feeling down, depressed, or hopeless? Would you say not at all, several days, more than half the days, or nearly every day? Select only one answer." <br>"Over the last 7 days, how often have you been bothered by the following problems … Feeling nervous, anxious, or on edge? Would you say not at all, several days, more than half the days, or nearly every day? Select only one answer." <br>"Over the last 7 days, how often have you been bothered by the following problems … Not being able to stop or control worrying? Would you say not at all, several days, more than half the days, or nearly every day? Select only one answer."<br><br>The answers to the provided questions are then assigned a numerical value: "not at all" = 0, "several days" = 1, "more than half the days" = 2, and "nearly every day" = 3. The two responses for each disorder are added together. For scores of 3 or greater, further evaluation by a health professional is recommended, as these scores have been shown to be associated with diagnoses of the respective disorders.

-  Extraction Method: ​ The data was exported from https://data.cdc.gov/NCHS/Indicators-of-Anxiety-or-Depression-Based-on-Repor/8pt5-q6wp/about_data as a .csv file.

-  Data Cleaning and Manipulation: ​ After downloading the data, the .csv file was read into a JupyterLab notebook and cleaned using python. The column names were changed to lowercase with no spaces or special characters to use SQL in the future. NA values were then found and determined to not be an issue for future use of the dataset because of the nature of the missing value's locations. Errors in the categorical data were then searched for by using the unique function, and none were found. The 'time_period_start' and 'time_period_end' columns were also converted into datetime format.

-  Data Units: ​ The 'value', 'low_ci', and 'high_ci' columns are all percentages, the rest have no units.

-  Data Formulas: ​ For the 'confidence_interval' column, it was defined as "low_ci[i] - high_ci[i]".

-  Data Validation: ​ All of the categorical data was checked using the unique function to make sure everything was case-sensitive to ensure consistency in the entries.

-  Data Columns: ​

    -  indicator: object, states whether the row is about symptoms of depression, anxiety, or both
    -  group: object, the demographic
    -  state: object, the location in the United States
    -  subgroup: object, a more specific definition of the demographic
    -  phase: object, the phase number of the study
    -  time_period: int64, the number of the study, i.e. the first study would be given a value of 1
    -  time_period_label: object, the start and end dates given as an interval of time
    -  time_period_start: datetime64[ns], the day a study starts
    -  time_period_end: datetime64[ns], the day a study ends
    -  value: float64, the percentage of people that gave an answer of at least 1 to the questionnaire
    -  low_ci: float64, the low point of the confidence interval
    -  high_ci: float64, the high point of the confidence interval
    -  confidence_interval: object, the mean of the 'value' plus and minus the variation in the 'value'
    -  quartile_range: object, the difference between the 75th and 25th percentiles <br><br>

-  Data Usage: ​ The dataset is intended for public access and use.
