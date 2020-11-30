# Life-Expectancy-WHO---Data-Analytics

Life Expectancy Prediction is a statistical analysis on factors influencing life expectancy.

[Team Pickle-Stage1 (R).ipynb](https://github.com/Priyankkoul/Life-Expectancy-WHO---Data-Analytics/blob/master/Team%20Pickle-Stage1%20(R).ipynb) - visualization ( done in R )

[Team Pickle-Stage2 (Python).ipynb](https://github.com/Priyankkoul/Life-Expectancy-WHO---Data-Analytics/blob/master/Team%20Pickle-Stage2%20(Python).ipynb) - model and testing( done in python3 )


## Dataset used

The Global Health Observatory (GHO) data repository under World Health Organization (WHO) keeps track of the health status as well as many other related factors for all countries The datasets are made available to public for the purpose of health data analysis. The dataset related to life expectancy, health factors for 193 countries has been collected from the same WHO data repository website and its corresponding economic data was collected from United Nation website. In this project we have considered data from year 2000-2015 for 193 countries for analysis. The individual data files have been merged together into a single dataset.

To download the final compiled dataset, click [here](https://drive.google.com/file/d/17ucLgjgEdqvsWndiNiQji4xKyBKqYVwY/view?usp=sharing).

## Required Installations

The project is made in Jupyter notebook environment. It would be a good choice to use [
Google Colab](https://colab.research.google.com/) as it provides  a Jupyter notebook environment that runs entirely in the cloud and most importantly, it does not require a setup. 

If you prefer otherwise,

To setup jupyter notebook on your system
```bash
pip3 install notebook
```


Use the package manager [pip](https://pip.pypa.io/en/stable/) to 
install the required packages.

```bash
pip3 install numpy
pip3 install pandas
pip3 install seaborn
pip3 install matplotlib
pip3 install scipy
pip3 install scikit-learn
```
To start Jupyter notebook environment

```bash
jupyter notebook
```
## Reproduce Results
All code blocks must be run in sequential manner to obtain the desired results.

For visualizations, [data-analytics-project (1).ipynb](https://github.com/Priyankkoul/Life-Expectancy-WHO---Data-Analytics/blob/master/data-analytics-project%20(1).ipynb)

For building the model from scratch, [data-analytics-project (2).ipynb](https://github.com/Priyankkoul/Life-Expectancy-WHO---Data-Analytics/blob/master/data-analytics-project%20(1).ipynb)

## Components and Parameter Settings
General Overview of the columns of the final compiled dataset
```
 #   Column                           Non-Null Count  Dtype  
---  ------                           --------------  -----  
 0   Country                          2938 non-null   object 
 1   Year                             2938 non-null   int64  
 2   Status                           2938 non-null   object 
 3   Life expectancy                  2928 non-null   float64
 4   Adult Mortality                  2928 non-null   float64
 5   infant deaths                    2938 non-null   int64  
 6   Alcohol                          2744 non-null   float64
 7   percentage expenditure           2938 non-null   float64
 8   Hepatitis B                      2385 non-null   float64
 9   Measles                          2938 non-null   int64  
 10  BMI                              2904 non-null   float64
 11  under-five deaths                2938 non-null   int64  
 12  Polio                            2919 non-null   float64
 13  Total expenditure                2712 non-null   float64
 14  Diphtheria                       2919 non-null   float64
 15  HIV/AIDS                         2938 non-null   float64
 16  GDP                              2490 non-null   float64
 17  Population                       2286 non-null   float64
 18  thinness  1-19 years             2904 non-null   float64
 19  thinness 5-9 years               2904 non-null   float64
 20  Income composition of resources  2771 non-null   float64
 21  Schooling                        2775 non-null   float64
```
Info about the columns
```
 	life_expectancy adult_mortality infant_deaths 	alcohol 	percentage_expenditure 	hepatitis_b 	measles 	bmi 		under-five_deaths 	polio 		total_expenditure 	diphtheria 	hiv/aids 	gdp 		population 	thinness_10-19_years 	thinness_5-9_years 	income_composition_of_resources 	schooling
count 	2928.000000 	2928.000000 	2938.000000 	2744.000000 	2938.000000 		2385.000000 	2938.000000 	2904.000000 	2938.000000 		2919.000000 	2712.00000 		2919.000000 	2938.000000 	2490.000000 	2.286000e+03 	2904.000000 		2904.000000 		2771.000000 				2775.000000
mean 	69.224932 	164.796448 	30.303948 	4.602861 	738.251295 		80.940461 	2419.592240 	38.321247 	42.035739 		82.550188 	5.93819 		82.324084 	1.742103 	7483.158469 	1.275338e+07 	4.839704 		4.870317 		0.627551 				11.992793
std 	9.523867 	124.292079 	117.926501 	4.052413 	1987.914858 		25.070016 	11467.272489 	20.044034 	160.445548	 	23.428046 	2.49832 		23.716912 	5.077785 	14270.169342 	6.101210e+07 	4.420195 		4.508882 		0.210904 				3.358920	
min 	36.300000 	1.000000 	0.000000 	0.010000 	0.000000 		1.000000 	0.000000 	1.000000 	0.000000 		3.000000 	0.37000 		2.000000 	0.100000 	1.681350 	3.400000e+01 	0.100000 		0.100000 		0.000000 				0.000000
25% 	63.100000 	74.000000 	0.000000 	0.877500 	4.685343 		77.000000 	0.000000 	19.300000 	0.000000 		78.000000 	4.26000 		78.000000 	0.100000 	463.935626 	1.957932e+05 	1.600000 		1.500000 		0.493000 				10.100000
50% 	72.100000 	144.000000 	3.000000 	3.755000 	64.912906 		92.000000 	17.000000 	43.500000 	4.000000 		93.000000 	5.75500 		93.000000 	0.100000 	1766.947595 	1.386542e+06 	3.300000 		3.300000 		0.677000 				12.300000
75% 	75.700000 	228.000000 	22.000000 	7.702500 	441.534144 		97.000000 	360.250000 	56.200000 	28.000000 		97.000000 	7.49250 		97.000000 	0.800000 	5910.806335 	7.420359e+06 	7.200000 		7.200000 		0.779000 				14.300000
max 	89.000000 	723.000000 	1800.000000 	17.870000 	19479.911610 		99.000000 	212183.000000 	87.300000 	2500.000000 		99.000000 	17.60000 		99.000000 	50.600000 	119172.741800 	1.293859e+09 	27.700000 		28.600000 		0.948000 				20.700000
```
Null value column wise
```
[iloc = 3] life_expectancy has 10 null values: 0.34% null
[iloc = 4] adult_mortality has 155 null values: 5.28% null
[iloc = 5] infant_deaths has 848 null values: 28.86% null
[iloc = 6] alcohol has 194 null values: 6.6% null
[iloc = 8] hepatitis_b has 553 null values: 18.82% null
[iloc = 10] bmi has 1456 null values: 49.56% null
[iloc = 11] under-five_deaths has 785 null values: 26.72% null
[iloc = 12] polio has 19 null values: 0.65% null
[iloc = 13] total_expenditure has 226 null values: 7.69% null
[iloc = 14] diphtheria has 19 null values: 0.65% null
[iloc = 16] gdp has 448 null values: 15.25% null
[iloc = 17] population has 652 null values: 22.19% null
[iloc = 18] thinness_10-19_years has 34 null values: 1.16% null
[iloc = 19] thinness_5-9_years has 34 null values: 1.16% null
[iloc = 20] income_composition_of_resources has 167 null values: 5.68% null
[iloc = 21] schooling has 163 null values: 5.55% null
Out of 22 total columns, 16 contain null values; 72.73% columns contain null values.
```
Outlier Information of all columns
```
---------------life_expectancy---------------
Number of outliers: 17
Percent of data that is outlier: 0.58%
---------------adult_mortality---------------
Number of outliers: 97
Percent of data that is outlier: 3.3%
---------------infant_deaths---------------
Number of outliers: 135
Percent of data that is outlier: 4.59%
---------------alcohol---------------
Number of outliers: 3
Percent of data that is outlier: 0.1%
---------------percentage_expenditure---------------
Number of outliers: 389
Percent of data that is outlier: 13.24%
---------------hepatitis_b---------------
Number of outliers: 222
Percent of data that is outlier: 7.56%
---------------measles---------------
Number of outliers: 542
Percent of data that is outlier: 18.45%
---------------under-five_deaths---------------
Number of outliers: 142
Percent of data that is outlier: 4.83%
---------------polio---------------
Number of outliers: 279
Percent of data that is outlier: 9.5%
---------------total_expenditure---------------
Number of outliers: 51
Percent of data that is outlier: 1.74%
---------------diphtheria---------------
Number of outliers: 298
Percent of data that is outlier: 10.14%
---------------hiv/aids---------------
Number of outliers: 542
Percent of data that is outlier: 18.45%
---------------gdp---------------
Number of outliers: 300
Percent of data that is outlier: 10.21%
---------------population---------------
Number of outliers: 203
Percent of data that is outlier: 6.91%
---------------thinness_10-19_years---------------
Number of outliers: 100
Percent of data that is outlier: 3.4%
---------------thinness_5-9_years---------------
Number of outliers: 99
Percent of data that is outlier: 3.37%
---------------income_composition_of_resources---------------
Number of outliers: 130
Percent of data that is outlier: 4.42%
---------------schooling---------------
Number of outliers: 77
Percent of data that is outlier: 2.62%
```
To vary the training and test dataset split change '0.2'
```python3
X_train, X_test, y_train, y_test = train_test_split(X,y,test_size = 0.2, random_state=42)

```

## Authors
* [Priyank Koul](https://github.com/Priyankkoul)
* [Arif Sidiq Wani](https://github.com/wanixarif)
* [Shevgoor Adithya Kamath](https://github.com/ShevgoorAdithyaKamath)
* [Ashutosh Rout]()

## Contributions
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

## License
[MIT](https://choosealicense.com/licenses/mit/)
