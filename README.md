# DAND-Udacity-5

In this project, heterogeneous file resources and types were gathered, assessed and cleaned. And then stored as a one, ready-to-analyze master csv file, After that, some analysis was performed on that master cleaned csv file. The following is a summary of each phase:

## Gather
Data were gathered from three resources:

The first one was given as a csv file, namely twitter-archive-enhanced.csv, which was provided by WeRateDogs twitter account to Udacity and then to us. Then, the data was imported as a pandas dataframe twitter-archive.
The second one was programmatically fetched from the URL https://d17h27t6h515a5.cloudfront.net/topher/2017/August/599fd2ad_image-predictions/image-predictions.tsv with which the response has been processed and saved into a tsv file, namely image-predictions.tsv. Then, the data was imported as a pandas dataframe image-predictions.
The third one was through Twitter API, we fetched the data of those tweets we have and then saved them as a JSON file with UTF-8 encoding, namely tweet-json.txt, Then, the data was extracted as a pandas dataframe tweet-info.
Assess
Two types of assessments were performed, visual assessment and programmatic assessment. And the following issues were found:

## Quality
twitter_archive
'in_reply_to_status_id', 'in_reply_to_user_id', 'retweeted_status_id', 'retweeted_status_user_id' are of type float, they should be string or integers
'timestamp','retweeted_status_timestamp' should be of type datetime
Missing values in dog stage columns have "None" instade of NaN
'rating_numerator' and 'rating_denominator' has some invalid values like 0, 1776 or 170
Invalid names or "None" found in 'name' column for many dogs, like a, an, the, such, etc..
Not all 'text' column content is shown, the endings are truncated
'source' column has extra text that makes it less readable
Has missing values in colmun 'expanded_urls'
tweet_info
2 tweet_id information are missing
Tidiness
In twitter_archive dog stages are poorly structured into multiple columns, where one column is enough
tweet_info and image_predictions can be merged with twitter_archive

## Clean
All the issues mentioned in the assessment phase were resolved programmatically. For example, the four columns on the dog stage were merged into one column, some erroneous column data types were changed to the appropriate type, some invalid data were handled such as some invalid dog ratings found in the given data and so on. Finally, cleaned data files were merged as one file to make the data ready for analysis.


## Analysis
After the data wrangling, we have ready-for-analysis data. We performed a quick analysis and elicitate some insights about it.
