# Cart Recommendation Data Pipeline

## Motivation:
In today's digital landscape, personalized experiences are paramount to engaging and retaining users. E-commerce, in particular, thrives on personalized recommendations - a mechanism that provides customers with suggestions based on their interests, browsing behavior, and purchase history. A well-crafted recommendation system can significantly boost user engagement, increase sales, and improve customer satisfaction. As an aspiring data engineer, I created this pipeline to get more experience in using real time data to make personalized and effective recommendations to users. 

## Summary of Approach:
My process began by analyzing a dataset from Kaggle from an e-commerce store used for cosmetic products. It contained the user id, user sessions, product id, user events, brand names, prices, and category ids. The user events contained purchases, views, adds to cart, and removals from cart. 
![Screenshot]<img width="973" alt="Datacategories" src="https://github.com/ginaiscoding/CartRecommendation/assets/104851148/91738991-f32a-4988-8f4c-f026984df160">

Using this data I analyzed a selected user's interactions, maintaining a history of their session activity and item interactions. The system then recommends items based on the user's previous interactions, prioritizing items in the user's cart that haven't been purchased yet. The recommended items are stored, and the system keeps track of the last N items for each session, where N is a predefined parameter. 

To simulate a real-time streaming environment, I then generate a new session ID for the user and produce a new message for the Kafka topic 'user-events'. The same recommendation procedure is performed for the new session, and an updated message is sent to the Kafka topic.

After simulating all sessions, the system evaluates its performance by calculating the precision and recall of the recommendations. Precision measures the proportion of recommended items that were relevant (i.e., appeared in the ground truth), while recall measures the proportion of relevant items that were recommended.

This approach combines real-time data processing with a historical perspective of user behavior, allowing the recommendation system to adapt to each user's preferences and browsing patterns, thereby enhancing the overall user experience and potentially driving increased engagement and sales.

## What I Learned:
This was my first time ever creating a data pipeline that used real-time data processing. It was a lot harder than I expected and I learned a lot. One of the key learning points is how to handle real-time data using Kafka. This is essential in many modern applications, particularly in situations wehre decisions need to be made quickly based on the most recent data. I also learned the basic mechanics of building a personalized recommendation system and how to calculate the performance of its metrics. By calculating precision and recall, I can assess the effectiveness of my system. And although my numbers were not great, I am very pleased to have made a working model. All in all i learned a lot from this 'simple' data pipeline project and i couldnt have done it without the help of my project leader Leon Staubach. Thanks so much! 
