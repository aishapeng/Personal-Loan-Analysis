# Personal Loan Analysis

## Task 1
Data Loading and Data Cleaning

i. Select important attributes

Firstly, attributes that are useful to analyse personal loans are selected. The description of the attributes can be found from the the origin of the dataset. Using the describe() PySpark Sql function, it computes the basic statistics for numeric and string columns which includes the count, mean, standard deviation, minimum, and maximum of the columns (PySpark 3.1.2 documentation, 2021). From the description, it can be seen that the data is dirty and the summary includes null values and dirty data. To achieve accurate data summary, these data has to be cleaned.

<img width="454" alt="image" src="https://user-images.githubusercontent.com/55709960/157483509-3e6e246c-d4a1-4279-9b6e-006456deac97.png">

ii. Remove null values and describe summary

Any rows with null values are dropped using dropna() which returns a new DataFrame omitting rows with null values (PySpark 3.1.2 documentation, 2021). Now, the DataFrame data is cleaned, and the describe() function is called again on the cleaned dataset to describe the count, mean, standard deviation, minimum, and maximum of the important attributes. The display() function makes it easier to show a large table in a meaningful display, showing the big picture of the dataset.

<img width="467" alt="image" src="https://user-images.githubusercontent.com/55709960/157483761-38908a70-cbdb-4f85-862d-7dc726f936af.png">

iii. Summary of data grouped and ordered by grade column

To take a closer look at the dataset, the grade column is chosen to group the data and show the summary of the dataset. This allows a more detailed look on the data to understand the different grades of loan. In order to do so, the grade column needs to be grouped using the groupBy() function which groups DataFrame to enable aggregate functions. Aggregate functions combines multiple rows of data into a single output, such as finding the sum or mean of input rows (Herviawan, 2017). To look at the results in a simpler way, the results are ordered ascendingly by the grade column using orderBy() function. 

The maximum, minimum, mean, and standard deviation of the input rows are queried using max(), min(), mean(), and stddev() functions respectively. To select all columns in a DataFrame, an asterisk symbol (*) can be used to represent all columns. From the summary, some insightful data is found such as higher grade loans (F) have higher interest rates and higher annual incomes

<img width="485" alt="image" src="https://user-images.githubusercontent.com/55709960/157483787-39547304-9e07-48eb-ac39-51d5910ea05c.png">

## Task 2
Data Transformations and Display Results

i. Find the distinct employment length in years. Possible values are from 0 to 10. Use two types of regular expressions (e.g. regexp_replace, regexp_extract) to clean the values in employment in years.

<img width="458" alt="image" src="https://user-images.githubusercontent.com/55709960/157484182-756a60df-1b38-43e2-939f-90d0a813ab8c.png">


ii. Identify the term, employment length columns and remove the string values then convert to numeric values by using Spark action command to show the details.

<img width="456" alt="image" src="https://user-images.githubusercontent.com/55709960/157484314-d45df66e-e299-4ced-8583-eab13c852b17.png">


iii. List the loan_status_grade by displaying the loan grade as In Grace period, fully paid, null valueifany, Late(31-120days), Late(16-30days), Current and Charged off.

<img width="454" alt="image" src="https://user-images.githubusercontent.com/55709960/157484385-6d207c23-dbce-423c-8754-2c94ab61996e.png">

iv. Display the purpose (loan types) and count the type of loans assigned after the total removal of null values. You can significantly use pyspark.sql functions isnan, when, count, over the selected columns which you did in Task 1.

<img width="454" alt="image" src="https://user-images.githubusercontent.com/55709960/157484642-47c01c3a-3dbb-4615-8cb2-99a56f043ded.png">


v. Manipulate the data transformations for the columns (dti, revol_util, late(31 -days), late(16- 30days) then groupby the loan_stats and count the number of bad_loan and good_loan. Determine the final schema to parquet and save table as Final_loan_data.

<img width="454" alt="image" src="https://user-images.githubusercontent.com/55709960/157484773-d2333e8b-8648-4b0f-bc2b-e8ede6e110ec.png">


