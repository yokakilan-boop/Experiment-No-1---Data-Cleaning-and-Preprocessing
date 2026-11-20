# Experiment No. 1: Data Cleaning and Preprocessing

## Aim

To perform data cleaning and preprocessing on a business dataset using Python libraries for better data quality and analysis readiness.

## Dataset

The dataset used for this experiment is `heartdisease.csv`. It contains
medical and demographic information related to heart disease patients.

The dataset is opened and analyzed using Jupyter Notebook to study its
data structure, identify data types, and perform basic statistical
analysis for data-cleaning and preprocessing purposes.

## Algorithm

1.  Import essential Python libraries.
2.  Load the dataset using Pandas.
3.  View the dataset structure, data types, and memory usage.
4.  Check for missing values and duplicates.
5.  Perform data summary statistics using `describe()`.
6.  View initial and final records using `head()` and `tail()`.
7.  Sort and group the data based on key attributes.
8.  Rename columns or modify data where necessary.
9.  Save the cleaned dataset for further analysis.

## Functions and Methods Used in the Experiment

### 1. Data Loading and Basic Exploration

  Function / Method      Description  
  ---------------------- ------------------------------------------------------\
  `pd.read_csv()`        Reads a CSV file into a Pandas DataFrame.\
  `df.info()`            Displays column names, data types, and memory usage.\
  `df.dtypes`            Returns the data types of all columns.\
  `df['column'].dtype`   Returns the data type of a specific column.\
  `df.describe()`        Provides summary statistics for numerical columns.\
  `df.head()`            Displays the first 5 rows of the DataFrame.\
  `df.tail()`            Displays the last 5 rows of the DataFrame.\

### 2. Sorting and Grouping

  Function / Method    Description  
  -------------------- ---------------------------------------------  
  `df.sort_values()`   Sorts the DataFrame by one or more columns.  
  `df.groupby()`       Groups data based on one or more columns.  
  `groupby.sum()`      Returns the sum for each group.  
  `groupby.mean()`     Returns the mean for each group.  
  `groupby.median()`   Returns the median for each group.  
  `groupby.max()`      Returns the maximum value in each group.  
  `groupby.min()`      Returns the minimum value in each group.  

### 3. Data Summary and Manipulation  

  Function / Method   Description  
  ------------------- ----------------------------------------------  
  `df.mean()`         Calculates the mean for all numeric columns.  
  `df.rename()`       Renames columns in the DataFrame.  

### 4. Optional Additions  

  Function / Method         Description  
  ------------------------- ----------------------------------------------  
  `df.isnull().sum()`       Checks for missing values in each column.  
  `df.duplicated().sum()`   Counts duplicate rows.  
  `df.dropna()`             Removes rows containing missing values.  
  `df.fillna()`             Fills missing values with a specified value.  
  `df.drop_duplicates()`    Removes duplicate rows.  
  `df.shape`                Returns the number of rows and columns.  
  `df.columns`              Lists column names in the DataFrame.  

## Program 
## Input

#Import essential Libraries
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
## Input 1
```
# More detailed info including memory usage

df.info()
```
## Output 1
```
<class 'pandas.core.frame.DataFrame'>
RangeIndex: 250 entries, 0 to 249
Data columns (total 17 columns):
 #   Column           Non-Null Count  Dtype  
---  ------           --------------  -----  
 0   S. No            250 non-null    int64  
 1   Gender           250 non-null    object 
 2   Age              250 non-null    int64  
 3   Education        250 non-null    int64  
 4   currentsmoker    250 non-null    int64  
 5   Cigsperday       250 non-null    int64  
 6   BPMeds           250 non-null    int64  
 7   Prevalentstroke  250 non-null    int64  
 8   PrevalentHyp     250 non-null    int64  
 9   Diabetes         250 non-null    int64  
 10  Totalcholestrol  250 non-null    int64  
 11  SysBP            250 non-null    float64
 12  DiaBP            250 non-null    float64
 13  BMI              250 non-null    float64
 14  Heartrate        250 non-null    int64  
 15  Glucose          250 non-null    int64  
 16  TenYearCHD       250 non-null    int64  
dtypes: float64(3), int64(13), object(1)
memory usage: 33.3+ KB 
```
# Input 2
```
#Get the summary of all variables / columns

df.describe()
```
# Output 2 
```
S. No	Age	Education	currentsmoker	Cigsperday	BPMeds	Prevalentstroke	PrevalentHyp	Diabetes	Totalcholestrol	SysBP	DiaBP	BMI	Heartrate	Glucose	TenYearCHD
count	250.000000	250.000000	250.00000	250.000000	250.000000	250.000000	250.000000	250.000000	250.000000	250.000000	250.00000	250.000000	250.000000	250.000000	250.000000	250.000000
mean	125.500000	50.088000	2.48000	0.456000	6.688000	0.108000	0.024000	0.256000	0.080000	235.192000	129.42760	83.491200	26.288400	84.220000	88.012000	0.184000
std	72.312977	12.268755	1.08735	0.499059	9.368336	0.311003	0.153356	0.437297	0.271837	37.276498	18.92353	11.649065	4.588731	16.377438	24.685407	0.388261
min	1.000000	30.000000	1.00000	0.000000	0.000000	0.000000	0.000000	0.000000	0.000000	120.000000	85.00000	55.600000	16.000000	55.000000	45.000000	0.000000
25%	63.250000	38.250000	2.00000	0.000000	0.000000	0.000000	0.000000	0.000000	0.000000	207.250000	118.02500	74.425000	23.200000	71.000000	72.000000	0.000000
50%	125.500000	51.500000	2.00000	0.000000	0.000000	0.000000	0.000000	0.000000	0.000000	237.500000	129.10000	84.050000	25.950000	86.000000	89.000000	0.000000
75%	187.750000	61.000000	3.00000	1.000000	12.000000	0.000000	0.000000	1.000000	0.000000	260.750000	141.75000	91.475000	29.375000	99.000000	103.000000	0.000000
max	250.000000	70.000000	4.00000	1.000000	30.000000	1.000000	1.000000	1.000000	1.000000	320.000000	180.90000	114.100000	41.700000	110.000000	163.000000	1.000000
```
# Input 3
```
#View first 10 rows

df.head()

#View last 10 rows

df.tail()
```
## Output 3
```
S. No	Gender	Age	Education	currentsmoker	Cigsperday	BPMeds	Prevalentstroke	PrevalentHyp	Diabetes	Totalcholestrol	SysBP	DiaBP	BMI	Heartrate	Glucose	TenYearCHD
0	1	Female	68	1	1	3	0	1	0	0	237	107.8	71.2	30.9	81	70	0
1	2	Female	58	4	1	1	0	0	0	0	268	113.2	94.7	26.8	108	58	0
2	3	Male	44	2	1	6	0	0	0	0	192	132.7	94.8	30.3	104	141	0
3	4	Male	37	4	1	18	0	0	0	0	250	132.3	74.4	25.8	89	120	0
4	5	Female	50	1	1	24	0	1	0	0	202	97.5	102.6	22.2	106	84	1


S. No	Gender	Age	Education	currentsmoker	Cigsperday	BPMeds	Prevalentstroke	PrevalentHyp	Diabetes	Totalcholestrol	SysBP	DiaBP	BMI	Heartrate	Glucose	TenYearCHD
245	246	Male	32	3	1	11	0	0	0	0	232	133.3	84.2	32.6	64	106	0
246	247	Female	49	3	1	27	1	0	0	0	185	136.5	85.4	22.3	94	58	0
247	248	Male	53	4	0	0	0	0	0	0	195	122.8	100.8	29.1	101	94	0
248	249	Male	62	1	1	27	0	0	0	0	246	142.6	80.0	25.9	96	123	0
249	250	Male	53	3	0	0	0	0	0	0	264	116.9	66.2	35.5	55	82	0
```
# Input 4
```
# Sorting and Grouping
df.sort_values('Education', ascending=True)
```
# Output 4
```
S. No	Gender	Age	Education	currentsmoker	Cigsperday	BPMeds	Prevalentstroke	PrevalentHyp	Diabetes	Totalcholestrol	SysBP	DiaBP	BMI	Heartrate	Glucose	TenYearCHD
0	1	Female	68	1	1	3	0	1	0	0	237	107.8	71.2	30.9	81	70	0
4	5	Female	50	1	1	24	0	1	0	0	202	97.5	102.6	22.2	106	84	1
6	7	Male	48	1	1	5	0	0	0	0	269	118.0	83.0	26.0	79	82	1
10	11	Male	53	1	0	0	1	0	1	0	248	138.9	85.1	27.3	58	92	0
13	14	Female	53	1	0	0	0	0	0	1	317	97.5	95.7	25.8	81	103	0
...	...	...	...	...	...	...	...	...	...	...	...	...	...	...	...	...	...
234	235	Male	31	4	0	0	0	0	1	0	201	143.1	73.5	20.2	69	99	0
232	233	Male	45	4	1	3	0	0	1	0	213	104.6	96.9	25.4	73	93	0
230	231	Female	64	4	1	26	0	0	0	0	289	129.6	87.3	18.6	101	82	0
247	248	Male	53	4	0	0	0	0	0	0	195	122.8	100.8	29.1	101	94	0
241	242	Female	70	4	1	27	1	0	0	0	204	131.7	73.4	32.9	87	92	0
250 rows × 17 columns
```
## Input 5
```
# Groupby functions
df.groupby('Education').mean(numeric_only=True)

df.groupby('Education').median(numeric_only=True)

df.groupby('Education').max(numeric_only=True)

df.groupby('Education').min(numeric_only=True)
```
## Output 5
```
S. No	Age	currentsmoker	Cigsperday	BPMeds	Prevalentstroke	PrevalentHyp	Diabetes	Totalcholestrol	SysBP	DiaBP	BMI	Heartrate	Glucose	TenYearCHD
Education															
1	118.254237	49.050847	0.508475	8.220339	0.169492	0.050847	0.186441	0.050847	240.949153	125.896610	83.930508	26.106780	83.813559	86.135593	0.203390
2	131.043478	50.246377	0.362319	4.985507	0.057971	0.028986	0.289855	0.130435	230.260870	130.650725	83.721739	25.805797	82.347826	90.028986	0.231884
3	127.246154	50.615385	0.523077	7.784615	0.092308	0.000000	0.261538	0.061538	234.400000	127.360000	81.956923	25.724615	85.923077	87.769231	0.169231
4	124.298246	50.368421	0.438596	5.912281	0.122807	0.017544	0.280702	0.070175	236.105263	133.959649	84.507018	27.703509	84.964912	87.789474	0.122807


S. No	Age	currentsmoker	Cigsperday	BPMeds	Prevalentstroke	PrevalentHyp	Diabetes	Totalcholestrol	SysBP	DiaBP	BMI	Heartrate	Glucose	TenYearCHD
Education															
1	126.0	50.0	1.0	3.0	0.0	0.0	0.0	0.0	247.0	127.2	83.3	26.3	84.0	86.0	0.0
2	135.0	52.0	0.0	0.0	0.0	0.0	0.0	0.0	229.0	130.8	84.5	25.0	81.0	90.0	0.0
3	122.0	53.0	1.0	3.0	0.0	0.0	0.0	0.0	234.0	125.2	81.6	24.5	88.0	93.0	0.0
4	129.0	51.0	0.0	0.0	0.0	0.0	0.0	0.0	235.0	134.1	85.0	27.2	89.0	85.0	0.0


S. No	Age	currentsmoker	Cigsperday	BPMeds	Prevalentstroke	PrevalentHyp	Diabetes	Totalcholestrol	SysBP	DiaBP	BMI	Heartrate	Glucose	TenYearCHD
Education															
1	249	70	1	30	1	1	1	1	317	156.7	111.6	37.0	110	129	1
2	245	69	1	28	1	1	1	1	312	174.0	108.6	36.4	110	154	1
3	250	70	1	30	1	0	1	1	320	180.9	114.1	35.5	109	141	1
4	248	70	1	30	1	1	1	1	299	175.6	107.0	41.7	110	163	1


S. No	Age	currentsmoker	Cigsperday	BPMeds	Prevalentstroke	PrevalentHyp	Diabetes	Totalcholestrol	SysBP	DiaBP	BMI	Heartrate	Glucose	TenYearCHD
Education															
1	1	30	0	0	0	0	0	0	120	85.0	55.6	16.0	57	45	0
2	3	30	0	0	0	0	0	0	144	85.0	61.7	16.0	55	45	0
3	18	30	0	0	0	0	0	0	126	85.0	58.9	16.0	55	45	0
4	2	31	0	0	0	0	0	0	150	87.7	57.1	18.0	55	45	0

```
## Input 6
```
# Calculate overall mean for all numeric columns
print("\nOverall mean for all numeric columns:")
print(df.mean(numeric_only=True))
```
## Output 6
```
Overall mean for all numeric columns:
S. No              125.5000
Age                 50.0880
Education            2.4800
currentsmoker        0.4560
Cigsperday           6.6880
BPMeds               0.1080
Prevalentstroke      0.0240
PrevalentHyp         0.2560
Diabetes             0.0800
Totalcholestrol    235.1920
SysBP              129.4276
DiaBP               83.4912
BMI                 26.2884
Heartrate           84.2200
Glucose             88.0120
TenYearCHD           0.1840
dtype: float64
```
## Input 7
```
# Rename a column
print("\nRenaming 'age' column to 'Age':")
df.rename(columns={'age': 'Age'}, inplace=True)
```
## Output 7
```
Renaming 'age' column to 'Age':
```
## Input 8
```
# Display updated columns
print("\nUpdated column names:")
print(df.columns)
```
## Output8
```
Updated column names:
Index(['S. No', 'Gender', 'Age', 'Education', 'currentsmoker', 'Cigsperday',
       'BPMeds', 'Prevalentstroke', 'PrevalentHyp', 'Diabetes',
       'Totalcholestrol', 'SysBP', 'DiaBP', 'BMI', 'Heartrate', 'Glucose',
       'TenYearCHD'],
      dtype='object')
```

## Result

The dataset was successfully cleaned and preprocessed. Data types were verified, missing values and duplicate values were identified, and statistics were generated. The data is now ready for further analysis such as EDA and regression modelling.
