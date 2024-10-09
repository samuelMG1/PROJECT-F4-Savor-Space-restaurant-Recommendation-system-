# Food Tourism: Personalized Restaurant Recommendations

# Project Overview
This project aims to create a personalized restaurant recommendation system that enhances the dining experience for users by leveraging machine learning and data analysis. The system provides tailored restaurant suggestions based on user preferences and restaurant attributes, helping users discover new culinary experiences with ease.

# Problem Statement
With the vast number of dining options available, making an informed choice for the perfect restaurant can be overwhelming. Traditional methods of filtering restaurants by location, cuisine, or amenities do not fully capture individual user preferences. This project seeks to address this challenge by developing a restaurant recommendation system that offers personalized suggestions based on a user’s specific tastes and past preferences.

# Objective
To develop a personalized restaurant recommendation system using content-based filtering and collaborative filtering techniques that provide users with relevant dining suggestions based on their preferences.

# Dataset
The dataset used in this project was scraped from Yelp and includes the following features for each business:

user_id: Unique identifier for each user.
business_id: Unique identifier for each business (restaurant).
name: Name of the restaurant.
address: Full address of the restaurant.
stars: Rating given by users (1.0 - 5.0 stars).
text: The review text provided by users.
review_count: Number of reviews the restaurant has received.
city: City where the restaurant is located.
state: State where the restaurant is located.
latitude: Latitude of the restaurant’s location.
longitude: Longitude of the restaurant’s location.
attributes: Attributes and features of the restaurant (e.g., parking, ambiance).
categories: List of restaurant categories (e.g., Italian, Mexican).
hours: Opening hours of the restaurant.

# Data Preparation
Renaming columns for clarity.
Handling missing data by removing or filling missing values.
Removing duplicate entries.
Selecting relevant features for the analysis.
Filtering rows to include only relevant businesses (restaurants).
Methodology

# Exploratory Data Analysis (EDA)
The dataset was analyzed to understand trends, including the distribution of restaurant ratings, popular restaurant categories, and the number of reviews per city. Visualizations such as histograms, box plots, and word clouds were used to illustrate key insights.

# Modeling
## Content-based Recommendation System:

Implemented using cosine similarity between TF-IDF vectors of restaurant descriptions to recommend restaurants based on user preferences.
## Collaborative Filtering:

Developed using the Surprise library’s SVD algorithm to predict user ratings based on similarities between users and restaurants.
Grid search and cross-validation were used to tune the model’s hyperparameters, improving its performance.

## Deep Neural Networks:

A deep learning model was incorporated to further improve predictions, using restaurant embeddings and dense layers to predict user ratings.

## How to Run the Notebook
Prerequisites
Python (version 3.6 or later)
Jupyter Notebook
Required Python libraries: numpy, pandas, matplotlib, seaborn, scikit-learn, surprise, tensorflow
Steps to Run:
Clone this repository or download the .ipynb file.
Install the necessary Python libraries:

# Results
The content-based filtering model provides personalized recommendations by analyzing the similarity between restaurant descriptions and user preferences.
The collaborative filtering model predicts restaurant ratings based on user behavior and provides additional recommendations.
The deep learning model further refines these predictions by capturing complex interactions between user and restaurant features.
Minimum Viable Product (MVP)
The system successfully addresses the cold start problem by switching between content-based recommendations and collaborative filtering based on user input. It provides a minimum viable product that offers restaurant recommendations in a user-friendly manner.

# Future Work
User Feedback Integration: Incorporate user feedback to continuously improve the recommendation system.
Geographical Expansion: Expand the geographical coverage to include more cities and regions.
Advanced Visuals: Add restaurant images and dish photos to enhance the user experience.
Real-time Updates: Enable real-time updates of restaurant information, including menu changes and opening hours.
Collaboration with Food Delivery Services: Integrate with food delivery services to allow users to order directly from recommended restaurants.

# Contributions
This project was developed by Andrew Manwa, Elsie Serem, Martin Omondi, Nancy Maina, and Samuel Gathogo. Contributions are welcome—please fork the repository and submit a pull request with proposed improvements.

License
This project is licensed under the MIT License. 
