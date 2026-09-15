PA3 | ECE2112 | EXPERIMENT 3 | RAMOS
---
PANDAS
---
Submitted by Ramos, Christine Joyce S. | 2ECE-A | 09.15.2026
---
Objectives
---
At the end of this laboratory activity, the student should be able to:
1. load a CSV dataset into a Pandas DataFrame;
2. select rows and columns using positional and label-based indexing;
3. filter records using conditions on a DataFrame column; and
4. extract a well-defined subset of data without changing the source data.

Instructions
---
Use the same cars.csv dataset supplied for Experiment 3. Write the solutions in one Jupyter Notebook and import Pandas as pd. The dataset contains the Model column together with the vehicle variables used in the original experiment.

• Load the CSV file into a DataFrame named cars.

• Use Pandas subsetting, slicing, indexing, and Boolean conditions. Do not manually type any requested table or answer.

• Do not modify values in cars; create a new DataFrame or Series for each requested subset.

• Preserve the row order of the source dataset unless stated otherwise.

• Display every requested result in an executed notebook cell.


PROGRAMMING PROBLEMS
---
A. POSITIONAL AND LABEL-BASED SLICING

After loading cars, complete the following operations.

a. Display the shape and complete list of column names of cars.

b. Using positional slicing, create cars 6 to 10 containing rows 6 through 10 of the dataset, where
the first data row is row 1.

c. From cars 6 to 10, display only the columns Model, mpg, cyl, hp, and gear, in that order.

Requirement: The row selection in part (b) must use iloc; the column selection in part (c) must
use column labels.

CODE
---
"import pandas as pd // this imports the pandas library as pd

cars = pd.read_csv('cars.csv') // this loads the data set named "cars" in the data frame // it displays the cars Data Frame

print("Shape of cars:", cars.shape) // this prints the row and columns
print("Column names:", cars.columns.tolist()) // this shows the list of the column names

cars_6_to_10 = cars.iloc[5:10] // this selects rows 6 through 10
selected_columns = ['Model', 'mpg', 'cyl', 'hp', 'gear']
cars_6_to_10_subset = cars_6_to_10[selected_columns]"

OUTPUT
---
Shape of cars: (32, 12)

Column names: ['Model', 'mpg', 'cyl', 'disp', 'hp', 'drat', 'wt', 'qsec', 'vs', 'am', 'gear', 'carb']

cars_6_to_10 - shows rows 6 through 10

cars_6_to_10_subset - shows rows 6 through 10 with only the columns "Model", "mpg", "cyl", "hp", and "gear"

B. MODEL LOOKUP
---
Use Boolean indexing on the Model column to answer both requests.

a. Display the complete row for Toyota Corolla.

b. For Pontiac Firebird, display only Model, mpg, hp, and wt.

Store the two results in toyota and pontiac, respectively. Do not use a hard-coded row number to
locate either model

CODE
---
toyota = cars[cars['Model'] == 'Toyota Corolla'] // this filters the data set for only the Toyota Carolla using Boolean indexing
display(toyota) // displays the full dataset of Toyota Corolla

pontiac = cars[cars['Model'] == 'Pontiac Firebird'][['Model', 'mpg', 'hp', 'wt']] // filter the dataset of Pontiac Firebird and only retains the specified columns 

display(pontiac) // displays the specified columns of Pontiac Firebird

OUTPUT
---
toyota - shows the the full dataset of Toyota Corolla

pontiac - displays the full row for Pontiac Firebird with only the specified columns 'Model', 'mpg', 'hp', and 'wt'

C. MULTI-MODEL SUBSETTING
---
Create a DataFrame named selected cars containing only the records for three models: Datsun 710,
Lotus Europa, and Ferrari Dino.

For these records, retain only Model, mpg, cyl, hp, and gear. Select the rows by their model values
rather than by row numbers. Display selected cars and its shape.

Required check: The final DataFrame must contain exactly three rows and five columns.

CODE
---
target_models = ['Datsun 710', 'Lotus Europa', 'Ferrari Dino'] // list of the specified car models

target_cols = ['Model', 'mpg', 'cyl', 'hp', 'gear'] // list of the specified columns

selected_cars = cars[cars['Model'].isin(target_models)][target_cols] // selects the rows matching the specified models and the specified columns

display(selected_cars) // this displays the final dataset for the required models

print("Shape of selected_cars:", selected_cars.shape) // this prints the shape to satisfy the required check.

OUTPUT
---
selected_cars - this displays the dataset for 'Datsun 710', 'Lotus Europa', 'Ferrari Dino' with only the specified columns 'Model', 'mpg', 'cyl', 'hp', and 'gear'

Shape of selected_cars: (3, 5)

END OF NOTEBOOK
---



