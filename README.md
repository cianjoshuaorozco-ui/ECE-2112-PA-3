# ECE-2112-PA-3
Cian Joshua Orozco | 2ECED

This repository contains Programming Assignment 3 for course, ECE2112 (Advanced Computer Programming and Algorithms). This assignment covers three problems associated to module 3.

<br>

## Instruction

Use the same cars.csv dataset supplied for Experiment 3. Write the solutions in one Jupyter Notebook and import Pandas as pd. The dataset contains the Model column together with the vehicle
variables used in the original experiment.

* Load the CSV file into a DataFrame named cars.

* Use Pandas subsetting, slicing, indexing, and Boolean conditions. Do not manually type any
requested table or answer.

* Do not modify values in cars; create a new DataFrame or Series for each requested subset.

* Preserve the row order of the source dataset unless stated otherwise.

* Display every requested result in an executed notebook cell.

<br>
<br>

```
import pandas as pd

cars = pd.DataFrame(pd.read_csv('cars.csv'))
cars
```

```import pandas as pd``` imports the Pandas library and assigns it as ```pd``` to be used in the script.

```cars = pd.DataFrame(pd.read_csv('cars.csv'))``` loads a .csv file named cars and loads it as a DataFrame named ```cars```.

```cars``` displays DataFrame.

<br>
<br>

## Problem A. Positional and Label-Based Slicing
After loading cars, complete the following operations.

__Objectives:__

```
a. Display the shape and complete list of column names of cars.

b. Using positional slicing, create cars 6 to 10 containing rows 6 through 10 of the dataset, where
the first data row is row 1.

c. From cars 6 to 10, display only the columns Model, mpg, cyl, hp, and gear, in that order.

Requirement: The row selection in part (b) must use iloc; the column selection in part (c) must
use column labels.
```

### a.

```
print(cars.shape)

column = list(cars.columns)
column
```
<br>

```print(cars.shape)``` prints a tuple that describes the dimensions (rows, columns) of the DataFrame ```cars```.

```column = list(cars.columns)``` extracts the names of all the columns from the DataFrame ```cars``` and stores them in the list ```column```.

```column``` displays the list of all the columns in the DataFrame ```cars```.

### b.

```
cars_6_to_10 = cars.iloc[5:10]
cars_6_to_10
```
<br>

```cars_6_to_10 = cars.iloc[5:10]``` uses ```.iloc``` to perform the extraction by using numerical position, extracting rows 6 to 10 by indices 5 to 9 (since index 10 is exclusive) and stores them in ```cars_6_to_10```.

```cars_6_to_10``` displays the extracted rows 6 to 10.

### c.

```
cars_6_to_10_c= cars_6_to_10.loc[:,['Model', 'mpg', 'cyl', 'hp', 'gear']]
cars_6_to_10_c
```
<br>

```cars_6_to_10_c = cars_6_to_10.loc[:, ['Model', 'mpg', 'cyl', 'hp', 'gear']]``` uses ```.loc``` to extract columns with labels instead of numerical positions. ```:``` selects all the rows for the search, while the list specifies the column labels that need to be extracted. The extracted requested columns will be stored in ```cars_6_to_10_c```.

```cars_6_to_10_c``` displays the filtered DataFrame with only the selected columns.

## Problem B. Model Lookup
## Problem C. Multi-Model Subsetting

## History
* 2026, September 08: File Created.
* 2026, September 08: Objectives and details added for Problem A.
* 2026, September 09: Objectives and details added for problem B and C.
