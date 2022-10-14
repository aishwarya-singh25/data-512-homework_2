# data-512-homework_2

This repository holds the notebooks, datasets and results for the homework assignment 2 as a part of Data512 - Human-Centered Data Science Course. The objective of this assignment is to understand the concept of bias in data using wikipedia articles. Following datasets are used in the project:

#### Input Datasets:
* politicians_by_country.SEPT.2022.csv -
The Wikipedia Category "Politicians by nationality" was crawled to generate a list of Wikipedia article pages about politicians from a wide range of countries.
* population_by_country_2022.csv
This dataset is drawn from the world population data sheet published by the Population Reference Bureau.


### Notebook - datacleaning.ipynb

To generate the final data for the analysis, we use API:Info (https://www.mediawiki.org/wiki/API:Info) and ORES (https://www.mediawiki.org/wiki/ORES). API:Info is used to get the latest revision ID of the article page using the article title and link. The ORES api uses the last revision ID to generate the quality of the article. Both the apis are used to generate final data for analysis using the notebook Data512_HW2_datacleaning.ipynb. Following are the intermediate datasets generated from the notebook.

#### Intermediate Files

* lastrevid.csv - stores the last revision ID for article pages
* ores_preds.csv - stores the ores predicted scores for the pages
* wp_countries-no_match.txt - list of countries with no match of lastrevid found

#### Output Files

* wp_politicians_by_country.csv - file used for further data analysis

#### Important Considerations
1. Information of some contries could not be fetched, the list is stored in wp_countries-no_match.txt.
2. A few countries had quotes "" within the link which resulting in API not being able to fetch the data.
3. Certain countries had population 0, could be an error or could be really close to but slightly less than 1 million.
4. The countries with population with populaiton 0 resulted in inf during data analysis. These rows were removed.

### Notebook - DataAnalysis.ipynb
Using the final dataset generated from datacleaning.ipynb was used to analyse data. This notebook contains list of top 10 and bottom 10 artciles based on total per capita articles for that country and region. Same analysis is performed for only selected 'good quality' articles. 

## Research Implications
###### 1. What biases did you expect to find in the data (before you started working with it), and why?
Initially I expected to see the most-developed countries at the top of the total-per-capita-article list. This was an assumption that politicians in this country would be more popular across the globe. 
###### 2. What (potential) sources of bias did you discover in the course of your data processing and analysis?
There clearly is a selection bias. Looks like there is some information missing specially from the developed countries. Even when we consider the most populated countries like India and China, they showed up at the bottom of the list. There could be a bias based on the population or the language spoken in the country, as all articles were in english.

###### 3. What might your results suggest about (English) Wikipedia as a data source?
Wikipedia has a lot of information but cannot be used as the only data source while performing data analysis like these/ 

###### 4. Can you think of a realistic data science research situation where using these data (to train a model, perform a hypothesis-driven research, or make business decisions) might create biased or misleading results, due to the inherent gaps and limitations of the data?
Any data analysis or research that is trying to closely look at the number of political leaders in a country, or their popularity would get biased results as a good number of political figures and their information is missing from the list.
