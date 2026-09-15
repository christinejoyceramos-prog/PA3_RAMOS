PA3 | ECE2112 | EXPERIMENT 3 | RAMOS

PANDAS

Submitted by Ramos, Christine Joyce S. | 2ECE-A | 09.15.2026

Objectives

At the end of this laboratory activity, the student should be able to:
1. load a CSV dataset into a Pandas DataFrame;
2. select rows and columns using positional and label-based indexing;
3. filter records using conditions on a DataFrame column; and
4. extract a well-defined subset of data without changing the source data.

Instructions

Use the same cars.csv dataset supplied for Experiment 3. Write the solutions in one Jupyter Notebook and import Pandas as pd. The dataset contains the Model column together with the vehicle variables used in the original experiment.

• Load the CSV file into a DataFrame named cars.

• Use Pandas subsetting, slicing, indexing, and Boolean conditions. Do not manually type any requested table or answer.

• Do not modify values in cars; create a new DataFrame or Series for each requested subset.

• Preserve the row order of the source dataset unless stated otherwise.

• Display every requested result in an executed notebook cell.


PROGRAMMING PROBLEMS

A. POSITIONAL AND LABEL-BASED SLICING

After loading cars, complete the following operations.

a. Display the shape and complete list of column names of cars.

b. Using positional slicing, create cars 6 to 10 containing rows 6 through 10 of the dataset, where
the first data row is row 1.

c. From cars 6 to 10, display only the columns Model, mpg, cyl, hp, and gear, in that order.

Requirement: The row selection in part (b) must use iloc; the column selection in part (c) must
use column labels.

CODE

"import pandas as pd // this imports the pandas library as pd

cars = pd.read_csv('cars.csv') // this loads the data set named "cars" in the data frame // it displays the cars Data Frame

print("Shape of cars:", cars.shape) // this prints the row and columns
print("Column names:", cars.columns.tolist()) // this shows the list of the column names

cars_6_to_10 = cars.iloc[5:10] // this selects rows 6 through 10
selected_columns = ['Model', 'mpg', 'cyl', 'hp', 'gear']
cars_6_to_10_subset = cars_6_to_10[selected_columns]"

