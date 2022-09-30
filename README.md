# women_in_data_datathon
Women in Data hosted a datathon highlighting on 
+ Equal Pay
+ Paid Family Leave
+ Education

We gravitated towards Paid Family Leave. In the last 5-10 years we have seen many companies revise paid leave policies for the better. Most companies have room for improvement but we wanted to analyze the progress made in companies, specifically large companies. 

# Contributors:
+ Monica Puerto (Lead) 
+ Elizabeth Connor 
+ Karolina Grodzińska
+ Anita Mohan

# Problem Statement

Does increasing paid leave have an effect/ contribute to :
+ Employee retention
+ Employee morale
+ Growth of a Company (# of Employees or Revenue)

# Methods
Our hackathon / datathon project on Paid Leave on Top US 50 Companies using NLP and data visualizations.
We created a novel dataset where we took the [Top 50 of the Top 500 Fortune Companies](https://www.zyxware.com/articles/4344/list-of-fortune-500-companies-and-their-websites) and collected the following information during the month of September 2022:

# Data Sources:

## large companies excel sheet
### sheet = 'main data'
+ Number of Employees from macrotrends.com
+ Sector from glassdoor.com
+ Revenue in Billions QTR 2 2022 from macrotrends.com
+ Median retention in years from Linkedin Premium
+ Latest Paid Maternity leave in Weeks*
+ Latest Paid Paternity leave in Weeks*
+ Last Policy Change Date on Paid Leave**
+ [Avg Polarity / Sentiment Score from Webscraped Reviews *before* Policy Changed](https://github.com/monipip3/women_in_data_datathon/blob/main/sentiment_analysis.ipynb)***
+ [Avg Polarity / Sentiment Score from Webscraped Reviews *after* Policy Changed](https://github.com/monipip3/women_in_data_datathon/blob/main/sentiment_analysis.ipynb)***
+ [Avg Polarity / Sentiment Score pct change from Webscraped Reviews after Policy Changed](https://github.com/monipip3/women_in_data_datathon/blob/main/sentiment_analysis.ipynb)***

### sheet = 'paid review links'

+ In Glassdoor there is a section under Benefits solely dedicated to Paid and Maternity Leave. We collected the links for the Top 50 companies we wanted to analyze. We then looped through the list and scraped the reviews along with some metadata about the review. [See this notebook for the code](https://github.com/monipip3/women_in_data_datathon/blob/main/Scraping_Glassdoor_Company_Reviews_parental_leave_only.ipynb).

## NLP / Sentimental Analysis

After webscraping the reviews which ended up being around ~4K of them. We applied sentiment analysis via 2 methods.

### Text Blob Package

Text Blob

### Google's T5 Finetuned on Emotion


## Tableau Dashboard


## Video Submission



## Future Work

Please feel free to fork this data and further analayze data! Also feel free to add to the sheet called Paid leave review links and webscrape more Fortune 500 companies!

