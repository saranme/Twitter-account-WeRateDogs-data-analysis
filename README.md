# WeRateDogs Twitter account data analysis

## Intro
This is a **student project** from the **Udacity Nanodegree "Data Analyst"**.
The goal of this project is to gather, assess, and clean data. Then act on it through analysis, visualization and/or modeling.

#### Documents I received to explore the dataset:
- `twitter_archive_enhanced.csv` : contains basic tweet data for all 5000+ of their tweets, but not everything.
One column the archive does contain though: each tweet's text, which it is used to extract rating, dog name and stage.
The data has been extracted programmatically so there will be errors in rating, names and stages columns.
- Additional Data via the **Twitter API**: query Twitter's API to gather retweet count and favorite count.
- Image Predictions file: is a table full of image predictions (the top three only) alongside each tweet ID, image URL, and the image number that corresponded to the most confident prediction (numbered 1 to 4 since tweets can have up to four images).
This file has been created running every image in the WeRateDogs Twitter archive through a neural network that can classify breeds of dogs. The result is the table with the image predictions.

#### Concepts to understand better what I am doing through gathering, assessing, cleaning and analyzing:
##### Gathering data:
- Enhanced Twitter archive is downloaded manually.
- Image Predictions is downloaded programmatically (using Requests library and this [URL](https://d17h27t6h515a5.cloudfront.net/topher/2017/August/599fd2ad_image-predictions/image-predictions.tsv).
- Additional Data via the Twitter API. Queried the Twitter API for each tweet's JSON data using Python's Tweepy library and stored each tweet's entire set of JSON data in a file called tweet_json.txt file. Each tweet's JSON data was written to its own line. Then read this .txt file line by line into a pandas DataFrame with (at minimum) tweet ID, retweet count, and favorite count.

##### Assessing and Cleaning data:
- Assessed them visually and programmatically for quality and tidiness issues. They are documented in wrangle_act.ipynb.
- The cleaning is performed in wrangle_act.ipyng
##### Storing, Analyzing and Visualizing data:
- The clean dataframe(s) is stored in twitter_archive_master.csv
- Data analysis is done in wrangle_act.ipynb

## Main findings I got from my exploratory data analysis:
##### How reliable is this neural network?
- The first prediction is the most reliable, with 59%, followed by a large difference from
the other two predictions, with 13% and 6% respectively.
- No correlation is observed between number of images and dog prediction in the #1
prediction.
- What the neural network identifies as not a dog seems to be part of a common
scenario in the photos (e.g. patio or bow tie)

##### Learning about the dogs
- Each prediction shows a different ranking of breeds. However, they do share some
breeds: Labrador Retriever, Chihuahua, and Golden Retriever.
- The breeds that receive the most likes and retweets are not breeds or dogs. In this
case, the neural network identifies things.
- There is no recurring name. Ratings don't match the most named names, either.
- Twitter users only like the ratings between 11 and 14 out of 10.
- The double category of Doggo and puppo.

## My analsis:
- `wrangle_act.ipynb`exploration and data analysis.
- `wrangle_report.html`: report that describes my wrangling efforts.
- `act_report.html` (with act_report_img folder images): report that communicates the insights and displays the visualizations.
- `twitter_archive_master.csv`: file that is modified and stored as the new dataframe.
- `tweet-jason.txt`: file created from Twitter's API query.
