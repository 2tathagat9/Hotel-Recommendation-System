# Hotel-Recommendation-System

In the recent years, online hotel booking has become most popular way to book a hotel. As the rate of growth of online searching of hotel has been increased due to which online hotel searching becomes tedious task. Also, the large amount of online information is increasing day by day. User’s preference plays very crucial role while recommending the hotel. Historical data of user’s preferences helps recommendation system to recommend best option. The model that we are proposing is a content-based recommendation system that recommends hotels based on the location and the requirements of the user. We do so using the nltk library in Python to apply some techniques of NLP to analyse the reviews of hotels left by users.

## Dataset Used

The dataset that we used contains 515,000 customer reviews and scoring of 1493 luxury hotels across Europe. The csv file contains 17 fields:

1. Hotel_Address: Address of hotel.
1. Review_Date: Date when reviewer posted the corresponding review.
1. Average_Score: Average Score of the hotel, calculated based on the latest comment in the last year.
1. Hotel_Name: Name of Hotel
1. Reviewer_Nationality: Nationality of Reviewer
1. Negative_Review: Negative Review the reviewer gave to the hotel. If the reviewer does not give
the negative review, then it should be: ‘No Negative’.
1. ReviewTotalNegativeWordCounts: Total number of words in the negative review.
1. Positive_Review: Positive Review the reviewer gave to the hotel. If the reviewer does not give
the negative review, then it should be: ‘No Positive’.
1. ReviewTotalPositiveWordCounts: Total number of words in the positive review.
1. Reviewer_Score: Score the reviewer has given to the hotel, based on his/her experience.
1. TotalNumberofReviewsReviewerHasGiven: Number of Reviews the reviewers has given in the
past.
1. TotalNumberof_Reviews: Total number of valid reviews the hotel has.
1. Tags: Tags reviewer gave the hotel.
1. dayssincereview: Duration between the review date and scrape date.
1. AdditionalNumberof_Scoring: There are also some guests who just made a scoring on the service
rather than a review. This number indicates how many valid scores without review in there.
1. lat: Latitude of the hotel.
1. lng: Longtitude of the hotel.

The dataset can be accessed here:
[Download the dataset](https://www.kaggle.com/datasets/jiashenliu/515k-hotel-reviews-data-in-europe?resource=download)

## Implementation

### Pre-processing the Data

1. First we loaded the dataset into our model and used the `head()` method to view the first 5
entries.
2. Next we replaced “United Kingdom” with “UK” and used `unique()` command to see all the
different country names.
3. Then we dropped some unnecessary columns from our dataset.
4. Next we made an impute function which converts strings of list into a normal list. We then
applied it to the “tags” column in the dataset.
5. Next we converted the contents of the columns “tags” and “countries” into lowercase.

### Recommender Function

* First we have taken location and description as a reason of visit to that place.
* Next we have lower cased the description using `.lower()` command.
* Now we have tokenized our lower cased description.
* In next line we have made a stop_words variable in which we loaded English dataset as the
stop word dataset.
* Next we have initialised the lemmatizer in the variable lemm.
* Now we will remove stop words from the description.
* Here we have initialised the set named filtered set and we have also added lemmatized or root
word to the filtered set.
* Now we will read the countries from the parameter named location.
* Next we will go through each hotel in the country mentioned and we will tokenize and
lemmatize the description of the hotels.
* Now we will rank each hotel based on the number of word matched.
* Here we have sorted the country dataset based on the similarity index.
* At last we have returned the Hotel name, average score, hotel address, similarity index,
matched as our output for the hotel recommend on the basis of words matched.
