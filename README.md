 <h1 align="center">pands-project2023</h1>
 <h2 align="center">Iris Dataset</h2>

  <p align="center">
   Cecilia Pastore 

<details>
    <summary> Project assignement </summary>
           <p>

<h3 align="center"> Problem statement </h2>
 
>This project concerns the well-known Fisher’s Iris data set [3]. You must research the data set
and write documentation and code (in Python [1]) to investigate it. An online search for
information on the data set will convince you that many people have investigated it
previously. You are expected to be able to break this project into several smaller tasks that
are easier to solve, and to plug these together after they have been completed.

>You might do that for this project as follows:
> 1. Research the data set online and write a summary about it in your README.
> 2. Download the data set and add it to your repository.
> 3. Write a program called analysis.py that:
> 4. Outputs a summary of each variable to a single text file,
> 5. Saves a histogram of each variable to png files, and
> 6. Outputs a scatter plot of each pair of variables.
> 7. Performs any other analysis you think is appropriate
 
>You may produce a Jupyter notebook as well containing all your comment. This notebook
should only contain text that you have written yourself, (it may contain referenced code
from other sources). I will harshly mark any text (not code) that I feel is not written directly
by you. I want to know what YOU think, not some third party.
>It might help to suppose that your manager has asked you to investigate the data set, with a
view to explaining it to your colleagues. Imagine that you are to give a presentation on the
data set in a few weeks’ time, where you explain what investigating a data set entails and how
Python can be used to do it. You have not been asked to create a deck of presentation slides,
but rather to present your code and its output to them. 
 

</p>
</details>

### Table of content
* [Iris Flower Datases - introduction](https://github.com/Cecilia8989/pands-project/blob/main/README.md#iris-flower-datases---introduction)
* [Import dataset](https://github.com/Cecilia8989/pands-project/blob/main/README.md#-import-dataset-)
  - [Import data set from an online location to a csv](https://github.com/Cecilia8989/pands-project/blob/main/README.md#import-data-set-from-an-online-location-to-a-csv)
  - [Import  the dataset from the CSV to the main script and adjust his format](https://github.com/Cecilia8989/pands-project/blob/main/README.md#import--the-dataset-from-the-csv-to-the-main-script-and-adjust-his-format)
* [Getting information about the Dataset](https://github.com/Cecilia8989/pands-project/blob/main/README.md#-getting-information-about-the-dataset-)
  - [Creation and introduction]()
  - [Check how appear the data in the Dataset](https://github.com/Cecilia8989/pands-project/blob/main/README.md#-check-how-appear-the-data-in-the-dataset-)
  - [Check Unique value](https://github.com/Cecilia8989/pands-project/blob/main/README.md#-check-unique-value-)
  - [Checking missing values](https://github.com/Cecilia8989/pands-project/blob/main/README.md#-checking-missing-values-)
  - [Shape of the dataset](https://github.com/Cecilia8989/pands-project/blob/main/README.md#-shape-of-the-dataset-)
  - [Data Type](https://github.com/Cecilia8989/pands-project/blob/main/README.md#-data-type-)
  - [Statistics](https://github.com/Cecilia8989/pands-project/blob/main/README.md#statistics)
  - [Statistics grouped by species](https://github.com/Cecilia8989/pands-project/blob/main/README.md#-stetistics-grouped-by-species)
  - [Quartiles per species](https://github.com/Cecilia8989/pands-project/blob/main/README.md#-quartiles-per-species-)
* []()
* []()
* []()


### Iris Flower Datases - introduction 
The iris flower dataset is a well-known dataset in the field of data science, and it is often used to illustrate basic data analysis, visualization techniques and machine learning .  The Iris Dataset is considered as the "Hello World" for data science [[Fig.1]](https://machinelearninghd.com/iris-dataset-uci-machine-learning-repository-project/).

<p align="center">
  <img src=https://machinelearninghd.com/wp-content/uploads/2021/03/iris-dataset.png>
</p>

The dataset contains measurements of the sepal length, sepal width, petal length, and petal width for 150 iris flowers belonging to three different species: Iris setosa, Iris versicolor, and Iris virginica. Fifty samples are collected for each species [[Fig.2]](https://www.bogotobogo.com/python/scikit-learn/scikit_machine_learning_features_extraction.php).

The iris flower dataset was originally collected by the botanist Edgar Anderson in the 1930s and later popularized by the statistician Ronald Fisher in his seminal paper on discriminant analysis. The dataset is sometimes referred to as Anderson's Iris dataset, as Anderson collected it to quantify the morphological variations among three closely related Iris species. Anderson ensured that all of the samples were collected from the same pasture on the Gaspé Peninsula, on the same day, and measured at the same time by the same person using the same apparatus [[1]](https://rpubs.com/AjinkyaUC/Iris_DataSet).

Since then, the dataset has become a classic example in the field of data science, and it is frequently used in introductory courses and textbooks. It is a simple and well-understood dataset, making it a popular choice for teaching and research purposes, providing an excellent opportunity to explore different aspects of data analysis and visualization.

The dataset is widely available and can be accessed freely on the [UCI website [2]](https://archive.ics.uci.edu/ml/datasets/iris).

<p align="center">
  <img src=https://www.bogotobogo.com/python/scikit-learn/images/features/iris-data-set.png>
</p>


<h3> Import dataset </h3>

#### Import data set from an online location to a csv 

As a first task, The dataset need to be imported and transformed in a CSV [[3]](https://www.angela1c.com/projects/iris_project/downloading-iris/).
I have:
- imported the iris dataset from the [UCI Machine learning repository](http://archive.ics.uci.edu/ml/machine-learning-databases/iris/) in data format
- changed the column names to correspond with the attribute information in a nice format
- and saved the dataset as a CSV 

To avoid having Python download the dataset every time the main script is executed, I created a separate script called **downloadiris.py**.


<details>
    <summary> Code Explanation </summary>
           <p>
            
Import the Pandas library. 
Pandas [[4]](https://www.w3schools.com/python/pandas/default.asp) is a powerful library with many functions for analyzing data, and in this case, it will be used to read the file as a CSV.

```python
import pandas as pd 
```
Define the URL from which to download the dataset from the UCI Machine Learning Repository.
```python
csv_ulr =  'https://archive.ics.uci.edu/ml/machine-learning-databases/iris/iris.data'
```
The dataset downloaded from csv_url does not contain any column names that match the attribute information. Therefore, we manually define column names.

```python
col_names = ['SepalLenght(cm)', 'SepalWidth(cm)', 'PetalLenght(cm)', 'PetalWidth(cm)', 'Species']
```
Using Panda library to download the dataset as a CSV and set the colums name.

```python
col_names = iris =  pd.read_csv(csv_ulr, names = col_names)
```
Save the CSV file and print a message to show the code have been execute correctly.

```python
iris.to_csv("iris_dataset.csv", index=False)
print("iris_dataset.csv created")
```
</p>
</details>

#### Import  the dataset from the CSV to the main script and adjust his format.

After saving the dataset from an online location as a CSV file in the same repository, we need to import it into our main script and adjust its format for further analysis. 

To do this, we can begin by importing the necessary libraries at the start of our script. 
We then import and define the dataset in the scrip and adjust the column/species names to a more readable format.  

##### *Import the libraries*

For this script we will use the the following libraries:

- pandas: a library for data manipulation and analysis
- NumPy: a library for numerical operations on arrays and matrices
- Matplotlib.pyplot: a plotting library for creating plot
- PyLab: a library that combines Matplotlib with NumPy functionality
- Seaborn: a library for creating informative and attractive statistical graphics

<details>
    <summary> Code </summary>

```python
# import needed libraries 
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import pylab as pl
import seaborn as sns 
```  
</p>
</details>

##### *Import the dataset from the CSV file*

The first part of the script is to define and import the dataset from the CSV file. 
This has been done using pandas library's read_csv() function [[5]](https://realpython.com/python-csv/#reading-csv-files-with-pandas). The dataset is stored in the DataFrame called 'df'.

<details>
    <summary> Code </summary>
           <p>
            
```python
# import data from a csv file using pandas 
df = pd.read_csv('iris_dataset.csv')
```
</p>
</details>

##### *Change the series name*

The code then replaces the names of the three species with more friendly names using the replace() method of the Series object representing the "Species" column[[6]](https://datagy.io/pandas-replace-values/).
The 'to_replace' parameter specifies the value to be replaced, while the 'value' parameter specifies the new value.

<details>
    <summary> Code </summary>
           <p>

```python
# replace the 3 spieces with a more friendly name 
df["Species"].replace(to_replace="Iris-setosa", value="Setosa", inplace=True)
df["Species"].replace(to_replace="Iris-versicolor", value="Versicolor", inplace=True)
df["Species"].replace(to_replace="Iris-virginica", value="Virginica", inplace=True)
```
</p>
</details>

<h3> Getting information about the Dataset </h3>

Once the dataset have been imported and formatted in the needed way, we will need to explore it and prepare it for analysis. This analysis of the information contained in the dataset, as requested, will be printed in a text file called **iris_analysis.txt** .

 <h4> Creation and introduction </h4>

This code opens a  file (and create it if is not already created) named iris_analysis.txt in write mode. The subsequent lines of code write an introduction to the file, including the author's name and the title of the project.

```
Project for the Subject Programming and Scripting 
 
Author: Cecilia Pastore 
 iris_analysis.txt 
```
</p>
</details>

<details>
    <summary> Code explanation </summary>
           <p>

The code is creating a new file named "iris_analysis.txt" and opening it in write mode using the open() function, with the file object being assigned to the variable f. The code then writes some introductory information about the text file, including the project title, author name, and the name of the text file itself [[7]](https://datagy.io/python-write-text-file/).

```python
# create the text file and write on them 
with open ('iris_analysis.txt', 'w') as f:
    # print an introduction of the text file 
    f.write("Project for the Subject Programming and Scripting \n \n")
    f.write("Author: Cecilia Pastore \n ")
    f.write("iris_analysis.txt \n \n")   
```

</p>
</details

<h4> Check how appear the data in the Dataset </h4>

Now, We can take a look on how the Data-Set look like printing the first 5 lines of it. 

```
Project for the Subject Programming and Scripting 
 
Author: Cecilia Pastore 
 iris_analysis.txt 
 
==== First 5 lines of the dataset ==== 
 
   SepalLenght(cm)  SepalWidth(cm)  PetalLenght(cm)  PetalWidth(cm) Species
0              5.1             3.5              1.4             0.2  Setosa
1              4.9             3.0              1.4             0.2  Setosa
2              4.7             3.2              1.3             0.2  Setosa
3              4.6             3.1              1.5             0.2  Setosa
4              5.0             3.6              1.4             0.2  Setosa
```

<details>
    <summary> Code Explanation </summary>
           <p>
First I have added a little introduction to be print in the text file. 
After, the 'df.head()' [[8]](https://www.geeksforgeeks.org/python-pandas-dataframe-series-head-method/) function have been used to display the first 5 rows of the df dataset, and then converts the output to a string using str(). The resulting string is then written to the file using the f.write() function.


```python
    # checking the first 5 line of the dataset to see if the format fit
    f.write("==== First 5 line of the dataset ==== \n \n")
    f.write(str(df.head())+'\n \n')
```

</p>
</details>

<h4> Check Unique value </h4>

We can now print the unique values of the column *Species*. This has the double function to check no duplicates of *Species* have been entered and the replace of the Species names have been done correctly. 
As we can see from the output, there are no other value apart of the three wanted *Species* and the rename of them have beene executed correctly.

```
==== Print unique value of species ==== 
 
Species
 
Setosa
Versicolor
Virginica
```

<details>
    <summary> Code Explanation </summary>
           <p>

The script defines a variable *unique_species* that contains the unique values in the *Species* column of the dataset. I would have been to do it through the use of *drop.duplicate()* function [[9]](https://www.geeksforgeeks.org/exploratory-data-analysis-on-iris-dataset/) or through the *unique()* function [[10]](https://www.projectpro.io/recipes/list-unique-values-in-pandas-dataframe). I chose to unique function to give a more tidy looking on the text file. 
Then, it writes these values in the text file using a for loop to display the values in a more readable format. The output is a list of unique species names, with each species name on a separate line, and the text "Species" written at the beginning to clarify the content of the list.

```python
    # print unique value on the the species colume to check no duplicate and that the replace has been done correctly 
    f.write("==== Print unique value of species ==== \n \n")
    unique_species = pd.unique(df['Species'])
    f.write("Species\n \n")
    for species in unique_species:
        f.write(species)
        f.write("\n")
    f.write("\n")
```

</p>
</details>

<h4> Checking missing values </h4>

The script will check if there are missing value or not. Missing values refer to the absence of data or information for one or more items or a whole unit. It can happen when the data is not provided, is lost or simply does not exist. We can see from the output that no column as any missing value. This was expected ad the iris dataset is know for not having missing values.

```
==== Checking missing value ==== 
 
SepalLenght(cm)    0
SepalWidth(cm)     0
PetalLenght(cm)    0
PetalWidth(cm)     0
Species            0
dtype: int64
```

<details>
    <summary> Code Explanation </summary>
           <p>

The script check missing value using the *isnull()* function [[9]](https://www.geeksforgeeks.org/exploratory-data-analysis-on-iris-dataset/).

```python
    # checking missing value
    f.write("==== Checking missing value ==== \n \n")
    f.write(str(df.isnull().sum())+'\n \n')   
```

</p>
</details>

 <h4> Shape of the dataset </h4>

The script prints the shape of the dataset, which is the number of rows and columns in the dataset. It also prints the size of the dataset, which is the product of the number of rows and columns, a list of all the column names in the dataset. 
Finally it show the number on entries for each species.
As we can see we have 150 lines, 5 columns for a total size of 750 entries. Each species has 50 entries .

```
==== Shape of the dataset ==== 
 
Number of rows: 150
Number of columns: 5
Size: 750
Columns: SepalLenght(cm), SepalWidth(cm), PetalLenght(cm), PetalWidth(cm), Species

Species
Setosa        50
Versicolor    50
Virginica     50
dtype: int64
```

<details>
    <summary> Code Explanation </summary>
           <p>

The script is used to retrieve various information about a dataset. It first uses the *shape()* [[11]](https://stackoverflow.com/questions/58008120/how-to-use-format-in-python-to-print-out-the-data-shape) function to print the number of rows and columns in the dataset. Then, it uses the *size()* function to print the total number of entries in the dataset. The *join()* [[12]](https://sparkbyexamples.com/pandas/pandas-join-dataframes-on-columns/) function is used to concatenate the names of all columns in the dataset and print them. 
Finally, the *value_counts()* [[9]](https://www.geeksforgeeks.org/exploratory-data-analysis-on-iris-dataset/) function is used to count the number of entries for each species in the dataset and print them.

```python
   # shape of the datased
    f.write("==== Shape of the dataset ==== \n \n")
    f.write("Number of rows: {}\n".format(df.shape[0]))
    f.write("Number of columns: {}\n".format(df.shape[1]))
    f.write("Size: {}\n".format(df.size))
    f.write("Columns: {}\n\n".format(", ".join(df.columns)))
    f.write(str(df.value_counts("Species"))+'\n\n')
```

</p>
</details
 
 <details>

 <h4> Data Type </h4>
 
Next, the script checks the data type of each column in the dataset. It outputs this information in the text file, with each column name followed by its corresponding data type. As we can see, the data type of all columns is float except for the *Species* column, which is an object datatype that contains the species referred to in the measurements.

```
==== Data type ==== 
 
Attribute 	 	 	 	 Type 
 
SepalLenght(cm)    float64
SepalWidth(cm)     float64
PetalLenght(cm)    float64
PetalWidth(cm)     float64
Species             object
dtype: object
```

<details>
    <summary> Code Explanation </summary>
           <p>

The code use the *dtypes* function to get the type of each columns [[13]](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.dtypes.html).

```python
    # get the data type 
    f.write("==== Data type ==== \n \n")
    f.write("Attribute \t \t \t \t Type \n \n")
    f.write(str(df.dtypes)+'\n\n')  
```

</p>
</details

 <details>
 <h4>Statistics</h4>

Some descriptive statistics for each column of the dataset are provided. It includes the count, mean, standard deviation, minimum, maximum, and quartile values for numeric columns. This is done through the *describe()* function [[14]](https://www.w3resource.com/pandas/dataframe/dataframe-describe.php).

```
==== Statistics ==== 
 
       SepalLenght(cm)  SepalWidth(cm)  PetalLenght(cm)  PetalWidth(cm)
count       150.000000      150.000000       150.000000      150.000000
mean          5.843333        3.054000         3.758667        1.198667
std           0.828066        0.433594         1.764420        0.763161
min           4.300000        2.000000         1.000000        0.100000
25%           5.100000        2.800000         1.600000        0.300000
50%           5.800000        3.000000         4.350000        1.300000
75%           6.400000        3.300000         5.100000        1.800000
max           7.900000        4.400000         6.900000        2.500000
```

<details>
    <summary> Code Explanation </summary>
           <p>

The *describe()* function is used to calculate the count, mean, standard deviation, minimum, maximum, and quartile values for the numeric columns of the dataset. 

```python
    # get statistics 
    f.write("==== Statistics ==== \n \n")
    f.write(str(df.describe())+'\n\n')  
```

</p>
</details
 
<details>
 
 <h4> Stetistics grouped by species</h4>

Next I want to check the statistics (mean, mediam, std, min and max) for each species.

```
==== SepalLenght(cm) Statistics ====

             mean  median       std  min  max
Species                                      
Setosa      5.006     5.0  0.352490  4.3  5.8
Versicolor  5.936     5.9  0.516171  4.9  7.0
Virginica   6.588     6.5  0.635880  4.9  7.9

==== SepalWidth(cm) Statistics ====

             mean  median       std  min  max
Species                                      
Setosa      3.418     3.4  0.381024  2.3  4.4
Versicolor  2.770     2.8  0.313798  2.0  3.4
Virginica   2.974     3.0  0.322497  2.2  3.8

==== PetalLenght(cm) Statistics ====

             mean  median       std  min  max
Species                                      
Setosa      1.464    1.50  0.173511  1.0  1.9
Versicolor  4.260    4.35  0.469911  3.0  5.1
Virginica   5.552    5.55  0.551895  4.5  6.9

==== PetalWidth(cm) Statistics ====

             mean  median       std  min  max
Species                                      
Setosa      0.244     0.2  0.107210  0.1  0.6
Versicolor  1.326     1.3  0.197753  1.0  1.8
Virginica   2.026     2.0  0.274650  1.4  2.5

```

<details>
    <summary> Code Explanation </summary>
           <p>

This script loops through all columns except for the last one (the species , and for each column, it calculates the mean, median, standard deviation, minimum, and maximum value for each species in the dataset. It does this by using the *groupby()* [[15]](https://learnpython.com/blog/how-to-summarize-data-in-python/) function to group the data by species, and then using the *agg()* function to apply the statistical functions to each group. 

```python
    # get an user more friendly view of the statistics 
    # for loop to print for each species the varaible mean, median, std, min, max 
    for column in df.columns[:-1]:
        f.write(f"==== {column} Statistics ====\n\n")
        f.write(f"{df.groupby('Species')[column].agg(['mean', 'median', 'std', 'min', 'max'])}\n\n")
    # get quartile per species   
```

</p>
</details
 
<details>
 <h4> Quartiles per species </h4>

On the same path of the previous part of the script, I wanted check the quartiles focusing on each species.

```
==== Quartiles per species ==== 
 
                 SepalLenght(cm)  SepalWidth(cm)  PetalLenght(cm)  PetalWidth(cm)
Species                                                                          
Setosa     0.25            4.800           3.125            1.400             0.2
           0.50            5.000           3.400            1.500             0.2
           0.75            5.200           3.675            1.575             0.3
Versicolor 0.25            5.600           2.525            4.000             1.2
           0.50            5.900           2.800            4.350             1.3
           0.75            6.300           3.000            4.600             1.5
Virginica  0.25            6.225           2.800            5.100             1.8
           0.50            6.500           3.000            5.550             2.0
           0.75            6.900           3.175            5.875             2.3
```

<details>
    <summary>  </summary>
           <p>

This code calculates the quartiles for each species in the dataset using the *groupby* function. The *groupby* function groups the data by the Species column, and then the quantile function is applied to each group. The quantile function is given a list of values [0.25, 0.50, 0.75] which represent the quartiles that we want to calculate for each group [[16]](https://stackoverflow.com/questions/55009203/how-does-pandas-calculate-quartiles). 

```python
    # get quartile per species 
    f.write("==== Quartiles per species ==== \n \n")
    f.write(str(df.groupby('Species').quantile([0.25, 0.50, 0.75]))+'\n\n')   
```

</p>
</details
 
 
 <details>
 <h4> </h4>



```

```

<details>
    <summary>  </summary>
           <p>


```python
   
```

</p>
</details
 
 
<details>
    <summary>Sources</summary>
           <p>

 - [1] [rpubs](https://rpubs.com/AjinkyaUC/Iris_DataSet)
 - [2] [UCI Machine Learning repository](https://archive.ics.uci.edu/ml/datasets/iris)
 - [3] [Importing and viewing the Iris dataset using pandas](https://www.angela1c.com/projects/iris_project/downloading-iris/) 
 - [4] [Pandas Tutorial](https://www.w3schools.com/python/pandas/default.asp)
 - [5] [Reading and Writing CSV Files in Python](https://realpython.com/python-csv/#reading-csv-files-with-pandas)
 - [6] [Pandas replace() – Replace Values in Pandas Dataframe](https://datagy.io/pandas-replace-values/)
 - [7] [How to Use Python to Write a Text File (.txt)](https://datagy.io/python-write-text-file/)         
 - [8] [Python | Pandas Dataframe/Series.head() method](https://www.geeksforgeeks.org/python-pandas-dataframe-series-head-method/)
 - [9] [Exploratory Data Analysis on Iris Dataset](https://www.geeksforgeeks.org/exploratory-data-analysis-on-iris-dataset/)         
 - [10] [How to list unique values in a Pandas DataFrame?](https://www.projectpro.io/recipes/list-unique-values-in-pandas-dataframe) 
 - [11] [How to use .format in python to print out the data shape](https://stackoverflow.com/questions/58008120/how-to-use-format-in-python-to-print-out-the-data-shape) 
 - [12] [Pandas Join DataFrames on Columns](https://sparkbyexamples.com/pandas/pandas-join-dataframes-on-columns/) 
 - [13] [pandas.DataFrame.dtypes](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.dtypes.html)
 - [14] [Pandas DataFrame: describe() function](https://www.w3resource.com/pandas/dataframe/dataframe-describe.php)
 - [15] [How to Generate a Data Summary in Python](https://learnpython.com/blog/how-to-summarize-data-in-python/)
 - [16] [How does pandas calculate quartiles?](https://stackoverflow.com/questions/55009203/how-does-pandas-calculate-quartiles)
 - [] []()
 - [] []()
 - [] []()
 - [] []()
 - [Fig.1] [Iris Dataset Project from UCI Machine Learning Repository](https://machinelearninghd.com/iris-dataset-uci-machine-learning-repository-project/)
 - [Fig.2] [Machine Learning 101](https://www.bogotobogo.com/python/scikit-learn/scikit_machine_learning_features_extraction.php)

</p>
</details>
 
