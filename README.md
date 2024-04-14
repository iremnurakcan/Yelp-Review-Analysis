# Yelp-Review-Analysis
# 1. Overall Project Objectives
Yelp is an application that provides a platform for customers to write reviews and give star ratings. Research indicates that a one-star increase led to a 59% increase in revenue for independent restaurants. Therefore, we see the Yelp dataset as a valuable repository of insights.

The main purpose of our project is to conduct a thorough analysis of 7 different cuisine types of restaurants, including Korean, Japanese, Chinese, Vietnamese, Thai, French, and Italian. We aim to determine what makes a good restaurant, what concerns customers have, and then make recommendations for future improvements and profit growth. Specifically, we will analyze customers' reviews to understand why customers love or dislike a restaurant. For instance, great reviews might be due to friendly service, while negative reviews could be about high prices. Additionally, we will compare these 7 cuisine types to gain valuable insights and make customized recommendations for different types of restaurants.

# 2. Description of Data
The Yelp dataset was downloaded from the Kaggle website. It includes a total of 5,200,000 user reviews and information on 174,000 businesses. We will focus on two tables: the business table and the review table.

Attributes of the business table include:

- business_id: ID of the business
- name: name of the business
- neighborhood
- address: address of the business
- city: city of the business
- state: state of the business
- postal_code: postal code of the business
- latitude: latitude of the business
- longitude: longitude of the business
- stars: average rating of the business
- review_count: number of reviews received
- is_open: 1 if the business is open, 0 otherwise
- categories: multiple categories of the business

Attributes of the review table include:

- review_id: ID of the review
- user_id: ID of the user
- business_id: ID of the business
- stars: ratings of the business
- date: review date
- text: review from the user
- useful: number of users who voted a review as useful
- funny: number of users who voted a review as funny
- cool: number of users who voted a review as cool

# 3. Direction of Analysis
Exploratory data analysis

- Count the number of each cuisine type of restaurants
- Count the number of reviews in each cuisine type of restaurants
- Visualize the distribution of restaurants according to the ratings and cuisine types of restaurants.
Review Analysis

- Clean the category column in the business table into different cuisine types of restaurants and find out how the reviews can help this type of restaurants improve in the future.
- Refer to the business ID in the business table to the review table, collect all the reviews of this type of restaurants, and perform sentiment analysis to analyze frequent words in positive and negative reviews.
- Implement an SVM model to get relatively positive and negative words and get scores for each word.
- Get the top 10 positive words and negative words in each cuisine type of restaurants to understand the reasons for high and low scores.
- Compare among different types of restaurants to figure out the advantages and disadvantages, then we can generate a series of recommendations for this type of restaurants for future development.
Overall, recommendations may have different topics, including but not limited to service, food, or decoration, etc. Our analysis is generally based on review words such as rude, overpriced, and slow to determine which aspect of these types of restaurants they could improve.

# 4. Summary of Progress
Selection and Filtering

- Filter out 50 states of the US.
- Filter out all restaurants in the US.
Cleaning

- Categorize all restaurants by cuisine type using matching keywords.
- Delete all records with a null category.
- Remove quotation marks from the name and address columns.
- Label restaurants with a rating above 4 as positive, below 3 as negative, and label rating 3 as neutral.
- Drop rows with a neutral label.
- Apply 'bag of words': the frequencies of various words that appear in each review as features and conduct SVM model to get scores for each word.
Reshaping and Reindexing

- Reindex the data frame.
- Build a new column to input the new category name and delete the previous column.
- Convert array to a dataframe.
Visualization

- Visualize the distribution of restaurants and reviews by category using seaborn.
- Visualize the distribution of restaurants and reviews by rating.
- Visualize the top 10 negative words and positive words in each cuisine type.
Manipulation

- Obtain a 'polarity score' (a value that reflects the polarity of sentiment) towards each restaurant category, where the sentiment score of each word is first multiplied by its frequency, then normalized by the total number of reviews for the specific category of restaurants.
Merging multiple data sets

- Merge the business table and review table.

# 5. Findings
In general, we found that for most restaurant types, 'delicious' ranks first among all positive words, indicating that taste might weigh more than other factors like service and price when people are judging a restaurant. For most cuisine types, the word 'friendly' ranks first before 'reasonable', suggesting that friendly service is more likely to be the reason for a high score rather than a reasonable price. It was also observed that when it comes to the flavor of food, customers value freshness more than tastiness.

Different characteristics are also shown for different restaurant categories. Vietnamese and Italian food received positive feedback because of freshness, while French restaurants received positive reviews for their sweet food. However, sweet food is the reason for Korean restaurants to have negative reviews. Korean, Japanese, Chinese, and Thai have positive reviews mainly for their friendly service, especially for Korean restaurants, since 'attentive' ranks third. The variety of food is also the reason for a high score for Korean, Japanese, and Thai cuisine types. 'Fun' and 'creative' are special characteristics for Japanese restaurants. For the Italian cuisine type, customers prefer classic Italian food. The reason for a high score in the French cuisine type is related to the romantic and beautiful appearance or environment.

From the negative word list, we could observe that 'bland' is one of the main problems for Korean, Thai, and Vietnamese restaurants, which means customers expect food of these three cuisine types to be spicy. For French, Italian, and Japanese cuisine types of restaurants, it is likely to have a low score because the food is cold. The low score of Japanese cuisine type is also due to the dark and crowded environment. 'Sour' is one of the main problems for Chinese cuisine type. Slow service is the main negative characteristic for Korean and French. French cuisine type receives negative reviews also for the expensive price. Thai receives negative reviews mainly for greasy food.

Since our analysis may help to extract specific features from any set of reviews, restaurant owners can make good use of it for essential information once they received a certain amount of Yelp reviews. From those reviews, they can understand why customers love or dislike their restaurants, maybe great reviews primarily due to fresh food, or perhaps unsatisfied reviews caused by too high price. Meanwhile, they can also compare the restaurant with similar restaurants within the same type.
