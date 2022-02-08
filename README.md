# Social Media Scraping
Scraping historical tweets with Twitter API v2

![image](https://user-images.githubusercontent.com/38474985/153022562-679473f9-c5f3-46a2-869a-e2c427b2f293.png)

I conducted a research study of the interaction and perception of different stakeholders of the education system with the international assesment PISA (Programme for International Student Assessment). More precisely, I set out to discover the answers to these research questions:  

*Research Question 1.*  How is the discussion around the PISA examination represented in Twitter discourse and how did the discourse evolve over time ?
*Research Question 2.* What is the demographic profile of the participants to this online conversation ?  

To answer these questions, I turned to social media, where all categories of stakeholders voice opinions (students, teachers, parents, institutions etc) and where information is freely available.

I needed to scrape **all historical tweets** while filtering for specific keywords I identified as being relevant.  

The first tool I tested was **snscrape**. I wrote another article on <a href='https://mihaelagrigore.medium.com/scraping-historical-tweets-without-a-twitter-developer-account-79a2c61f76ab'>how to scrape historical tweets using without the need of a Twitter developer account using snscrape</a> and <a href='https://github.com/mihaelagrigore/Scraping-historical-tweets-without-Twitter-API'>this is its GitHub repo</a>.

Snscrape was easy to get started with (easy to use, good documentation, plenty of examples), but after performing the data collection I thought I go too few tweets. I can't day for sure how many tweets is a right amount, but I reasoned as follows: if I only get 5.000 tweets for 2012 related to PISA tests results, then it means that at most 5.000 people tweeted globally using my keywords . This seems like a low number, given that PISA is the most widely known and discussed of all the ILSAs (International Large Scale Assessments). To get an idea of its magnitude: in 2018 there was 79 participating countries.  

Starting from this reasoning and considering that I found no resource that would estimate the percentage of results collected by snscrape from the full archive of historical tweets, I decided to look into Twitter's new <a href='https://techcrunch.com/2021/01/26/twitters-new-api-platform-now-opened-to-academic-researchers'>Academic Research product track</a>.

This repository contains one Jupyter Notebook where you can find the sections below. If those are something you're interested in, explore the notebook. Also, feel free to get in touch if you have specific questions about this work / need help with your own (research) project.

1. [Getting started with Academic Research product track](#1.-Getting-started-with-Academic-Research-product-track)
2. [Pagination of results for historical tweets collection](#2.-Pagination-of-results-for-historical-tweets-collection)
3. [Tweet fields](#3.-Tweet-fields)
4. [Scraping rate limits](#4.-Scraping-rate-limits)
5. [Retweeted tweets and truncation](#5.-Retweeted-tweets-and-truncation)
6. [Twitter API v2 Expansions](#6.-Twitter-API-v2-Expansions)
7. [Mass collection of historical tweets for multiple keywords](#7.-Mass-collection-of-historical-tweets-for-multiple-keywords)
8. [Load tweets from the CSV file into pandas DataFrame for analysis](#8.-Load-tweets-from-the-CSV-file-into-pandas-DataFrame-for-analysis)
9. [Removing duplicate tweets](#9.-Removing-duplicate-tweets)
10. [User location from Twitter data](#10.-User-location-from-Twitter-data)
11. [Tweets preliminary data analysis](#11.-Tweets-preliminary-data-analysis)
12. [What's next ? Sentiment analysis](#12.-What's-next-?)  

### Libraries needed: 
```
requests
nltk
seaborn
geotext
geograpy3
pycountry
CountryInfo
```
