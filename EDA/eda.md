# What is EDA
Exploratory data analysis (EDA) involves using graphics and visualizations to explore and analyze a dataset.
- EDA can be used for data cleaning
- Subgroup analyses
- for understanding your data better
- With EDA, you can find anomalies in your data, such as outliers or unusual observations
- uncover patterns
- understand potential relationships among variables
- generate interesting questions or hypotheses that you can test later using more formal statistical methods
- the distribution of variables in your dataset. That is, what is the shape of your data? Is the distribution normal? Does it have a fat tail? Is it skewed? Is it bimodal?
- whether or not your data have outliers or unusual points. This may indicate data quality issues or lead to interesting insights.
# Data Exploration
It often gives us the first glance at what is important in our data and what is garbage.

Data Exploration consists of the following parts:

## 1. Univariate exploration - exploring one variable at a time:
- Explanatory variables (variables we will use for modeling)
- Target variable (if applicable)

## 2. Multivariate exploration - exploring more than one variable at the same time:
- Manual – using domain knowledge
- Automatical – using Math

## Outlier Detection
Another important part of EDA and data preparation is the Outlier Detection. Sometimes, we have to deal with observations that are "extreme". Left ignored, these extremes can interfere with our model so it is important to address them at the outset.

### We have two main types of outliers:

- Univariate: we are looking at one variable at a time
- Multivariate: even though there are no univariate outliers, we can spot some extreme values if we look at the values of multiple variables at the same time.

There are a lot of reasons why outliers occur:

- Data Entry Errors – e.g. people make mistakes when filling in a survey.
- Measurement Errors – e.g. a device recording various measurements can be faulty.
- Experimental Errors – we can make a mistake when experimenting.
- Intentional Outliers – people can make "mistakes" intentionally, for example, in a loan application.
- Sampling Errors – e.g. we might take a sample which is too small.
- Natural Outliers – e.g. there might be a lot of snow one year and no snow in the following one.

### What is the Impact of Outliers on a Dataset?
Outliers can drastically change the results of data science projects. There are numerous impacts of outliers in a data set:

They increase the error variance, therefore, reducing the power of statistical tests.
They can bias or influence estimates that may be of substantive interest.
They can also impact the basic assumption of a regression, and other statistical model assumptions.

## How to Detect Outliers?
In this section, we are going to present the most commonly used techniques of the outlier detection, which are:

- Statistical tests
- Distance-based approaches
- Density-based approaches
- Visualization

# Visualization Tools

- [Matplotlib](/EDA/Matplotlib.ipynb),
- [Seaborn](/EDA/Seaborn.ipynb)
- [Plotly](/EDA/Plotly.ipynb)

# data wrangling


It is worth mentioning that the EDA process invariably includes tasks to clean and transform the data. The combination of cleaning and transforming data is known as data wrangling.

## Data Wrangling in Python
The Pandas framework of Python is used to execute the steps involved in data wrangling; steps such as sorting, filtering and grouping data.

Data wrangling in Python deals with the below functionalities:

### 1. Data exploration:
 In this process, the data is studied, analyzed and understood by visualizing representations of data.

### 2. Dealing with missing values: 
Most datasets have a vast amount of missing values, NaN, that need to be taken care of by replacing them with mean, or mode, or simply by dropping the row with a NaN value.
### 3. Reshaping data:
 In this process, data is manipulated according to the requirements, where new data can be added or pre-existing data can be modified.
### 4. Filtering data
Sometimes datasets are comprised of unwanted rows or columns which need to be removed or filtered
### 4. Other:
 By this point, you should have an efficient dataset that can be used for a required purpose like data analysis, machine learning, data visualization, model training etc.






