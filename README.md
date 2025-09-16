# ALUNING_RYA_2A_PA3
This repository includes Python programs that provide solutions to two (2) problems from Program Assignment 3: Python Data Analysis.

---
## PROBLEM 1
**Problem:** Using knowledge obtained from the experiment and demonstrations: <br>
a. Load the corresponding .csv file into a data frame named cars using pandas <br>
b. Display the first five and last five rows of the resulting cars <br>
**Code Process:**
1. The program begins by importing the Pandas library and referring to it as pd.
2. It then reads the dataset cars.csv using pd.read_csv() and stores the contents in a DataFrame named cars.
3. The cars DataFrame is displayed, showing all the rows and columns of the dataset, including attributes such as model, mpg, cylinders, horsepower, weight, and others.
4. To examine the first few records, the program uses cars.head(), which returns the first 5 rows of the dataset.
5. Similarly, to view the last few records, the program uses cars.tail(), which returns the last 5 rows of the dataset.

```Python
import pandas as pd

cars = pd.read_csv('cars.csv')
cars

#to show the first 5 rows
cars.head()

#to show the last 5 rows
cars.tail()
```
---
## PROBLEM 2
**Problem:** Using the dataframe cars in problem 1, extract the following information using subsetting, slicing and indexing operations. <br>
a. Display the first five rows with odd-numbered columns (columns 1, 3, 5, 7...) of cars. <br>
b. Display the row that contains the ‘Model’ of ‘Mazda RX4’. <br>
c. How many cylinders (‘cyl’) does the car model ‘Camaro Z28’ have? <br>
d. Determine how many cylinders (‘cyl’) and what gear type (‘gear’) do the car models ‘Mazda RX4 Wag’, ‘Ford Pantera L’ and ‘Honda Civic’ have <br>

**Code Process:**
1. The program starts by importing the Pandas library and referring to it as pd.
2. The dataset cars.csv is read using pd.read_csv() and stored in a DataFrame called cars.
3. **(a)** To display the first five rows with odd-numbered columns (1, 3, 5, …), the program uses slicing with .iloc[:, 1::2] to select every second column starting from index 1, then applies .head() to retrieve the first five rows. The result is stored in result.
4. **(b)** To display the row containing the model Mazda RX4, the program selects it using slicing: cars[0:1], since it is the first row in the dataset.
5. **(c)** To determine how many cylinders (cyl) the Camaro Z28 has, the program uses label-based indexing with .loc[]:
6. **(d)** To find the number of cylinders (cyl) and gear type (gear) for Mazda RX4 Wag, Ford Pantera L, and Honda Civic, the program uses .loc[] with specific row indices [1, 28, 18] and selects only the Model, cyl, and gear columns.

```Python
import pandas as pd

cars = pd.read_csv('cars.csv')
cars

#To display first five rows with odd-numbered columns
odd_columns = cars.iloc[:, 1::2]
result = odd_columns.head()
result

#To display the row containing the model Mazda RX4
cars[0:1]

#To determine how many cylinders (cyl) the Camaro Z28 has
cars.loc[cars['Model']=='Camaro Z28', ['Model', 'cyl']]

#To find the number of cylinders (cyl) and gear type (gear) for Mazda RX4 Wag, Ford Pantera L, and Honda Civic
cars.loc[[1,28,18],['Model', 'cyl', 'gear']]

```
---
