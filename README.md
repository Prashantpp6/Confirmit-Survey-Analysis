# Automated Analysis of Confirmit Surveys

This code takes raw data and layout xlsx files generated from the Confirmit platform and outputs an analysis of the survey data.

* Buckets are automatically added for the 5-, 7-, and 11-scale likert questions as well as 100-scale slider questions
* The entire analysis can be outputted as a csv file 


## Requirements

* Python 3
* pandas


## Instructions

Arguments:

1. `data_path`: path to the raw data xlsx file
2. `layout_path`: path to the raw layout xlsx file
3. `col_name`: name of the column used for cutting the data
4. `output_path`: output path as csv

Command line usage:

```
python confirmit_analysis.py data_path layout_path col_name output_path
```

Jupyter notebook usage:

```python
from confirmit_analysis import DataClean, Analysis

dc = DataClean(data_path, layout_path)
af = Analysis(dc.data, dc.layout, col_name)
af.analysis_csv(output_path) # outputs the entire analysis as a csv file
af.questionlist[col] # shows the analysis for a specific column inline
```


## Screenshots

Here's an example of running the code in the Jupyter notebook:

![example](https://github.com/Prashantpp6/Confirmit-Survey-Analysis/blob/master/datacleaning.png)


DataClean lists existing 5-, 7-, or 11-scale grid or 100-scale slider questions for which buckets have been created.

Here's a preview of the csv output, which showcases the automatically bucketed analysis:

![csv_screenshot](https://github.com/Prashantpp6/Confirmit-Survey-Analysis/blob/master/preview%20bucketed%20analysis.png)

