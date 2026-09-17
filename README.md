# ECE-2112-PA-3
**Made by: Adrian Earl A. Ng | 2ECE-C**  
  
This repository contains Programming Assignment 1 for the course "ADVANCED COMPUTER PROGRAMMING AND ALGORITHMS" with code ECE2112 during S.Y.2026-2027.
Programming Assignment 2 has 3 python problems related to Module 3: Pandas.
# A. POSITIONAL AND LABEL-BASED SLICING
After loading cars, complete the following operations.  
**a.** Display the shape and complete list of column names of `cars.`  
**b.** Using positional slicing, create `cars_6_to_10` containing rows 6 through 10 of the dataset, where
the first data row is row 1.  
**c.** From `cars_6_to_10`, display only the columns `Model`, `mpg`, `cyl`, `hp`, and `gear`, in that order.

`df.iloc([0],[0])` - used in this problem to select which rows and columns of data frame `cars` would be copied to new data frame `cars_6_to_10`.  
`df.shape` - used in this problem to output a set showing the dimensions of the data frame.  
`df.columns` - used in this problem to output a set listing all the column's names in the data frame.  
`df.loc[[0],['column_name']]` -  used to isolate which columns and rows to copy over to the new data frame.
```python
cars = pd.read_csv('cars.csv')
cars_6_to_10 = cars.iloc[5:10, [0, 1, 2, 4, 10]]
print ("Shape of Data Frame 'cars': ", cars.shape, "\n\n", cars.columns,"\n\nData Frame 'cars_6_to_10':")
cars_6_to_10.loc[:, ['Model', 'mpg', 'cyl', 'hp', 'gear']]
```

# B. MODEL LOOKUP
Use Boolean indexing on the `Model` column to answer both requests.  
**a.** Display the complete row for `Toyota Corolla`.  
**b.** For `Pontiac Firebird`, display only `Model`, `mpg`, `hp`, and `wt`.  

Store the two results in `toyota` and `pontiac`, respectively. Do not use a hard-coded row number to locate either model.

No new functions were used in this problem. The output `toyota` and `pontiac` were in different cells to preserve the formatting of a data frame without importing another library. 
```python
toyota = cars.loc[cars['Model']=='Toyota Corolla']
pontiac = cars.loc[cars['Model']=='Pontiac Firebird', ['Model', 'mpg', 'hp', 'wt']]
toyota

pontiac
```

# C. MULTI-MODEL SUBSETTING
Create a DataFrame named `selected_cars` containing only the records for three models: `Datsun 710`, `Lotus Europa`, and `Ferrari Dino`.  

For these records, retain only `Model`, `mpg`, `cyl`, `hp`, and `gear`. Select the rows by their model values rather than by row numbers. Display `selected_cars` and its shape.

No new functions were used in this problem. Simple indexing and logical arguments were used to specify which columns and rows to copy into the new data frame `selected_cars`.
```python
selected_cars = cars.loc[(cars['Model']=='Datsun 710') | (cars['Model']=='Lotus Europa') | (cars['Model']=='Ferrari Dino'), ['Model', 'mpg', 'cyl', 'hp', 'gear']]
print ("Shape of Data Frame 'selected_cars'", selected_cars.shape, "\n\nData Frame 'selected_cars':")
selected_cars
```

**README File Version History:**  
September 8, 2026 - Initial README output  
September 10, 2026 - Added some solution explanations
September 17, 2026 - Added some more solution explanations
