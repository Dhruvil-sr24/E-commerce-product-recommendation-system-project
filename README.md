# E-commerce-product-recommendation-system
This project demonstrates a machine learning-based Product Recommendation System, designed to offer users personalized product suggestions based on browsing and purchase behavior. The system analyzes user interactions by leveraging collaborative and content-based filtering to provide relevant product recommendations. The goal is to enhance the shopping experience for users while boosting sales for e-commerce platforms.

# Dataset
The dataset used for this project is sourced from Amazon's electronic products ratings. It includes user reviews and ratings without any predefined headers. To prevent bias, each user and product is assigned a unique identifier instead of using names or identifiable data.

Dataset Link: Amazon Electronics Ratings Dataset https://www.kaggle.com/datasets/skillsmuggler/amazon-ratings/code

# Implementation Approach
#1. Rank-Based Recommendations
Objective:
  * Recommend products with the highest ratings count.
  * Target new users with popular product recommendations.
  * Address the Cold Start Problem for users with no prior interactions.
Outputs:
  * Suggest the top 5 products with a minimum of 50 or 100 interactions.
Methodology:
  * Compute the average rating for each product.
  * Count the total ratings for each product.
  * Create a DataFrame sorted by average ratings.
  * Implement a function to fetch the top n products meeting a specific interaction threshold.
# 2. Similarity-Based Collaborative Filtering
Objective:
  * Provide personalized recommendations tailored to users based on the preferences of similar users.

Outputs:
  * Suggest the top 5 products based on interactions of similar users.
Methodology:
  * Convert user_id values to integers for easier handling.
  * Define a function to identify similar users:
  * Use cosine similarity to calculate similarity scores between users.
  * Rank users based on similarity scores and exclude the original user.
  * Define a recommendation function:
  * Identify products interacted with by similar users but not the current user.
  * Suggest the top n products from this filtered list.
# 3. Model-Based Collaborative Filtering
Objective:
  * Generate personalized recommendations using a model-based approach to handle sparsity and scalability issues.

Outputs:
  * Suggest the top 5 products for any user based on predicted preferences.
Methodology:
  * Transform the interaction matrix into a CSR (Compressed Sparse Row) format to optimize memory and computation.
  * Perform Singular Value Decomposition (SVD) to reduce the matrix's dimensionality to 50 latent features.
  * Predict ratings for all users by reconstructing the matrix from the SVD components.
  * Store predictions in a DataFrame for easy access.
  * Create a recommendation function:
  * Compare actual and predicted ratings for a user.
  * Filter out products already rated by the user.
  * Rank products by predicted ratings to suggest the top n items.
Model Evaluation:
  * Calculate the RMSE (Root Mean Squared Error) between actual and predicted ratings:
  * Compute the mean squared error (MSE) of predictions.
  * Take the square root of MSE to get RMSE.
  * The RMSE provides insight into the accuracy of the model's predictions.
#### Note:
⚠️ This project is intended solely for educational purposes to understand the workings of recommendation systems. 

