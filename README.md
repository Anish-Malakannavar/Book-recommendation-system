# Book-recommendation-system

This project aims to build a book recommendation system using collaborative filtering and popularity-based filtering techniques. The dataset used in this project contains information about books, users, and their ratings.

## Exploratory Data Analysis (EDA) Summary:
This project involved analyzing three datasets: books, users, and ratings, to gain insights into user behavior and preferences in book ratings. The datasets were cleaned, explored, and merged to create a comprehensive dataset for analysis.

#### Books Dataset:

Explored book titles and authors, identifying popular books and authors.
Investigated the distribution of publication years and publishers.
Handled missing values in the book author column by filling them with the mode.
Converted the book author column to a category data type for efficient storage.

#### Users Dataset:

Examined user locations and ages to understand the demographics of readers.
Detected and treated outliers in the age column, replacing them with the mean of non-outlier data.
Filled missing values in the age column with the mean age.

#### Ratings Dataset:

Explored the distribution of book ratings, noting that higher ratings were more common among users.
Separated explicit ratings (1-10) from implicit ratings (0) for analysis.

#### Merged Dataset:

Combined the books, users, and ratings datasets into one comprehensive dataset for analysis.
Investigated the merged dataset's information, including book titles, authors, publication years, user IDs, ratings, locations, and ages.

# Model

## Popularity based filtering

1. **Merging Ratings with Books**: Combining the ratings and books data allows us to associate each rating with its corresponding book, so we can analyze ratings for each book.
2. **Counting Number of Ratings per Book**: Counting the number of ratings for each book helps us understand how popular a book is among users. Books with more ratings are likely to be more popular.
3. **Calculating Average Rating per Book**: Calculating the average rating for each book gives us an idea of the overall rating for a book. This helps us identify books that are not only popular but also highly rated.
4. **Merging Number of Ratings and Average Rating Dataframes**: By merging the dataframes containing the number of ratings and average rating, we create a single dataframe that includes both pieces of information for each book.
5. **Filtering Popular Books**: Filtering the dataframe to include only books with at least 250 ratings helps us focus on books that are popular and have been rated by a significant number of users. This threshold can be adjusted based on the specific requirements of the recommender system.
6. **Merging with Books Dataframe**: Merging the filtered dataframe with the original books dataframe allows us to include additional information about the books, such as the author and image URL, in the final list.
7. **Removing Duplicate Entries**: Dropping duplicate entries based on the book title ensures that each book appears only once in the final list, avoiding duplication of information.
8. **Selecting Final Columns**: Selecting and rearranging columns in the final dataframe helps us present the information in a clear and concise manner, including only the relevant columns for the recommendation list.

## **Collaborative Filtering-Based Recommender System**

1. **Identifying Active Users**: It identifies users who have rated more than 200 books, assuming that these users are more active and their ratings are more reliable.
2. **Filtering Ratings**: It filters the ratings dataframe to include only ratings from the active users identified in the previous step.
3. **Identifying Popular Books**: It identifies books that have been rated by at least 50 users, assuming that these books are popular and widely read.
4. **Filtering Final Ratings**: It filters the ratings dataframe to include only ratings for the popular books identified in the previous step.
5. **Creating a Pivot Table**: It creates a pivot table where rows represent books, columns represent users, and values represent ratings. This format is suitable for collaborative filtering.
6. **Calculating Similarity Scores**: It calculates the cosine similarity scores between each pair of books based on their user ratings. This helps determine how similar one book is to another based on user preferences.
7. **Defining a Recommendation Function**: It defines a function that takes a book title as input and returns a list of similar books based on the similarity scores. It finds the index of the input book in the pivot table, sorts the similarity scores, and retrieves the top 4 most similar books (excluding the input book itself).
8. **Generating Recommendations**: It uses the recommendation function to generate recommendations for the book '1984' and returns the book titles, authors, and image URLs of the recommended books.

### **Instructions for Deployment**

1. Clone the repository to your local machine.
2. Install the required dependencies using **`pip install -r requirements.txt`**.
3. Run the Flask application using **`python app.py`**.
4. Visit the specified URL in your web browser to access the book recommendation system.

### **Conclusion**

This project demonstrates the implementation of a book recommendation system using collaborative filtering and popularity-based filtering. The system provides personalized recommendations based on user ratings and can be further optimized and deployed for real-world use.

### **Future Improvements**

- Incorporate additional features such as user demographics and book genres for more personalized recommendations.
- Implement a user interface for easier interaction with the recommendation system.
- Continuously update the recommendation system to improve its accuracy and relevance.

### **References**

- [Surprise library documentation](https://surprise.readthedocs.io/en/stable/)
- Flask documentation
- Pandas documentation
