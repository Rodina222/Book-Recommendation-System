# Book-Recommendation-System
A book recommendation system is a tool or algorithm that recommends books to users based on their preferences, behavior, or other relevant data, aiming to help them find new books of interest and improve their reading experience through various techniques. This is a team project of 4 members.

## Implementation

### Setting up

```bash
!pip install pyspark
```

### Dependencies
- PySpark
- Matplotlib
- Seaborn

### Initializing Spark Session
from pyspark.sql import SparkSession

# Create a Spark Session
```bash
spark = SparkSession.builder \
    .appName("Book Recommendation") \
    .getOrCreate()
```
## Dataset
The dataset used for this project is from Kaggle's Book Recommendation Dataset, which includes:

Books: Contains book details such as ISBN, title, author, publication year, and publisher.
Users: Represents users with anonymized IDs and demographic data.
Ratings: Contains book rating information, with ratings ranging from 1-10 or implicit (0) if not rated.
Preprocessing
Handling Missing Values
Missing values in columns like 'Age' were handled by replacing them with the median age.

### Data Cleaning
Duplicates were removed from the dataset to ensure data integrity and avoid bias in recommendations.

### Exploratory Data Analysis (EDA)
Various EDA techniques were used to understand the dataset, including visualizations of ratings distribution, publication years, top publishers, and user locations.

## Model Building
- Collaborative Filtering with ALS
- ALS (Alternating Least Squares) model was employed for collaborative filtering, focusing on item-based recommendations.

## Training and Evaluation
The model was trained using a cross-validation pipeline to optimize hyperparameters. Evaluation metrics such as RMSE (Root Mean Squared Error) were used to assess model performance.

## Recommendations
Top recommendations for users and books were generated using the trained ALS model, providing personalized suggestions based on user preferences.

## Results
The model achieved an RMSE of 3.93, indicating good performance in predicting user ratings.

## Additional Experiments
Experimentation with K-means clustering for book grouping and analysis was also conducted, exploring alternative approaches to enhance recommendation accuracy.

## Saving and Loading Models
Trained models were saved for future use, ensuring scalability and reusability of the recommendation system.

## Conclusion
This project demonstrates the implementation of a book recommendation system using collaborative filtering techniques with PySpark. By leveraging user behavior and preferences, the system enhances user experience by suggesting books tailored to individual tastes.
