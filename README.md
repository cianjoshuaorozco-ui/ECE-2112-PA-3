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

```print(cars.shape)``` prints a tuple that describes the dimensions (rows, columns) of ```cars```.

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

```cars_6_to_10_c = cars_6_to_10.loc[:, ['Model', 'mpg', 'cyl', 'hp', 'gear']]``` uses ```.loc``` to extract columns with labels instead of numerical positions. ```:``` selects all the rows for the search, while the list ```['Model', 'mpg', 'cyl', 'hp', 'gear']``` specifies the column labels that need to be extracted. The extracted requested columns will be stored in ```cars_6_to_10_c```.

```cars_6_to_10_c``` displays the filtered DataFrame with only the selected columns.

<br>
<br>

## Problem B. Model Lookup

Use Boolean indexing on the Model column to answer both requests

__Objectives:__

```
a. Display the complete row for Toyota Corolla.

b. For Pontiac Firebird, display only Model, mpg, hp, and wt.

Store the two results in toyota and pontiac, respectively. Do not use a hard-coded row number to
locate either model.

```

### a.
```
toyota = cars.loc[cars['Model']=='Toyota Corolla']
toyota
```

<br>

```toyota = cars.loc[cars['Model']=='Toyota Corolla']``` uses a boolean condition inside ```.loc``` to search for the row containing the model name "Toyota Corolla". The entire row is stored in ```toyota```.

```toyota``` displays the row extracted by the previous line.

<br>

### b.
```
pontiac = cars.loc[cars['Model']=='Pontiac Firebird', ['Model', 'mpg', 'hp', 'wt']]
pontiac
```

<br>

```pontiac = cars.loc[cars['Model']=='Pontiac Firebird', ['Model', 'mpg', 'hp', 'wt']]``` uses a boolean condition inside ```.loc``` to search for the row containing the model name "Pontiac Firebird". The row found is then filtered to only store certain columns given in the next argument ```['Model', 'mpg', 'hp', 'wt']``` and is then stored in ```pontiac```.

```pontiac``` displays the filtered row with the selected columns.

<br>
<br>

## Problem C. Multi-Model Subsetting

__Objetives:__

```
Create a DataFrame named selected cars containing only the records for three models: Datsun 710,
Lotus Europa, and Ferrari Dino.

For these records, retain only Model, mpg, cyl, hp, and gear. Select the rows by their model values
rather than by row numbers. Display selected cars and its shape.

Required check: The final DataFrame must contain exactly three rows and five columns.
```

<br>
<br>

```
selected_cars = cars.loc[(cars['Model']=='Datsun 710') | (cars['Model']=='Lotus Europa') | (cars['Model']=='Ferrari Dino'), ['Model', 'mpg', 'cyl', 'hp', 'gear']]
display(selected_cars)

print(selected_cars.shape)
```

<br>

```selected_cars = cars.loc[(cars['Model']=='Datsun 710') | (cars['Model']=='Lotus Europa') | (cars['Model']=='Ferrari Dino'), ['Model', 'mpg', 'cyl', 'hp', 'gear']]``` uses boolean operator ```|``` (OR) inside ```.loc``` to search for rows containing the model names "Datsun 710", "Lotus Europa", and "Ferrari Dino". These rows are filtered to only store specific named columns which were given in the next argument ```['Model', 'mpg', 'cyl', 'hp', 'gear']```. The filtered rows with the selected columns are stored in ```selected_cars```.

```display(selected_cars)``` displays the filtered rows.

```print(selected_cars.shape)``` prints a tuple that describes the dimension (rows, columns) of ```selected_cars```.


## History
* 2026, September 08: File Created.
* 2026, September 08: Objectives and details added for Problem A.
* 2026, September 09: Objectives and details added for problem B and C.
