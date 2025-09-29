# ALUNING_RYA_2A_PA3
This repository includes Python programs that provide solutions to two (2) problems from Program Assignment 3: Python Data Analysis.

---

## PROBLEM 1

**Problem:**
Using knowledge obtained from the experiment and demonstrations: <br> 
a. Load the corresponding `.csv` file into a DataFrame named `cars` using pandas. <br> 
b. Display the first five and last five rows of the resulting `cars`. <br> 

### Code Process

**Explanation:**
We first need to import the **pandas** library, which is widely used for data analysis. By giving it an alias `pd`, we make it easier to call its functions later in the program.

```python
import pandas as pd
```

**Explanation:**
Now, we load the dataset `cars.csv` into a DataFrame called `cars`. A **DataFrame** is like a table with rows and columns, and it allows us to easily manipulate and analyze the dataset.

```python
cars = pd.read_csv('cars.csv')
cars
```

**Explanation:**
To check the beginning of our dataset, we use `.head()`. By default, this displays the **first five rows**, helping us verify that the dataset was loaded properly.

```python
cars.head()
```

**Explanation:**
To check the end of the dataset, we use `.tail()`. This displays the **last five rows**, which ensures that the entire dataset was read without missing values at the bottom.

```python
cars.tail()
```

---

## PROBLEM 2

**Problem:**
Using the DataFrame `cars` in Problem 1, extract the following information using subsetting, slicing, and indexing operations: <br> 
a. Display the first five rows with odd-numbered columns (columns 1, 3, 5, 7...). <br> 
b. Display the row that contains the ‘Model’ of ‘Mazda RX4’. <br> 
c. How many cylinders (‘cyl’) does the car model ‘Camaro Z28’ have? <br> 
d. Determine how many cylinders (‘cyl’) and what gear type (‘gear’) do the car models ‘Mazda RX4 Wag’, ‘Ford Pantera L’ and ‘Honda Civic’ have. <br> 

### Code Process

**Explanation:**
Before extracting data, we again import pandas and load the `cars.csv` file into a DataFrame. This step is necessary to perform subsetting and slicing.

```python
import pandas as pd
cars = pd.read_csv('cars.csv')
```

**Explanation (Part a):**
To get only the odd-numbered columns, we use `.iloc[:, 1::2]`.

* `:` means select all rows.
* `1::2` means start from column index 1 and then skip every other column (1, 3, 5...).
  After that, `.head()` is used to show only the first five rows of these selected columns.

```python
odd_columns = cars.iloc[:, 1::2]
result = odd_columns.head()
result
```

**Explanation (Part b):**
To display the row containing the model `Mazda RX4`, we use slicing. Since it is located at the very first row of the dataset, we slice `0:1` to return just that row while keeping the DataFrame format.

```python
cars[0:1]
```

**Explanation (Part c):**
To check the number of cylinders (`cyl`) of the `Camaro Z28`, we use `.loc[]` for label-based indexing.

* The condition `cars['Model'] == 'Camaro Z28'` finds the row where the model matches.
* `['Model', 'cyl']` specifies that only the Model and cyl columns should be shown.

```python
cars.loc[cars['Model']=='Camaro Z28', ['Model', 'cyl']]
```

**Explanation (Part d):**
For multiple cars (`Mazda RX4 Wag`, `Ford Pantera L`, and `Honda Civic`), we use `.loc[]` with specific row indices `[1, 28, 18]`.

* These indices correspond to the three models in the dataset.
* `['Model', 'cyl', 'gear']` ensures we only display the relevant information: model, number of cylinders, and gear type.

```python
cars.loc[[1,28,18], ['Model', 'cyl', 'gear']]
```

---

## Conclusion

In this program assignment, we learned how to use pandas to perform basic data analysis tasks such as loading datasets, subsetting, slicing, and indexing.

* In **Problem 1**, we practiced loading a CSV file into a DataFrame and previewing its content using `.head()` and `.tail()`.
* In **Problem 2**, we applied different indexing techniques to extract specific rows and columns, demonstrating how powerful pandas is in filtering and organizing data.

Overall, this exercise provided hands-on experience in data wrangling using Python, which is a fundamental skill for working with datasets in real-world applications.

---
*Version 2*
