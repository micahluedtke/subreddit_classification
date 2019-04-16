# Project 3: Subreddit Classification with Natural Language Processing
## Linguistics vs. Language Learning

### Excutive Summary
For this project, I attempted to use natural language processing techniques and classifer models to predict whether a reddit post came from two similar subreddits (Linguistics and Language Learning). 

#### Problem: 
**Quantitative:** Can word frequency and usage be used to predict where a reddit post came from the r/Linguistics or the r/LanguageLearning subreddits?
<br>**Qualitative:** What insights can we gain from the difference in keywords between two different groups studying language in different ways?

#### Process:
##### Web Scraping and Data Cleaning
I started by exploring different subreddits and trying to get a feel for their content. Ultimately, I zeroed in on r/LanguageLearning and r/Linguistics because of my personal interest in them and the interesting question they purposed: how do people who study the stucture of language and people who learn to speak foriegn languages different in their approach?
<br>I did all of my scraping in the scrape.ipynb Jupyter Notebook and created a funciton that would pull a specificed number of posts from two subreddits, merge them into one pandas dataframe and save them as a .csv that was timestamped. This was crucial because the posts are constantly changing, so this gave me a record of when the data was collected and it preserved it for when I returned to my modeling.
##### Exploratory Data Analysis
My initial EDA was to read through some of the posts in both of the subreddits that I was planning on analyzing. After importing the data, I deteremined that many of the 60+ columns of information I had for each post was not relavent (columns like "user cake day" and "attachment file name" etc). I dropped these columns and saved a few potentially helpful columns ('author', 'created_utc', 'num_comments', 'permalink', 'score', 'title') and of course the two main targets: 'selftext' and 'subreddit'.
<br>I created 
##### Model Building
##### BONUS: Constructed Languages

