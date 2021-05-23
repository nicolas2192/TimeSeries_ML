# Time Series Forecasting

Being able to forecast your data accuratelly is an essential skill nowdays. Predicting the trend is not enough, you need to be able to pinpoint future values with a very low margin error. This repo addresses this situation, we will see how using a complex model instead of a simple linear regression we can improve our predictions without imparing the processing time significantly.

### :boom: Let's grow some trees

The idea behind this implementation was to improve an already existing predictive model. The original model run ok with datasets that dont exhibit any seasonality but failed to predict seasonal time series. This problem was solved implementing a new Random Forest Regressor model.
Here we can see how the new model (green line) better fits to the data.

<img align="center" width="1027" height="805" src="readme/lr_rf_comparison.png">

**Feature engineering, is it worth it?**

Short answer, yes. It's clear that complex algorithms will perform better than simpler ones (some exceptions apply), however, one must not forget that feature engineering is the tool that give us a performance edge. Data science is not just about using the most convoluted algorithms, it is about understandig the data and spotting not-so-obvious patterns to create new features that will improve any model's performance. Next two charts set side by side the same Random Forest model's performace with and without feature engineering.

<img align="center" width="1033" height="831" src="readme/rf_rf_comparison.png">

This case's feature engineering was simple, but, got the job done:

- last day and first day (of the month).
- weekdays, values ranging from 0 to 6 where 0 is Monday and 6 Sunday
- day of the month, values ranging from 1 to 31.

<img align="center" width="591" height="298" src="readme/feature_engineering.png">

After running the model for 4 different datasets and computing the R2 error metric we got the following results:

Notice that our Random Forest outperforms the Simple Linear Regression in the last 3 examples, however, when the data behaves like a line you are better off using a Simple Linear Regression.

<img align="center" width="279" height="143" src="readme/r2_acc.png">

Check every dataset's performance either by downloading and running the notebook or just by heading to the charts folder and checking it there.


### :computer: Technology stack
Written in python 3. Main modules:

**Pandas** -> Data manipulation, cleansing and analysis.

**Scikit-Learn** -> Forecasting.

**Matplotlib** -> Charting and visualization.


### :information_source: Data info
There are 4 different datasets in the data folder (t1, t2, t3 and t4). Each one is comprised by two columns; date and value.

<img align="center" width="152" height="164" src="readme/dataset_example.png">

<img align="center" width="1152" height="432" src="charts/t3_raw.png">

## :love_letter: Contact info
Doubts? Advice?  Drop me a line! :smirk:

