# Subreddit Classification with Natural Language Processing
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
![alt text](https://github.com/micahluedtke/subreddit_classification/blob/master/pictures_of_slides/Subreddit%20Classification%20with%20Natural%20Language%20Processing%20(3).png "Logo Title Text 1")
##### Exploratory Data Analysis
My initial EDA was to read through some of the posts in both of the subreddits that I was planning on analyzing. After importing the data, I deteremined that many of the 60+ columns of information I had for each post was not relavent (columns like "user cake day" and "attachment file name" etc). I dropped these columns and saved a few potentially helpful columns ('author', 'created_utc', 'num_comments', 'permalink', 'score', 'title') and of course the two main targets: 'selftext' and 'subreddit'. 
<br>I created a correlation heatmap and a seaborn pairplot with the numeric variables to see if any additional parameters might be helpful while modeling. The only parameter with a strong correlation was the 'created_utc' at -.54, but from the pairplot it can be seen that this merely results from higher frequency of posts in the r/LanguageLearning subreddit (the sample size of the two subreddits was the same and pulled at the same time, but r/Linguistics has twice the range of 'created_utc'.)
![alt text](https://github.com/micahluedtke/subreddit_classification/blob/master/pictures_of_slides/Subreddit%20Classification%20with%20Natural%20Language%20Processing%20(4).png "Logo Title Text 1")
##### Model Building
I built four different models for the data. A logistic regression classifer and a multinomial Naïve Bayes classifer for the data after using a CountVectorizer and a logistic regression classifer and a multinomial Naïve Bayes classifer for the data after using a term frequency-inverse document frequency (TF-IDF). The combination of multinomial Naïve Bayes classifer and TF-IDF vectorizer was the most effective at classifying the reddit posts.
![alt text](https://github.com/micahluedtke/subreddit_classification/blob/master/pictures_of_slides/Subreddit%20Classification%20with%20Natural%20Language%20Processing%20(5).png "Logo Title Text 1")
![alt text](https://github.com/micahluedtke/subreddit_classification/blob/master/pictures_of_slides/Subreddit%20Classification%20with%20Natural%20Language%20Processing%20(6).png "Logo Title Text 1")
![alt text](https://github.com/micahluedtke/subreddit_classification/blob/master/pictures_of_slides/Subreddit%20Classification%20with%20Natural%20Language%20Processing%20(7).png "Logo Title Text 1")
![alt text](https://github.com/micahluedtke/subreddit_classification/blob/master/pictures_of_slides/Subreddit%20Classification%20with%20Natural%20Language%20Processing%20(8).png "Logo Title Text 1")
![alt text](https://github.com/micahluedtke/subreddit_classification/blob/master/pictures_of_slides/Subreddit%20Classification%20with%20Natural%20Language%20Processing%20(9).png "Logo Title Text 1")
##### BONUS: Constructed Languages
While exploring subreddits and considering which ones I would analyze, I also consider using r/conlangs which is a subreddit dedicated to constructed languages which are languages that were constructed by a single person or small group relatively quickly, rather than over time by natural languages development processes. 
After I was happy with my model, I took a sample from r/conlangs and ran it through my model to see if the discussion in r/conlangs was more similar to r/Linguistics or r/LanguageLearning. The posts were classified as r/Linguistics 65%-75% of the time.
![alt text](https://github.com/micahluedtke/subreddit_classification/blob/master/pictures_of_slides/Subreddit%20Classification%20with%20Natural%20Language%20Processing%20(10).png "Logo Title Text 1")
![alt text](https://github.com/micahluedtke/subreddit_classification/blob/master/pictures_of_slides/Subreddit%20Classification%20with%20Natural%20Language%20Processing%20(11).png "Logo Title Text 1")
