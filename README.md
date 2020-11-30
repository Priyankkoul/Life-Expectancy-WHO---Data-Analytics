# Life-Expectancy-WHO---Data-Analytics

Life Expectancy Prediction is a statistical analysis on factors influencing life expectancy.

[data-analytics-project (1).ipynb](https://github.com/Priyankkoul/Life-Expectancy-WHO---Data-Analytics/blob/master/data-analytics-project%20(1).ipynb) - visualization ( done in R )

[data-analytics-project (2).ipynb](https://github.com/Priyankkoul/Life-Expectancy-WHO---Data-Analytics/blob/master/data-analytics-project%20(1).ipynb) - model ( done in python3 )


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
