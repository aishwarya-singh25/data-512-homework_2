# data-512-homework_2

This repository holds the notebooks, datasets and results for the homework assignment 2 as a part of Data512 - Human-Centered Data Science Course. The objective of this assignment is to understand the concept of bias in data using wikipedia articles. Following datasets are used in the project:

##### Input Datasets:
* politicians_by_country.SEPT.2022.csv -
The Wikipedia Category "Politicians by nationality" was crawled to generate a list of Wikipedia article pages about politicians from a wide range of countries.
* population_by_country_2022.csv
This dataset is drawn from the world population data sheet published by the Population Reference Bureau.


#### Notebook - datacleaning.ipynb

To generate the final data for the analysis, we use API:Info (https://www.mediawiki.org/wiki/API:Info) and ORES (https://www.mediawiki.org/wiki/ORES). API:Info is used to get the latest revision ID of the article page using the article title and link. The ORES api uses the last revision ID to generate the quality of the article. Both the apis are used to generate final data for analysis using the notebook Data512_HW2_datacleaning.ipynb. Following are the intermediate datasets generated from the notebook.

#### Intermediate Files



#### Notebook - DataAnalysis.ipynb



