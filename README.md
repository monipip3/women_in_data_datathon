# women_in_data_datathon
Women in Data hosted a 2022 datathon highlighting  
+ Equal Pay
+ Paid Family Leave
+ Education

We gravitated towards Paid Family Leave. In the last 5-10 years we have seen many companies revise paid leave policies for the better. Most companies have room for improvement, but we wanted to analyze the initial progress made in companies in order to encourage others to follow suit. We began by using the Top 50 companies as listed by Fortune 500. 

# Contributors:
+ Monica Puerto (Lead) 
+ Elizabeth Connor 
+ Karolina Grodzińska
+ Anita Mohan

# Problem Statement

Does increasing paid leave have an effect/contribute to:
+ Employee retention
+ Employee morale

# Methods
Our hackathon / datathon project on Paid Leave on Top US 50 Companies using NLP and data visualizations.
We created a novel dataset where we took the [Top 50 of the Top 500 Fortune Companies](https://www.zyxware.com/articles/4344/list-of-fortune-500-companies-and-their-websites) and collected the following information during the month of September 2022:

# Data Sources:

## [large companies excel sheet](https://github.com/monipip3/women_in_data_datathon/blob/main/data/large_companies.xlsx)
### sheet = 'main data'
+ Number of Employees *from macrotrends.com*
+ Sector *from glassdoor.com*
+ Revenue in Billions QTR 2 2022 *from macrotrends.com*
+ Median retention in years from *Linkedin Premium*
+ Latest Paid Maternity leave in Weeks *extraced first from press release then supplemented by Fairygodboss.com*
+ Latest Paid Paternity leave in Weeks *extraced first from press release then supplemented by Fairygodboss.com*
+ Last Policy Change Date on Paid Leave *extracted from press release*
+ [Avg Polarity / Sentiment Score from Webscraped Reviews *before* Policy Changed](https://github.com/monipip3/women_in_data_datathon/blob/main/sentiment_analysis.ipynb) 
*created a flag if this review was before the date of policy change in the press release*
+ [Avg Polarity / Sentiment Score from Webscraped Reviews *after* Policy Changed](https://github.com/monipip3/women_in_data_datathon/blob/main/sentiment_analysis.ipynb)
*created a flag if this review was before the date of policy change in the press release*
+ [Avg Polarity / Sentiment Score pct change from Webscraped Reviews after Policy Changed](https://github.com/monipip3/women_in_data_datathon/blob/main/sentiment_analysis.ipynb) *calculation done in Tableau*

### sheet = 'paid review links'

+ In Glassdoor there is a section under Benefits solely dedicated to Paid and Maternity Leave. 

<img src="https://github.com/monipip3/women_in_data_datathon/blob/main/img/GLASSDOOR.png" width="600" />

We collected the links for the Top 50 companies we wanted to analyze. We then looped through the list and scraped the reviews along with some metadata about the review. [See this notebook for the code](https://github.com/monipip3/women_in_data_datathon/blob/main/Scraping_Glassdoor_Company_Reviews_parental_leave_only.ipynb). If you would like to add more companies from the Top Fortune 500 Companies list to the [reviews dataset we compiled](https://github.com/monipip3/women_in_data_datathon/blob/main/data/reviews_all_companies.pkl) please fork our repo and do so!

## NLP / Sentimental Analysis

After webscraping via the Python package Beautiful Soup, the reviews which ended up being around ~5K of them. 

<img src="https://github.com/monipip3/women_in_data_datathon/blob/main/img/WEBSCRAPING.png" width="600" />

We tweaked code from the [Bullet Byte Blog](https://bulletbyte.weebly.com/tech/how-to-scrape-a-companys-glassdoor-reviews-using-python). We idenitifed the Parental Leave section of each Fortune 50 Company and looped through each url and extracted the reviews. See that [webscraping code here](https://github.com/monipip3/women_in_data_datathon/blob/main/Scraping_Glassdoor_Company_Reviews_parental_leave_only.ipynb).

We applied sentiment analysis via 2 methods : 

### Text Blob Package

Text Blob is a rule based sentiment Python package where each word receives a score and then the whole text gets an average score called polarity that ranges from -1 to 1. With -1 being the most negative , 0 being neutral, and 1 being the most positive.

<img src="https://github.com/monipip3/women_in_data_datathon/blob/main/img/TEXTBLOB.png" width="600" />

### Google's T5 Finetuned on Emotion

A transformer model from Google called T5 but we ended up using text blob because it had a better measure of neutral review. It idenitief six emotions: sadness, joy, love, anger, fear, and suprise. However we found that a good portion of the reviews were neutral. 


<img src="https://github.com/monipip3/women_in_data_datathon/blob/main/img/TRANSFORMERMODEL.png" width="600" />

When grouping the emotions identified by the transformer model, we saw a good chunk of these emotions were classified as neutral by Text Blob which we agreed upon human review.

<img src="https://github.com/monipip3/women_in_data_datathon/blob/main/img/emotions.png" width="600" />

## Tableau Dashboard

<img src="https://github.com/monipip3/women_in_data_datathon/blob/main/img/tableau.png" width="600" />

We created a [story dashboard](https://public.tableau.com/app/profile/karolina.grodzinska/viz/WomeninDataDatathon/Dashboard) where you can interact with Glassdoor ratings over time for a particular company and assess how the policy updates affected the review score polarity. 


## Video Submission

https://youtu.be/2IFthhdfaTQ

## Future Work

This work has the potential to leave a lasting impact on the future of American Paid Leave policies. As more companies update their policies, we now have the ability to monitor employee retention improvement as time continues. 
Retention was captured from Linkedin Premium as of September 2022, but Linkedin calculates a cumulative median retention, the proper way to analyze is retention before and after similarily the way we calculated sentiment before and after the policy change to capture employee morale. 
**As seen on our dashboard 86% companies with a policy changed had a median sentiment increase of 2.6% , and over half of those companies had a 10% increase in sentiment.**
Furthermore, this dataset can be used to monitor company growth (# of Employees or Revenue) following Paid Leave policy updates. We hope you will use the trend analysis (and add to it!) to advocate for improved Paid Leave policies at your company. 

Please feel free to fork this data and further analayze data! Also feel free to add to the sheet called Paid leave review links and webscrape more Fortune 500 companies!

