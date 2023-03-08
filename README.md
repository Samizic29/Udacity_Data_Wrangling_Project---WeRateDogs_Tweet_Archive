# Data Wrangling: WeRateDogs Tweet Archive

## Dataset
The dataset wrangled is the tweet archive of Twitter user [@dog_rates](https://twitter.com/dog_rates), also known as [WeRateDogs](https://en.wikipedia.org/wiki/WeRateDogs). **WeRateDogs** is a Twitter account that rates people's dogs with a humorous comment about the dog. These ratings almost always have a denominator of 10. 

They are three datasets:
1. `Twitter Archive Enhanced`: This dataset was provided by Udacity for download as an csv file. The WeRateDogs Twitter archive contains basic tweet data (tweet id, timestamp, source, rating, name, dog stage) for 2356 of their tweets.
2. `Image Predictions`: This dataset is present in each tweet according to a neural network. It is hosted on Udacity's servers and was downloaded programmatically using the Requests library. It's in a tsv file. This is about image predictions (the top three only) alongside each tweet ID, image URL, and the image number that corresponded to the most confident prediction (numbered 1 to 4 since tweets can have up to four images).
3. `Additional Data via the Twitter Api`: In this dataset, retweet count and favourite count was extracted from `twitter_archive_enhanced` using Tweepy library via Twitter Api (tweet_json.txt).

## Data Wrangling

In this section, all the three pieces of data were gathered, accessed and cleaned for analysis.

### Assessment
In this section, eight (8) quality issues and two (2) tidiness issues were detected using both visual and programmatic assessment to assess the data.

### Quality issues

The eight (8) quality issues are:

1. tweets archive table - Remove all retweets.
2. tweets archive table - drop in reply to status id, in reply to user id, retweeted status id, retweeted status user id, retweeted status timestamp column (missing data).
3. Extract url content from source column.
4. Extract text url content form the text column.
5. Erroneous datatype assigned to timestamp column.
6. Extract data and time from timestamp column.
7. Inaccurate rating denominator (not exactly 10 - greater/less than).
8. Invalid names in the name column.

### Tidiness issues

The two (2) tidiness issues are:

1. tweets archive table - Clubbing 4 dog stage columns into 1 column
2. Merged all the three (3) datasets into one (1)

## Summary of Findings
After data wrangling and analyzing:

- `tweet id`: 744234799360020481 has the most retweet_count of 79515
- `tweet id`: 666102155909144576 has the least retweet_count of 16
- `tweet id`: 822872901745569793 has the most favorite count of 132810
- `tweet id`: 666102155909144576 has the least favorite count of 81
- `tweet ids` have more rating over 1 (1161) compared to under 1 (833).
- `dog stage`: Pupper has the highest tweets (tweet id) while Floofer has the lowest.

## Conclusion
The main goal of this project is data wrangling. Further analysis and visualization can be carried out on this dataset.
